---
tags:
  - market_risk
  - portfolio_theory
  - value_at_risk
  - var
  - variance_covariance
aliases:
  - VCV
  - VaR
key_concepts:
  - Backtesting VaR accuracy
  - Basel internal models
  - Forecasting volatility methods
  - Market risk measurement
  - Value at Risk (VaR)
  - Variance-covariance approach
---
# MARKET RISK  

# Value at Risk  

# Aims  

• To explain the concept of value at risk (VaR).   
• To measure VaR using the variance-covariance (VCV) approach.   
• To outline methods used in forecasting volatility.   
• To use backtesting to assess the accuracy of VaR forecasts.   
• To outline the ‘Basel internal models’ approach in setting regulatory standards.  

# 44.1 INTRODUCTION  

Financial institutions, particularly large investment banks, hold positions in a wide variety of assets such as stocks, bonds, foreign exchange, as well as futures and options contracts. Because prices of these assets can move quickly and by large amounts, investment banks want to know what risk they are holding over the next 24 hours as well as over the next week or month. Once they know what their risk position is then they can either decide to maintain or reduce it or alternatively to hedge the risk – usually by using derivatives. Risk due to price changes is known as ‘market risk’ and measuring and monitoring changing market risk is the subject of this chapter.  

For their own prudential reasons !nancial intermediaries need to measure the overall ‘dollar’ market risk of their portfolio, which is usually referred to as value at risk (VaR). In addition, the regulatory authorities use VaR to set minimum capital adequacy requirements for !nancial institutions. If a bank has a high VaR then the regulator may limit the amount of dividends paid to stockholders, so that the bank can increase its ‘capital’ via an increase in its retained pro!ts. Alternatively, a bank can increase its ‘capital’ by issuing more stock to investors via a ‘seasoned ofering’ (or ‘rights issue’ in the UK), which it often is reluctant to do because this dilutes the claims on future dividends of existing stockholders. The possibility of having to increase ‘bank capital’ using either of these methods is supposed to act as a deterrent to banks increasing their level of market risk to unacceptable levels.  

The interaction between investment decisions and risk calculations is now absolutely central in managing mutual funds, hedge funds, pension funds, and a bank’s marketable assets. The chief risk o#cer (CRO) in a !nancial institution has a key role in the risk management process.  

In this chapter we examine how to measure market risk, mainly using stocks as our example. There are various ways to measure portfolio risk and we concentrate on the variance-covariance method (also called the delta-normal method). Since market risk varies over time we examine the accuracy of our forecast of VaR.  

# 44.2 VALUE AT RISK (VAR)  

In this section we use concepts from portfolio theory to provide us with a simple yet useful forecast of market risk, namely, value at risk – which is now the industry standard. Suppose you hold a portfolio of stocks. The return $R_{t+1}$ between today and tomorrow, is the capital gain or loss on the stocks (plus any cash payments such as dividends). However, dividend payments are announced in advance, so the source of uncertainty and risk over the next day (say) is mainly due to price changes. For simplicity, assume dividend payments are zero so that the return on a stock is1:  

$$
R_{t+1}=\frac{P_{t+1}-P_{t}}{P_{t}}
$$  

Measuring returns over 1 day allows us to determine daily VaR for a stock portfolio. Suppose you currently hold $\$3,0300$ in your stock portfolio and the CRO reports to the CEO of a bank, that over the next 24 hours (1 day) the VaR is $\$1000$ , at a $95\%$ con!dence level (also referred to as a $5\%$ ‘left-tail’ value or 5th percentile). This implies that:  

Given your current stock portfolio, there is a $95\%$ chance (probability) that you will lose less than $\$100m$ over the next day (24 hrs).  

Note that losing ‘less than’ $\$1000$ also means you might make gains on your portfolio – in fact there is a $50\%$ chance you will make gains (if daily stock returns are normally distributed with a zero mean) – Figure 44.1.  

Note that the risk o#cer is not saying you will lose less than $\$1000$ , only that there is a 95 out of 100 chance that you will lose less than $\$1000$ . So, as a concept VaR involves a speci!c probability or con!dence level and a speci!c time horizon over which we measure risk. We cannot predict exactly how much you will lose (or gain) over any 24-hour period – since the world is risky – we can only provide a ‘best guess’ with a certain probability. This is not the only way we can express the daily VaR and an equivalent statement is:  

![](9c99cc8797845579d923a4f65ef5017a8def885505b2edaae6696ae73fe80f2d.jpg)  
FIGURE 44.1 Normal distribution  

Given your current stock portfolio then you expect to lose less than \$100m (over any 24-hour period), in 19 out of the next 20 days.  

You can see where ‘probability’ comes in, since ‘19 out of 20 days’ is equivalent to ‘95 days out of 100’, that is, $95\%$ of the time. Hence, if you hold the $\$3,0300$ stock portfolio unchanged over the next 20 days, then on about 19 of those days you would lose less than $\$1000$ , hence:  

If the daily portfolio VaR is $\$100m$ , at a $95\%$ confdence level (5th percentile) then if you continue to hold your current stock portfolio, you expect to lose less than \$100m in 19 of the next 20 days and to lose more than \$100m on one day out of the next 20 days.  

Note that even though the VaR concept is concerned with potential losses it is usually reported as a positive number. Much of the material discussed is based on the risk measurement methodology as set out in RiskMetricsTM (1996) which emanates from JPMorgan.  

# 44.2.1 Measuring Risk  

The riskiness of a single asset is summarised in the probability distribution of its returns. For daily stock returns the outcomes can take on many values and a convenient !rst assumption is that these outcomes are normally distributed. There is no single acceptable measure of the riskiness inherent in a particular statistical distribution, but for the normal distribution the standard deviation (or variance) is widely accepted as a measure of risk.  

![](6702daf684228df2bcb8a05adcee90c30b42ddb5313f704c7fef3d039754b765.jpg)  
FIGURE 44.2 Normal distribution  

![](a97879183d435bcf316aaf90fd807a9933ee606d8cbb24a0c84271c85c651f51.jpg)  
FIGURE 44.3 Daily returns S&P 500 (January 1990–March 2019)  

For normally distributed returns we can be $90\%$ certain that the actual return will equal the expected return $\mu$ plus or minus $1.65\sigma$ (see Figure 44.2) where $\sigma$ is the standard deviation of the returns. Put another way, we expect the actual return to be less than $\mu-1.65\sigma$ on $5\%$ of occasions or greater than $\mu+1.65\sigma$ , also on $5\%$ of occasions (e.g. 1 time in 20).  

The mean daily return on a stock is small and close to zero. From a statistical point of view, there is so much ‘noise’ in daily returns (i.e. daily returns have a large standard deviation, relative to their mean return) so:  

• when calculating daily VaR, we assume the mean return is zero.   
• Hence, $1.65\sigma$ is a measure of the (per cent) ‘downside risk’ (at the 5th percentile).  

If you hold a (net) position of $\$1$ in one asset (e.g. stock of AT&T), then the (dollar) VaR is:  

$$
V a R=\$123
$$  

which is a basic ‘building block’ for calculating the VaR of more complex portfolios.  

# EXAMPLE 44.1  

# Calculation of Daily VaR  

Suppose daily stock returns are normally distributed. Assume the mean daily return on AT&T stocks is $\mu=0$ with standard deviation $\sigma=0.005$ ( $0.5\%$ . You hold $\begin{array}{r}{V_{0}=}\end{array}$ $\$115m$ in AT&T stocks. What is the daily $\$1$ -VaR of your position, at the 5th percentile and what does this mean?  

If daily returns $R$ are normally distributed then $\mu\pm1.65\sigma$ has $5\%$ of the probability distribution in each tail – leaving $90\%$ of the probability in the ‘centre’ of the distribution. Hence $90\%$ of daily returns lie between:  

$$
\mu+1.65\sigma=+0.825\%\mathrm{and}\mu-1.65\sigma=-0.825\%
$$  

Put another way, only $5\%$ of the daily returns should exceed $+0.825\%$ and $5\%$ should be smaller than $-0.825\%$ . Either of these cases should occur no more than 1 day in every 20 days (i.e. $5\%$ of the time). The $\$8$ -VaR of a US investor holding $\$115m$ in AT&T stock is:  

$$
V a R=\mathfrak{H}V_{0}(1.65\sigma)=\mathfrak{H}115\mathrm{m}\left(0.825/100\right)=\mathfrak{H}948,750
$$  

Hence in 95 days out of 100, you should not lose more than $\$948,750$ over any 24-hour period (assuming you maintain your initial position of $\$115m$ in AT&T stocks). But $5\%$ of the time (i.e. 5 days out of 100) you will lose more than $\$948,750$ .  

A more direct approach to calculating the daily VaR is to note that the dollar change in value of the stock is $d V=V_{0}R$ , where $V_{0}=$ initial dollar holding in the stock, $R=$ daily return on the stock. It then follows directly that $\sigma_{d V}=V_{0}\sigma_{R}$ and hence the VaR at the 5th percentile is:  

$$
\mathrm{VaR}=1.65\sigma_{d V}=V_{0}(1.65)\sigma_{R}.
$$  

# 44.2.2 Are Daily Returns Normally Distributed?  

Empirically, daily returns (i.e. daily price changes, $d P/P)$ for exchange rates, long-term bond prices, and stock prices are all approximately normally distributed but they do deviate somewhat from normality, in the following ways:  

• return distributions often have fatter tails than the normal distribution • returns are negatively skewed (i.e. there are more observations in the left-tail than the right-tail).  

In Figure 44.3 we show the histogram of daily returns using the S&P 500 index of US stocks – the mean daily return is very close to zero. The histogram is broadly ‘bell shape’, like the normal distribution. But the empirical distribution has a thinner peak than the normal distribution and there are a few more occurrences of extreme negative and positive returns than would be associated with the normal curve (i.e. the empirical histogram has fatter tails than the normal distribution) – this is excess kurtosis. In addition, the empirical distribution is reasonably symmetric so there is no appreciable negative or positive skew. In fact, for daily returns on most spot (cash market) assets it is probably a reasonable approximation to assume normality.  

# 44.2.3 Portfolio Risk  

How can we measure the $\$5$ -VaR of a portfolio of assets? First we present a ‘text book’ approach to this problem and then we use a more direct approach. Let’s take two assets for simplicity – stocks of AT&T and Microsoft, in proportions (or ‘weights’) $1/_{4}$ and ${}^{3}/_{4}$ respectively. The return $R_{p}$ on portfolio of stocks is:  

$$
R_{p}=w_{1}R_{1}+w_{2}R_{2}=(1/4)R_{1}+(3/4)R_{2}
$$  

The standard deviation of returns on the portfolio is given by the usual formula from portfolio theory (as found in standard text books):  

$$
\sigma_{p}=\sqrt{w_{1}^{2}\sigma_{1}^{2}+w_{2}^{2}\sigma_{2}^{2}+2w_{1}w_{2}\rho\sigma_{1}\sigma_{2}}
$$  

where $\sigma_{i}$ is the standard deviation of the return on stock- $i$ and $\rho$ is the correlation coe#cient between the return on stock-1 (AT&T) and the return on stock-2 (Microsoft). So when we have a portfolio of stocks, consideration must be given to all the correlations between returns when calculating the portfolio standard deviation. (Note also that the term $\rho\sigma_{1}\sigma_{2}$ is the covariance between the two returns, usually written $\sigma_{i j}$ .)  

In Equation $\left(44.4\right)\sigma_{p}$ is measured as a ‘per cent per day’ (expressed as a decimal) but the CEO of a bank is more interested in the dollar-VaR. By analogy with the single asset case the $\$1$ -VaR for the portfolio is given by:  

$$
V a R_{p}=V_{p}(1.65)\sigma_{p}=V_{p}1.65\sqrt{w_{1}^{2}\sigma_{1}^{2}+w_{2}^{2}\sigma_{2}^{2}+2w_{1}w_{2}\rho\sigma_{1}\sigma_{2}}
$$  

where $V_{p}$ is the total amount invested in the stock portfolio. It is more convenient if the VaR calculation uses the dollar amount in each stock. If the initial dollar amounts held in each  

stock are $V_{1}=\$100$ and $V_{2}=\$300$ , then $V_{p}=V_{1}+V_{2}=\S400$ and $w_{1}=V_{1}/V_{p}={}^{1}/4$ and $w_{2}=$ $V_{2}/V_{p}={}^{3}/4$ . Substituting for $w_{1},w_{2}$ in (44.5):  

$$
\begin{array}{r l}&{V a R_{p}=\sqrt{(V_{1}1.65\sigma_{1})^{2}+(V_{1}1.65\sigma_{2})^{2}+2\rho(V_{1}1.65\sigma_{1})(V_{2}1.65\sigma_{2})}}\\ &{\qquad=\sqrt{\mathrm{VaR}_{1}^{2}+\mathrm{VaR}_{2}^{2}+2\rho(\mathrm{VaR}_{1})(\mathrm{VaR}_{2})}}\end{array}
$$  

This is rather convenient since the dollar portfolio-VaR uses the individual dollar VaR’s for each stock. If the dollar amounts held in each stock $(V_{1},V_{2})$ are positive, then the smaller the correlation between the two stock returns, the lower is $V a R_{p}$ . This is the usual diversi!cation efect in portfolio theory. However, also note that if you have short-sold say $\$100$ of stock-1 then $V_{1}=-\$10m$ in Equation (44.6). So if stock-2 is held long then the larger is the positive correlation between the two stock returns, the smaller is portfolio risk and the VaR.  

# 44.2.4 Worst-case VaR  

Consider what would make $V a R_{p}$ a rather large number, indicating high portfolio risk. If stock returns are perfectly positively correlated $(\rho=+1)$ and you hold positive amounts in each stock $(V_{1},V_{2})>0$ , then this is a worst-case scenario, since there are no bene!ts from diversi!cation. Thus the maximum value that $V a R_{p}$ can take (for $V_{1}>0,V_{2}>0\rangle$ , known as the worst-case VaR, is given by setting $\rho=+1$ in (44.6) which gives:  

$$
V a R_{p}=V_{p}1.65\left(w_{1}\sigma_{1}+w_{2}\sigma_{2}\right)=V a R_{1}+V a R_{2}
$$  

Hence, the ‘worst-case VaR’ is simply the sum of the individual VaRs.2 In the real world it is unlikely that the correlation between the returns of two stocks like AT&T and Microsoft is $+1$ , so your ‘best estimate of risk will usually be the diversi!ed VaR’ given by Equation (44.6). However, in ‘crisis periods’ it is often the case that correlations increase, and the worst-case VaR provides a ‘high’ !gure which may be representative of these crisis periods (e.g. during the 1987, 2000–1 and 2008 stock market crashes and the bond price meltdown of 1997). So, risk managers usually look at both the diversi!ed-VaR and the worst-case VaR. This gives them a feel for what would happen if historic correlations did not stay the same but increased in a crisis period.  

# 44.2.5 Two Assets  

Using matrix algebra, Equation (44.6) can be succinctly written as:  

$$
\begin{array}{r}{V a R_{p}=[{\bf Z C Z^{\prime}}]^{1/2}\qquadC=\left[\begin{array}{l l}{1}&{\rho}\\ {\rho}&{1}\end{array}\right]}\end{array}
$$  

where $Z=[V a R_{1},V a R_{2}]=[V_{1}1.65\sigma_{1}$ $V_{2}1.65\sigma_{2}]$ is a row vector of the individual VaRs for each asset and $c$ is the $2{\times}2$ correlation matrix.  

When we have more than $n$ -assets, $V a R_{p}$ can be represented in exactly the same way but there are $n$ entries in the $Z$ -vector and the correlation matrix is $(n\times n)$ . Statisticians provide estimates of the next day’s forecast of ‘volatilities’ $\sigma_{i}$ and correlation coe#cients (in matrix C), while traders provide the dollar amounts $V_{i}$ they hold in each stock. So in practice, to calculate $V a R_{p}$ with $n$ -stocks we need:  

1. the dollar position in each of the $n$ -stocks   
2. forecasts of the daily standard deviation and correlations.3  

As mentioned above, when reporting individual VaRs these are always taken as positive, even though they represent a potential loss (which conventionally has a negative sign). In calculating $V a R_{p}$ , the sign of the individual $V_{i}$ must be incorporated in $Z$ and if the stock is held long (i.e. you own it) then $V_{i}>0$ but if the stock has been short-sold then $V_{i}<0.$ A simple example will clarify the issues involved.  

# EXAMPLE 44.2  

# Calculation of Portfolio VaR  

Data: A US investor holds $\$100$ of AT&T stock and has short-sold $\$50$ of Cisco stock. Daily volatility of AT&T, $\sigma_{1}=1.5\%$ and daily volatility of Cisco, $\sigma_{2}=1.0\%$ The correlation between AT&T returns and Cisco returns is $\rho=-0.1$  

Questions: 1. What is the daily VaR? 2. What is the worst-case daily VaR?  

Answer: Long position: $V a R_{1}=(\S10\mathrm{m})1.65(1.5/100)=\S247,500$ Long position: $V a R_{2}=(-\mathfrak{F}55\mathrm{m})1.65(1.0/100)=-\mathfrak{F}82,500$  

$$
\begin{array}{r l}&{\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad}\\ &{\quad\quad\quad\quad=\sqrt{247,500^{2}+82,500^{2}+2(-0.1)(247,500)(-82,500)}}\\ &{\quad\quad=\S268,601}\end{array}
$$  

Note the two negative signs $\cdot_{-0.1}\cdot$ and $\cdot_{-82,500},$ re\$ecting the negative correlation and the short-sale of Cisco, respectively. These two ‘factors’ tend to increase portfolio risk and VaR. You obtain the same result if you use the matrix formulation in Equation (44.8). The worst-case VaR (assumes all stocks are held long and all correlation coe#cients $\rho=+1{\dot{\bf{\rho}}}.$ ).  

Worst-case $V a R_{p}=V a R_{1}+V a R_{2}=\S330\mathrm{,000}.$  

# 44.2.6 VaR: Portfolio of Stocks  

Now we calculate VaR using a more direct approach, which will be useful when we consider more complex portfolios (e.g. containing foreign assets and bonds) in the next chapter. For a portfolio of $n$ -stocks, there is a linear relationship between the dollar change in the value of the portfolio $d V_{p}$ and stock returns. Given $V_{p}=\sum_{i=1}^{n}N_{i}P_{i}$ where $N_{i}=$ number of stocks- $\cdot i$ , $P_{i}=$ price of stock- $i$ , then:  

$$
d{\cal{V}}_{p}=\sum_{i=1}^{n}{\cal{N}}_{i}d P_{i}=\sum_{i=1}^{n}{\cal{V}}_{i}(d P_{i}/P_{i})=\sum_{i=1}^{n}{\cal{V}}_{i}R_{i}
$$  

where $V_{i}=N_{i}P_{i}$ is the dollar amount in each stock and $R_{i}=d P_{i}/P_{i}$ is the (proportionate) return on stock-i. The above holds exactly for stocks and is a reasonable approximation for several other securities (e.g. the return on a foreign stock measured in domestic currency, the return on a bond, FRAs, FRNs, forwards, and futures). It follows directly from Equation (44.9) that the standard deviation of the dollar change in portfolio value is:  

$$
\sigma_{d V_{p}}=\left[\sum_{i=1}^{n}V_{i}^{2}\sigma_{i}^{2}+\sum_{i\ne j}\sum V_{i}V_{j}\rho_{i j}\sigma_{i}\sigma_{j}\right]^{1/2}
$$  

Equation (44.10) can be used to calculate the standard deviation of the dollar change in portfolio value regardless of the form of the distribution of stock returns. But the standard deviation alone does not allow us to determine the 5th percentile lower ‘cut-of’ value, unless we assume a speci!c distribution for asset returns. In particular, if we add the assumption of (multivariate) normally distributed asset returns, then the diversi!ed-VaR at the 5th percentile is $V a R_{p}=1.65\sigma_{d V_{p}}$ , which can be more compactly written (here, for $n=3$ assets):  

$$
V a R_{p}=1.65\sigma_{d V_{p}}=\sqrt{{\bf Z}{\bf C}{\bf Z}^{\prime}}
$$  

$$
\begin{array}{r l r}&{}&{V a R_{i}=V_{i}(1.65)\sigma_{i}}\\ &{}&{Z\quad=[V a R_{1},V a R_{2},V a R_{3}]}\\ &{}&{C=\left[\begin{array}{l l l}{1}&{\rho_{12}\ \rho_{13}}\\ {\rho_{12}}&{1}&{\rho_{23}}\\ {\rho_{13}\ \rho_{23}}&{1}\end{array}\right]\quad(3\times3\ \mathrm{correlation}\ \mathrm{matrix}).}\end{array}
$$  

The linearity and normality assumptions are crucial here. The change in portfolio value is sometimes perfectly consistent with linearity (e.g. for a stock portfolio) and where it is not, we often impose linearity as an approximation (i.e. we use a !rst order Taylor series expansion for the change in portfolio value). Note that if the relationship between $d V_{p}$ and asset returns is highly non-linear (e.g. for stock options), then even if the returns of the underlying assets (stocks) are themselves normally distributed, the distribution of the change in the option’s value will not be normally distributed. Hence, for a portfolio of options we cannot simply use the $\cdot_{1.65\sigma_{d V_{p}}},$ rule – we have to examine the complete distribution of outcomes, using MCS and other techniques.  

Providing we assume linearity and (multivariate) normality, all we need to calculate $V a R_{p}$ is the value of each asset holding $V_{i}$ and forecasts for the correlation coe#cients and the return volatilities – hence it is known as the ‘variance-covariance’ (VCV) method. The worst-case VaR occurs when all the $n$ -assets are assumed to be held long (i.e. all $V_{i}>0$ ) and all assets returns are perfectly positively correlated (hence $\mathbf{C}=$ the unit matrix where all elements are $+1$ ). Thus from (44.11):  

$$
W o r s t-c a s e V a R=V a R_{1}+V a R_{2}+\ldots+V a R_{n}
$$  

The VaR for a portfolio of three stocks is given in Table 44.1. Each individual VaR is calculated as $V a R_{i}=V_{i}(1.65\sigma_{i})$ – this is in the fourth column. The worst-case VaR is simply the sum of the individual VaRs. The diversi!ed VaR is calculated using the formula $\scriptstyle{\sqrt{Z C Z^{\prime}}}$ . The diversi!ed VaR is much smaller than the worst-case VaR because although all the correlation coe#cients are positive, stock-2 has been short-sold (hence the $\cdot_{-10,000},$ in the second column) and this ‘manufactures’ a negative correlation between its return and the returns on stocks 1 and 3. Hence there is a strong diversi!cation efect and the (diversi!ed) VaR at 783 is much less than the worst-case VaR of 1,996.  

An Excel spreadsheet on the website calculates the VaR for a portfolio of 10 stocks using matrix notation.  

TABLE 44.1 VaR, portfolio of three stocks   


<html><body><table><tr><td>Assets</td><td>Value</td><td>Std. dev.</td><td>VaR</td><td colspan="3">Correlation matrix (= C)</td></tr><tr><td>１</td><td>10,000</td><td>5.4180%</td><td>894</td><td>1</td><td>0.962</td><td>0.403</td></tr><tr><td>2</td><td>-10,000</td><td>3.0424%</td><td>502</td><td>0.902</td><td>1</td><td>0.61</td></tr><tr><td>3</td><td>10,000</td><td>3.6363%</td><td>600</td><td>0.403</td><td>0.61</td><td>1</td></tr><tr><td></td><td></td><td></td><td>Individual VaRs</td><td>894</td><td>-502</td><td>600</td></tr></table></body></html>

Worst case $\operatorname{VaR}=1,996$ Diversified 783  

# 44.3 FORECASTING VOLATILITY  

It is clear from the above analysis that to calculate daily-VaR using the variance-covariance approach we need to forecast tomorrow’s stock return volatility. A simple forecasting scheme is to assume that tomorrow’s forecast of daily volatility is a simple moving average (SMA) of past squared returns $R_{t}^{2}$ , over the last 30 days (say):  

$$
\sigma_{t+1}^{2}=(1/30)\sum_{i=0}^{29}R_{t-i}^{2}
$$  

Note that in (44.12) we do not use the more usual term $(R_{t-i}-\overline{{R}})^{2}$ because we have assumed the mean daily return is zero. If today $(=t)$ is Monday after the market has closed, then (44.12) gives a forecast of Tuesday’s volatility based on the squared returns from Monday, last Friday’s, Thursday’s, etc., for the past 30 trading days. When ‘tomorrow’ arrives then on Tuesday, we make a new forecast. Now, our forecast for Wednesday includes Tuesday’s, Monday’s, etc. squared return (and we drop the !nal day’s return from 31 days ago). Hence our forecast is continually updated as we ‘move through time’.  

A problem with the SMA is that it gives equal weight (of 1/30) to all of the past 30 day’s squared returns, when forecasting tomorrow’s volatility. It seems more intuitive when forecasting ‘tomorrow’ to give relatively greater weight to what has happened in the recent past then in the more distant one. This can be achieved by using an exponentially weighted moving average (EWMA) forecast:  

$$
\sigma_{t+1}^{2}=(1-\lambda)\sum_{i=0}^{\infty}\lambda^{i}R_{t-i}^{2}
$$  

where $R$ is the daily return on the asset (with mean zero), $\lambda$ is a ‘weight’ lying between 0 and 1 (e.g. $\lambda=0.94,$ ). The weights $\lambda^{i}$ decline exponentially, so this forecasting scheme is known as an EWMA model. For example, for $\lambda=0.94$ , the $\lambda^{i}$ weights decline as 0.94, 0.88, 0.83 , . . etc. and squared returns which occur further in the past are given less weight in forecasting tomorrow’s variance. Actually, the above equation can be written in a simpler form:  

$$
\sigma_{t+1}^{2}=\lambda\sigma_{t}^{2}+(1-\lambda)R_{t}^{2}
$$  

Suppose you have 250 daily observations on squared returns $R_{t}^{2}$ . To start the recursive forecast using (44.13b) we might (arbitrarily) take a simple average of the !rst 30 observations on $R_{t}^{2}$ . If we denote this average as $\sigma_{30}^{2}=\dot{\sum_{1}}^{30}R_{k}^{2}/30$ then the forecast can be updated for day-31 using the ‘new’ value for $R_{30}^{2}$ :  

$$
\sigma_{31}^{2}=\lambda\sigma_{30}^{2}+(1-\lambda)R_{30}^{2}
$$  

The forecast $\sigma_{31}^{2}$ can then be updated daily until we get to day-100 after which the future values of %1201, %1202 etc. are independent of the initial value we used for %30. As we have 250 days of historical data then we can continue the recursive forecast up to day-250. As additional information on daily returns becomes available our forecast of the variance (or standard deviation) changes as we move forward through time. It has been found that the EWMA forecasting equation gives better predictions than the SMA (based on the mean squared forecast errors).  

![](bb282311474594fe0d600ca4d58498ff0be7d205e28e8bf1217d2f9eb63a5a90.jpg)  
FIGURE 44.4 EWMA forecast – daily FX returns (Eurodollar)  

The above EWMA formula when applied to daily changes in the spot exchange rate is shown in Figure 44.4 and you can see how the EWMA forecasts move by quite substantial amounts and this will directly in\$uence our changing daily forecasts of the VaR of a portfolio of foreign assets, which depends on the exchange rate.  

Banks and !nancial institutions want to forecast the VaR not only over 1 day but also over other horizons such as a week or a month. However, it would be time consuming to calculate the many volatilities (not to mention correlations) required for these diferent horizons. Changes in weekly volatility are not the same as movements in daily volatility. However, if we assume daily (continuously compounded, log) returns are independent over time (and identically distributed) we can ‘scale them up’ to give a forecast of weekly or monthly volatility by using the ‘root $T$ -rule’ $({\sqrt{T}}-r u l e)$ . For iid returns, the standard deviation over $T$ -days is:  

$$
\sigma_{T}=\sqrt{T}\sigma
$$  

So given our EWMA forecast of tomorrow’s daily standard deviation $\sigma$ we simply scale it up by $\quad{\sqrt{T}}$ – the number of trading days over which we want to calculate the VaR.  

# EXAMPLE 44.3  

√T rule  

You hold a $\$1000$ stock portfolio. Tomorrow’s forecast of daily portfolio volatility, $\sigma=0.02$ $2\%$ per day). What is your forecast for volatility over 25 (business) days and what is your estimate of the VaR over 25 days (at the 5th percentile), if you hold a $\$1000$ portfolio?  

Over 25 trading days (i.e. approximately 1 calendar month), the standard deviation of portfolio returns is $\sigma_{25}=\sqrt{25}\:\bar{\sigma}=5(0.02)\stackrel{.}{=}0.10$ (i.e. $10\%$ over 25 days). The VaR estimate over a 25-day horizon is therefore $\$16.5m$ $5\mathrm{m}\left(=\S100\mathrm{m}\times1.65\times0.10\right)$ .  

Suppose each month has 25 trading days. Over the next 20 consecutive months you expect to lose more than $\$16.5m$ in about one of these months (assuming you do not alter the composition of your current portfolio).  

Forecasts for covariances use a similar EWMA scheme:  

$$
\sigma_{R_{1}R_{2}}(t+1)=(1-\lambda)R_{1t}R_{2t}+\lambda\sigma_{R_{1}R_{2}}(t)
$$  

A forecast for the correlation coe#cient is derived from the separate forecasts for variances and covariances4:  

$$
\rho(R_{1},R_{2})=\sigma_{R_{1}R_{2}}/\sigma_{R_{1}}\sigma_{R_{1}}
$$  

# 44.4 BACKTESTING  

Forecasts of daily standard deviations and correlations for each stock and hence for the daily VaR will change from day to day (even when asset holdings remain unchanged). We want to assess whether our forecasts of daily portfolio-VaR are accurate at the 1st percentile. From the standard normal distribution the 1st percentile ‘cut of’ point is $-2.33$ . The (changing) daily forecast of portfolio VaR at the 1st percentile is therefore $V a R_{p,t+1}=V_{p}(2.33)\sigma_{p,t+1}$ .  

![](b91b7a059d06a26cac8a45e7459ff158c3411b7bc1e8961aaaeb1fea6bcb949d.jpg)  
FIGURE 44.5 Backtesting  

The historical out-turn for the actual daily (overnight) pro!t or loss $\scriptstyle({\mathrm{P/L}})$ on the portfolio is $d V_{p}=\sum_{i=1}^{n}V_{i}R_{i}$ where $R_{i}$ are actual returns on successive days.5  

In F=igure 44.5, the rolling one-day-ahead forecasts $V a R_{p,t+1}$ are the two symmetric solid lines. The actual daily $\mathrm{{P/L}}$ on the portfolio $d V_{p}$ (assuming positions in the various assets are unchanged) are the ‘stars’. The actual $\mathrm{{P/L}}$ !gures re\$ect the pro!t/loss that would have occurred if the initial $\$1$ -position in each asset had been held over successive 24 hour periods over the past $n=600$ days (say). The actual $\mathrm{{P/L}}$ does not re\$ect any position changes due to intraday trading.  

If the forecasts of $V a R_{p,t+1}$ (at the 1st percentile) are adequate then we should observe about 1 out of 100 ‘stars’ above the upper forecast-VaR solid line (and about 1 out of 100 below the lower solid line). If there are more than $1\%$ of the ‘stars’ outside either of these lines, then our forecasts for $\sigma_{i}$ and $\rho_{i,j}$ and hence for the portfolio- $\cdot V a R_{p,t+1}$ , are an underestimate of the true portfolio risk. This procedure is known as backtesting.  

In the hypothetical example in Figure 44.5 the actual losses over $n=600$ days, exceed the forecast- $V a R_{p,t+1}$ about 9 times out of 600 daily observations, when for an accurate VaR model we expect on average about 6 $(=1\%$ of 600 outliers. Hence the VaR-forecast slightly overstates the potential losses, at the 1st percentile. If a !nancial regulator (e.g. Bank of England in the UK and the Fed in the USA) found many more than 9 out of 100 ‘exceedances’ (or ‘outliers’) then it might require a bank to hold more capital because of the poor performance of its risk model.  

Example 44.4 tests whether the observed number of ‘outliers’ $X=9$ is consistent with the assumption of normally distributed returns and accurate forecasts of volatilities and correlations that lie behind the VaR forecasts.  

# EXAMPLE 44.4  

# Backtesting  

Percentile chosen for VaR outliers: $p=0.01\left(1\%\right)$   
Number (#) of days used (sample): $n=600$   
Actual number (#) of outlier losses: $X=9$ the 1 percentile   
Expected # of outliers from VaR forecast: $E X=n p=6$   
Stdv of # of outliers (for sample size $n$ ): std $\operatorname{\!\nu}(X)={\sqrt{n p(1-p)}}=2.44$  

# Exact test using the binomial distribution (Excel)  

Probability of !nding 9 or more ‘outliers’ (if the VaR model is correct)  

‘TRUE’ in Excel gives the cumulative probability of between 0 and 8 outliers. So !nding 9 (instead of the expected 6 outliers) could occur by chance with a reasonably high probability of $15.2\%$ , even if your VaR model is ‘correct/good’.  

# Using the normal approximation to the binomial distribution6  

Using the normal distribution for our test, we can be $95\%$ con!dent’ that our VaR forecasts are ‘statistically acceptable’ if the number of outlier losses $X$ is less than $6+(1.65)$ $2.44=10$ (where 1.65 is the one-tail critical value for the $N(0,1)$ distribution at the 5th percentile). Hence, the observed number of outliers $X=9$ lies within the acceptable statistical error band of 10 outliers which could occur just due to chance.  

More formally, at $5\%$ ‘statistical signi!cance level’ we do not reject the null hypotheses that our VaR forecasts are acceptable. Repeating the above using the $z$ -statistic, $z=(9-6)/2.44=1.23<1.65$ critical value for a one-tail test at $5\%$ signi!cance level.  

The $\mathbf{\dot{\rho}}_{p}$ -value’ for $z=1.23$ is $18.6\%$ – this is the probability of observing 9 or more outliers, when the VaR model is correct (i.e. when the expected number of outliers $E X=6$ ). We therefore do not reject the null hypothesis that our VaR model is ‘accurate’ (when predicting VaR losses at the 1st percentile level).  

There are also ‘runs tests’ which check for independence in the VaR forecast outliers. If returns are independent over time as assumed in our VaR approach then any ‘outliers’ should appear in a random order over time. Put another way, we do not expect to see ‘bunching’ of outliers – that is, we should not observe !ve ‘outliers’, say, occurring in one speci!c week.  

# 44.5 CAPITAL ADEQUACY  

Financial !rms (e.g. banks, mutual funds) hold positions in marketable assets and are therefore prone to losses. Prudential considerations imply that ‘capital’ (i.e. broadly speaking, the value of bank equity (stocks) held by investors in a bank plus cumulative retained pro!ts) should be held as a ‘cushion’ against potential losses, otherwise the bank may become insolvent. The European Union, the Basel Committee (on Banking Supervision at the Bank for International Settlements, BIS) and the Federal Reserve Board (‘The Fed’) in the US have agreed that capital held by banks should re\$ect their market (and other) risks.  

# 44.5.1 Basel Approach  

The Basel ‘capital charge’ for market risk is based on the VaR of the bank’s (market) portfolio: the higher the forecast portfolio VaR, the higher is the amount of capital it has to hold to meet regulatory requirements (see Finance Blog 44.1). But how high? This is determined by speci!c rules negotiated via the BIS, but with some discretion by the home regulator (e.g. in the UK this is the Financial Policy Committee [FPC], which is part of the Bank of England and this function is often part of a country’s Central Bank responsibility).  

# Finance Blog 44.1 Bank Regulation for Market Risk  

Broadly speaking the Basel rules have a minimum capital charge based on the VaR over a 10-day horizon and measured at the 1st percentile (rather than the 5th percentile). The 10-day VaR is calculated using the root- $T$ rule applied to the forecast of daily portfolio volatility $\sigma_{p}$ :  

$$
B a s e l\colon R e g u l a t o r y V a R=k V_{p}2.33(\sqrt{10}\sigma_{p})
$$  

where the ‘multiplier’ $k$ is chosen on a bank-by-bank basis with a minimum value of 3. The Basel-VaR determines the minimum capital that must be held by the bank against its ‘market risks’ (and there is also an adjustment for certain ‘speci!c risks’). If the bank’s VaR model looks a bit ‘suspect’ (i.e. when backtesting reveals many more outlier losses than predicted by the VaR forecasts, at the 1st percentile), then the ‘home regulator’ may increase a bank’s capital requirement above this minimum level (i.e. increase $k>3$ ). There is also a requirement to undertake a stressed-VaR. This involves the !nancial institution taking its current portfolio and calculating the losses that would have occurred, had this portfolio been held (unchanged) over a chosen past adverse historical period.  

Regulators also operate a green, yellow, and red, ‘tra#c lights’ approach with more severe penalties, the worse the performance of a bank’s VaR model when backtested. There is also more attention paid to a measure of risk known as ‘expected shortfall’, which is the (dollar) amount you expect to lose on average, given that your losses are greater than your VaR forecast. The !gure for the expected shortfall is therefore greater than the !gure for the VaR amount.  

# 44.6 SUMMARY  

• If the daily VaR for a portfolio of stocks is $\$100$ , at a $95\%$ con!dence level (5th percentile) then you expect to lose no more than $\$100$ in 5 out of the next 100 days and therefore you expect to lose more than $\$100$ , on 5 days out of the next 100 days – assuming you hold an unchanged portfolio of stocks over the period.   
• The (dollar) VaR for a stock portfolio is easily calculated using the variance-covariance method (VCV). The VCV approach assumes that each observed (daily) stock return is drawn independently from an identical distribution (i.e. same mean return and volatility) the return is normally distributed – in short, daily stock returns are assumed to be niid. In addition, daily returns across diferent stocks may be correlated – so returns are multivariate normal.   
• Forecasts of variances and covariances (correlations) of returns are often generated using the EWMA method.   
• The $\sqrt{T}$ -rule is often used for ‘scaling up’ daily volatility forecasts, in order to forecast VaR over longer horizons of up to 1 month (25 trading days) – this requires an assumption that daily returns are identically and independently distributed over time (but does not require that they are normally distributed).   
• Regulators check the accuracy of a bank’s forecasts of portfolio-VaR by backtesting and set higher capital requirements when (a) the VaR forecast is high or (b) backtesting shows that the VaR forecasting model used is inaccurate.  

# EXERCISES  

# Question 1  

Intuitively, why might you give more weight to recent movements in stock returns when forecasting tomorrow’s volatility?  

# Question 2  

Explain how you would assess whether your daily volatility forecasts for an individual stock return are accurate.  

# Question 3  

A US investor holds $\$100$ of AT&T shares and has short-sold $\$50$ of Apple shares. Daily volatility of AT&T, $\sigma_{1}=1.5\%$ and daily volatility of Apple, $\sigma_{2}=1.0\%$ . The correlation between AT&T returns and Apple returns is $-0.1$ . What is the $\$1$ -VaR for this portfolio? What is the worst-case VaR?  

# Question 4  

You have a portfolio consisting of £10,000 in each of 3 assets, 1, 2, and 3. You have calculated the daily standard deviations to be $5.418\%$ , $3.0424\%$ , $3.6363\%$ , respectively. The correlation between returns on asset-1 and asset-2 is 0.962, between asset-1 and asset-3 is 0.403, and between asset-2 and asset-3 is 0.610.  

(a) What is the VaR for this portfolio?   
(b) What is the worse-case VaR?   
(c) What is the VaR if £10,000 of asset-2 is short-sold? Explain this result compared with the outcomes in (a) and (b).  

# Question 5  

Your forecast of daily volatility, $\sigma=0.01$ $1\%$ per day). How might you forecast volatility over 25 (business) days? What assumptions are you making?  

# Question 6  

Explain the step used in ‘backtesting’ forecasts of daily VaR at the 5th percentile. Assume you have $\$100$ in each of two stocks and you have past daily data from 1 to $T$ .  

# Question 7  

Suppose the regulator for banks uses the 1st percentile to assess the VaR of a portfolio. What do you think the regulator would do if after backtesting the risk management system in your investment bank, found that actual losses exceeded your forecast-VaR losses 10 times in 175 forecasts?  