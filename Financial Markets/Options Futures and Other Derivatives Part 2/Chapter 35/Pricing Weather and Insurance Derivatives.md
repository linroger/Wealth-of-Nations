---
tags:
  - cat_bonds
  - historical_data
  - insurance_derivatives
  - risk_neutral_pricing
  - weather_derivatives
aliases:
  - Pricing Insurance Derivatives
  - Pricing Weather Derivatives
  - Weather and Insurance Derivatives
key_concepts:
  - CAT bond returns
  - Historical data estimation
  - Insurance derivative pricing
  - Risk-neutral valuation
  - Weather derivative pricing
---

# 35.7  PRICING WEATHER AND INSURANCE DERIVATIVES  

One distinctive feature of weather and insurance derivatives is that there is no systematic risk (i.e., risk that is priced by the market) in their payoffs. This means that estimates made from historical data (real-world estimates) can also be assumed to apply to the risk-neutral world. Weather and insurance derivatives can therefore be priced by  

1. Using historical data to estimate the expected payoff   
2. Discounting the estimated expected payoff at the risk-free rate.  

Another key feature of weather and insurance derivatives is the way uncertainty about the underlying variables grows with time. For a stock price, uncertainty grows roughly as the square root of time. Our uncertainty about a stock price in 4 years (as measured by the standard deviation of the logarithm of the price) is approximately twice that in 1 year. For a commodity price, mean reversion kicks in, but our uncertainty about a. commodity's price in 4 years is still considerably greater than our uncertainty in 1 year. For weather, the growth of uncertainty with time is much less marked. Our uncertainty. about the February HDD at a certain location in 4 years is usually only a little greater than our uncertainty about the February HDD at the same location in 1 year.. Similarly, our uncertainty about earthquake losses for a period starting in 4 years is usually only a little greater than our uncertainty about earthquake losses for a similar period starting in 1 year..  

Consider the valuation of an option on the cumulative HDD. We could collect 50 years of historical data and estimate a probability distribution for the HDD. This could be fitted to a lognormal or other probability distribution and the expected payoff on the option calculated. This would then be discounted at the risk-free rate to give the value of the option. The analysis could be refined by analyzing trends in the historical data and incorporating weather forecasts produced by meteorologists.  

# Example 35.4  

Consider a call option on the cumulative HDD in February 2019 at the Chicago.   
O'Hare Airport weather station with a strike price of 700 and a payment rate of.   
$\$10,000$ per degree day. Suppose that the HDD is estimated from 50 years of.   
historical data to have a lognormal distribution with the mean HDD equal to 710 and the standard deviation of the natural logarithm of HDD equal to 0.07..   
From equation (15A.1), the expected payoff is.  

where  

$$
\begin{array}{c}{{10,000\times\left[710N(d_{1})-700N(d_{2})\right]}}\ {{}}\ {{d_{1}=\displaystyle\frac{\ln(710/700)+0.07^{2}/2}{0.07}=0.2376}}\ {{}}\ {{d_{2}=\displaystyle\frac{\ln(710/700)-0.07^{2}/2}{0.07}=0.1676}}\end{array}
$$  

or $\$230,900$ . If the risk-free interest rate is $3\%$ and the option is being valued in February 2018 (one year from maturity) the value of the option is  

$$
250,900\times e^{-0.03\times1}=243,400
$$  

or $\$243,400$  

We might want to adjust the mean of the probability distribution of HDD for temperature trends. Suppose that a linear regression shows that the cumulative HDD for February is decreasing at the rate of 0.5 per year (perhaps because of global warming), so that the estimate of the mean HDD in February 2019 is only 697. Keeping the estimate of the standard deviation of the natural logarithm of the payoff the same, this would reduce the value of the expected payoff to $\$180,400$ and the value of the option to $\$175,100$  

Finally, suppose that long-range weather forecasters consider it likely that. February 2019 will be particularly mild. The estimate of the expected HDD might then be reduced even further making the option even less valuable..  

In the insurance area, Litzenberger et al. have shown that there is (as one would expect) no statistically significant correlation between the returns from CAT bonds and stock market returns.' This confirms that there is no systematic risk and that valuations can. be based on the actuarial data collected by insurance companies.  

CAT bonds typically give a high probability of an above-normal rate of interest and a. low probability of a big loss. Why would investors be interested in such instruments?. The answer is that the expected return (taking account of possible losses) is higher than. the return that can be earned on risk-free investments. However, the risk in CAT bonds can (at least in theory) be completely diversified away in a large portfolio. CAT bonds. therefore have the potential to improve risk-return trade-offs..  
