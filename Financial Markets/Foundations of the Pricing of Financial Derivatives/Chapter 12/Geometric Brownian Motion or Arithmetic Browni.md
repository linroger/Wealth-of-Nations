---
tags:
  - '#arithmetic_brownian_motion'
  - '#asset_pricing'
  - '#financial_derivatives'
  - '#geometric_brownian_motion'
  - '#lognormal_distribution'
  - '#model_comparison'
  - '#normal_distribution'
  - '#option_pricing_models'
  - '#risk_management'
  - '#stock_splits'
---
# 12.6 GEOMETRIC BROWNIAN MOTION OR ARITHMETIC BROWNIAN MOTION?

The key focus of this book is addressing approaches to valuing financial derivatives. Based on materials covered thus far, there appears to be a key decision to be made in our journey. Do we go with GBM or ABM?

In their exploration of this question, Brooks and Brooks (2017) explore the genesis of. the decision to pursue GBM over ABM. Historically, the first approach was ABM intro-. duced by Bachelier (1900). In France, during Bachelier's time, option contracts technically. could admit negative strike prices. Further, it was only a few decades prior to Bachelier's work that France introduced the Limited Liability Acts on July 24, 1867. For a host of reasons, French companies were slow in adopting a limited liability charter.' Thus, it appears possible that Bachelier addressed options on company stock that had unlimited liability or. a potential for negative prices. Although we will never know if these features motivated Bachelier to pursue ABM over GBM, it is an interesting artifact..

Osborne (1959) provided one of the original analyses of continuously compounded. stock returns. Based on the observation that for percentage changes less than. $15\%$ there is not a material difference between modeling with the normal or lognormal distributions, he opted for the lognormal distribution based on the lognormal appearance of the cross-sectional distribution of stock prices.10 Sprenkle (1961) argued in favor of the log-. normal distribution due to it having no chance of negative values. Alexander (1961) raised some concerns regarding this choice due to time series financial data exhibiting fat tails.

Samuelson (1965) seems to have created the phrase "geometric Brownian motion." He opted for GBM over ABM primarily due to the nonnegativity of the lognormal distribution and some technical problems with Bachelier's (1900) model.11 Following Samuelson (1965), Black and Scholes (1973) as well as Merton (1973) chose GBM.

Brooks and Brooks (2017) identify several issues related to the choice between modeling the underlying with either the lognormal or normal distribution. We briefly highlight a few here:

Positive values, $S_{t}>0$ . With GBM, there is a zero probability of the asset price being zero in the future. ABM solves this problem. Based on US Census data, approximately $0.7\%$ of businesses file for some form of bankruptcy each year. Thus, some percentage of these bankruptcy filing companies result in equity prices being permanently zero. Note there is a fundamental difference between legal bankruptcy, such as a court filing, and economic bankruptcy, such as the stock being deemed worthless. Many legal bankruptcies do not result in economic bankruptcy..
Portfolios, $\Pi_{t}=\sum_{i=1}^{n}N_{i}S_{i,t}$ . With GBM, a simple portfolio of assets follows no known statistical distribution. Thus, internal coherence of risk measures is not feasible due to the lack of the additive property of the lognormal distribution. ABM solves this problem.
Time-series independence. With GBM, changes in the asset returns are assumed to be independent of the asset price itself. ABM suffers from dependence particularly over long periods of time. For example, if a stock price doubles in value, the absolute volatility of price changes does not automatically double with arithmetic Brownian motion.

Factor models, $S_{t}=f(x_{1},x_{2},...,x_{n})$ An asset can have multiple risk factors. ABM can easily handle multiple factors, whereas with GBM it is a difficult challenge. Mathematically, the two approaches can be expressed as.

$$
\begin{array}{r l}&{d S_{t}=\mu(S,t)d t+\displaystyle\sum_{i=1}^{n}\sigma_{\mathbb{S},i}(t)d W_{i}\left({\mathrm{ABM}}\right){\mathrm{and}}}\ &{d S_{t}=\mu(S,t)d t+\displaystyle\sum_{i=1}^{n}\sigma_{i}(t)x_{i}d W_{i}\cdot({\mathrm{GBM}})}\end{array}
$$

Clearly, the ABM version results in the terminal distributions being normally distributed, whereas the GBM version follows no known tractable distribution.

Evidence. Finance is an empirical science; hence, the model choice depends heavily on. financial market behavior. For example, asset prices often behave significantly different in other countries when compared to the Us. Thus, access to alternative frameworks is justified.
Risk. Risk can be represented based on relative measures $(\%)$ or absolute measures $\$9$ or other currency). Stock splits require ABM to manually adjust absolute volatility, but there is a leverage effect that is implicitly handled by ABM. The leverage effect is the intuitive observation that as a stock price declines it becomes more highly leveraged. Thus, by definition the stock price would be expected to be more volatile in a relative sense. GBM automatically adjusts for stock splits, but the leverage effect is ignored.
Extreme volatilities. ABM can handle extreme volatilities better than GBM. For example, with simulations, the lognormal distribution is numerically unstable for high volatilities. In practice, option volatilities in excess of $100\%$ are common for some options. For example, relative volatilities have been found to be above. $1{,}000\%$ for electricity options. Shocking, indeed!
Binomial convergence. GBM can be derived from a multiplicative binomial process. ABM implies an additive binomial process. Both lattices can be modeled to converge to the appropriate terminal distributions.
Homogeneity of degree 1. GBM-based models typically are homogeneous of degree 1, whereas ABM-based models are not.12 For example, within an ABM framework stock splits will result in option pricing models that do not properly adjust. Scaling absolute volatility, however, can easily solve this problem.
Geometric drift. Both ABM and GBM can handle geometric drift.

Ultimately, the choice between ABM-based models or GBM-based models should be based on which model provides the most useful information for improving the financial decision-making process. The better approach for one type of financial process may not be the better approach for another. Thus, there is good reason to study both.
