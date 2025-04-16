---
tags:
  - '#apple_stock_aapl'
  - '#daily_returns_first_differences'
  - '#etf_analysis'
  - '#financial_data_analysis'
  - '#lognormal_distribution'
  - '#probability_distributions'
  - '#skewness_kurtosis'
  - '#sp_500_etf_spy'
  - '#stock_returns'
  - '#technology_sector_etf_xlk'
---
# 5.2 CONTRASTING THE NORMAL WITH THE LOGNORMAL PROBABILITY DISTRIBUTIONS

Based on properties of the lognormal distribution, if $S_{t}=S_{t-1}e^{R_{t}^{c}}$ and $R_{t}^{c}$ is normally dis-.
tributed, then we know. $S_{t}$ is lognormally distributed. Recall if $x$ has a lognormal distribu-.
tion, then the PDF is.

$$
\lambda(x)={\frac{1}{x\sigma{\sqrt{2\pi}}}}e^{-\left({\frac{[\ln(x)-\mu]^{2}}{2\sigma^{2}}}\right)}.
$$

Again, the range of a lognormally distributed variable is $0<x<+\infty$ . Importantly, zero is not included.

Recall from Chapter 4, the. $n^{t b}$ noncentral moment is defined as ${\mu_{n}}^{\prime}(x)=E(x^{n})$ and the $n^{t b}$ central moment is defined as. $\mu_{n}(x)=E[(x-\mu)^{n}]$ . Thus, subtracting a constant term from a random variable affects only the mean, not the higher central moments, such as. variance, skewness, and kurtosis. We denote the first difference or dollar profit and loss as

$$
\Delta S_{t}=S_{t}-S_{t-1}.
$$

There are many finance applications where we are interested in dollar gains and losses. For example, company earnings are simply revenues less expenses. Because earnings can be zero or negative, we do not want model earnings with a distribution that does not admit zero or negative numbers.4 Because the uncertainty at time. $t-1$ is solely the instrument price or value at time $t$ , the expected value is

$$
E(\Delta S_{t})=E(S_{t})-S_{t-1}.
$$

The higher central moments are simply

$$
\operatorname{var}(\Delta S_{t})=\operatorname{var}(S_{t}),
$$

$$
S k e w(\Delta S_{t})=S k e w(S_{t}),\mathrm{and}
$$

$$
K u r t o s i s(\Delta S_{t})=K u r t o s i s(S_{t}).
$$

Several important insights can be gained when we assume a lognormal distribution. First, the continuously compounded rate of return follows a normal distribution. Second, the normalized skewness of the rate of return should be zero, but the normalized skewness of the first difference should be positive. Third, the normalized kurtosis of the rate of return should be 3, but the normalized kurtosis of the first difference should be greater than 3.5

When building quality valuation models, it is important to understand empirical properties of financial data. Here we briefly review empirical data related to two exchangetraded funds (ETFs), the S&P 500 ETF (SPY) and the Technology Sector ETF (XLK), as well as Apple stock (AAPL). We explore five years of daily data. Figure 5.3 provides plots of the time series rates of return and first differences. To facilitate comparison, the first differences are based on an assumed $\$1$ investment at the beginning of the period. For ease of comparison, we set the $y\cdot$ -axis to be the same for all the return plots. Likewise, we set the y-axis to be the same for all the first difference plots. Intuitively, we would expect that an individual stock would be more risky than a portfolio of stocks within its sector. Further, we would expect the technology sector ETF would be more risky than a broad-based index such as SPY. The pattern of standard deviations is consistent with our intuition. Outside of basic distributional properties, it is unclear how skewness and kurtosis would behave. Interestingly, all skewness measures are negative rather than zero or positive as the distributional assumptions would imply. Further, the skewness measures are similar between returns and first differences. We would have expected the first difference skewness to be positive or at least less negative than returns. All kurtosis measures are greater than three with daily first differences being slightly lower.

![](6885aa8b13f918816473cbb048e12c379c069c735990aa3462194384c11a27b0.jpg)
FIGURE 5.3 Time Series of Daily Returns and First Differences

Figure 5.4 provides histograms of this same data along with the corresponding normal distribution probability density function. The histograms are more spread out as we move from SPY to XLK to AAPL. The patterns are very similar when comparing returns and first differences as well as consistent with the previous univariate analysis.

![](2d6d024d9d953fc28ea9f53a1358431aa80fa7dac7005c2a4c9bb9e78316d4ae.jpg)
FIGURE 5.4 Histogram of Daily Returns and First Differences
