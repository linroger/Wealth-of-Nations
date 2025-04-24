---
tags:
  - domestic_equity
  - portfolio_risk
  - single_index_model
  - var_calculation
  - vcv_method
aliases:
  - SIM
  - Value at Risk
key_concepts:
  - Coupon bond as zero-coupon
  - Portfolio of foreign stocks
  - Reduce VaR computations
  - Single index model (SIM)
  - VaR for portfolio of options
---
# VaR: Other Portfolios  

# Aims  

• To show how we can reduce the number of computations required to calculate VaR, while still retaining the linearity assumption and hence allowing the use of the variance-covariance (VCV) method.   
• To show how the single index model (SIM) is used to simplify the calculation of the VaR for a portfolio containing a large number of stocks.   
• To demonstrate how a portfolio of foreign stocks can be viewed as equivalent to holding the foreign market index and the foreign currency. This allows calculation of VaR in the domestic currency, using the VCV method.   
• To show how representing a coupon paying bond as a series of zero-coupon bonds allows calculation of the VaR using the VCV method, for portfolios containing many bonds with diferent cash fows and durations.   
• To show how the VCV method can be used to calculate the (approximate) VaR for a portfolio of options.  

# 45.1 SINGLE INDEX MODEL  

We use the single index model (SIM) to show how the volatility of a well-diversifed portfolio of stocks can be measured by the volatility of the market return (e.g. the S&P 500) and the portfolio beta. This substantially reduces the computational burden when calculating VaR because the large number of correlations between individual stock returns can be encapsulated in the portfolio beta, and therefore do not have to be estimated. But it must be remembered that the SIM requires several simplifying assumptions – most notably that specifc random events that afect stock returns for one company are uncorrelated with random events which afect stock returns of another company.  

# 45.1.1 Domestic Equity: SIM  

Consider a portfolio consisting of $n$ -stocks held in a specifc country (e.g. USA). Forecasting the n variances and particularly the $n(n-1)/2$ correlations (covariances) across all stocks is computationally extremely burdensome, particularly for the covariance terms as there are so many of them. To ease the computational burden, we use the SIM since this allows all of the variances and covariances between returns to be subsumed into the $n$ -asset betas (and a forecast for the variance of the market return). The SIM is:  

$$
R_{i}=\alpha_{i}+\beta_{i}R_{m}+\varepsilon_{i}
$$  

where $R_{i}$ is the return on stock- $i$ , $\boldsymbol{R_{m}}$ is the market return, $\beta_{i}$ is the beta of stock-i. The $\varepsilon_{i}$ are (usually) assumed to be niid and in addition we make the crucial assumption that there is no contemporaneous correlation across the random error terms for diferent stocks (at time $t_{-}$ ), $E(\varepsilon_{i}\varepsilon_{j})=0$ . Hence, we assume that frm ‘specifc risk’ (e.g. due to patent applications, IT failures, strikes, reputational efects, etc.) are uncorrelated across diferent frms. (Also, $\boldsymbol{R_{m}}$ is independent of $\varepsilon_{i}$ .) An estimate of $\beta_{i}$ can be obtained either from a ‘risk measurement service’ (e.g. investment bank) or by running a time series regression of $R_{i}$ on $\boldsymbol{R_{m}}$ (using say one year of daily returns data). Using (45.1) the return on a portfolio of $n$ -stocks can be represented as:  

$$
R_{p}=\sum_{i=1}^{n}w_{i}R_{i}=\alpha_{p}+\beta_{p}R_{m}+\varepsilon_{p}
$$  

where $\alpha_{p}\equiv\sum_{i=1}^{n}w_{i}\alpha_{i},\beta_{p}\equiv\sum_{i=1}^{n}w_{i}\beta_{i},\varepsilon_{p}\equiv\sum_{i=1}^{n}w_{i}\varepsilon_{i}$ and $w_{i}=V_{i}/V_{p}$ is the proportion of total portfolio value held=in each stock=. From Equat=ion(45.2), the portfolio return depends linearly on the market return (given the portfolio beta $\beta_{p})$ ). It is easily shown that if $E(\varepsilon_{i}\varepsilon_{j})=0$ , the variance of the portfolio return is:  

$$
\sigma_{p}^{2}=\beta_{p}^{2}\sigma_{m}^{2}+\sigma^{2}(\varepsilon_{p})
$$  

where $\sigma^{2}(\varepsilon_{p})=\Sigma w_{i}^{2}\sigma^{2}(\varepsilon_{i})$ .  

The specifc risk of each stock $\sigma^{2}(\varepsilon_{i})$ can be ‘diversifed away’ when stocks are held as part of a well-diversifed portfolio (with small amounts held in each stock). Hence the term $\Sigma w_{i}^{2}\sigma^{2}(\varepsilon_{i})$ is small and can be ignored (see Appendix 45.B):  

$$
\sigma_{p}=\beta_{p}\sigma_{m}.
$$  

Thus when using the SIM we only require estimates of $\beta_{i}$ for the $n$ -stocks and a forecast of $\sigma_{m}$ , in order to calculate $\sigma_{p}$ . We therefore dispense with the need to estimate $n$ -values for the standard deviation of individual stock returns $\sigma_{i}$ and more importantly the $n(n-1)/2$ values for the correlation coe\$cients $\rho_{i j}$ between all of the stock returns. This considerably reduces the computational burden of estimating the portfolio-VaR, which is given by:  

$$
V a R_{p}=V_{p}1.65(\beta_{p}\sigma_{m})
$$  

The SIM is a ‘factor model’ with only one factor, the market return $\boldsymbol{R_{m}}$ . However, this approach could be extended within the VaR framework, by assuming several factors afect each stock return. For example, a widely used model is the so-called Fama–French three-factor model, where the return on any stock is determined by the market return $R_{m}$ , the return on small (market cap) stocks minus large (market cap) stocks and the return on high book-to-market minus low book-to-market stocks . Applying the SIM and the Fama–French three-factor model to each of the $n$ -stock returns, implies that the forecast of portfolio variance $\sigma_{p}$ only depends on estimates of the three factor betas, and forecasts of the three variances and six distinct covariances between the ‘three factors’ of the Fama–French model.  

# 45.1.2 Foreign Assets  

How do we deal with exchange rate risk when calculating VaR for a portfolio that contains foreign assets? Suppose a US investor (Mr Trump) holds a $\mathsf{\epsilon}_{\mathrm{i}00\mathrm{m}}$ diversifed portfolio in German stocks which exactly mirror movements in the German stock market index, the DAX. So, Trump’s German stock portfolio has a beta of 1 with respect to the DAX market index. The dollar value of Mr Trump’s German portfolio is subject to changes in the DAX and changes in $s$ , the Dollar-Euro spot FX-rate. In efect Mr Trump holds a two-asset portfolio, the foreign stock itself and the foreign currency. The percentage return on the German portfolio (in USD) is1:  

$$
\mathrm{USD\return}\colon R_{p}=R_{D A X}+R_{S}
$$  

where $R_{S}={}$ return on the spot-exchange rate, that is $R_{S}=d S/S$ . If stocks in the DAX fall at the same time as the euro depreciates against the US dollar, then Mr Trump would lose in USDs on both counts – a ‘double whammy’ of losses on the DAX itself plus losses when euros are converted into dollars. This is because after depreciation of the euro, for every euro that Mr Trump has in the DAX, he obtains fewer dollars.  

Hence a positive correlation between the DAX index and the euro exchange rate increases the riskiness of the US investor’s portfolio, measured in US dollars. Conversely, a negative correlation between the DAX and the euro exchange rate implies a lower dollar risk for Mr Trump’s German stock portfolio.  

To measure the dollar-VaR for a US investor with stocks held in the DAX we have to modify our previous VCV approach. First, because we are interested in the dollar-VaR we have to convert Trump’s initial position in Euros, into USD. If Mr Trump has $\mathsf{\epsilon}_{\mathrm{i}00\mathrm{m}}$ invested in the DAX and the current Dollar-Euro spot FX rate is $S_{0}=1.05$ (USD per Euro), then the initial USD position is $V_{\mathfrak{s}}=S_{0}(\in100\mathrm{m})=\mathfrak{s l}05\mathrm{m}$ . The key equation (see Appendix 45.A) is:  

$$
d V_{\$\mathbb{S}}\approx V_{\mathbb{S}}(R_{D A X}+R_{S})
$$  

It follows directly that the dollar-VaR is then given by the usual formula:  

$$
\mathrm{VaR}_{\mathrm{P}}=\sqrt{\mathrm{ZCZ}^{\prime}}
$$  

where  

$$
Z=[V a R_{D a x},V a R_{s}]=[V_{\mathcal{S}}1.65\sigma_{D A X},V_{\mathcal{S}}1.65\sigma_{S}]
$$  

$V_{\mathcal{S}}=$ the initial $\$8$ -value of the position held in the $(\$105m)$ $\sigma_{D A X}=$ the volatility of the index $\sigma_{S}=$ the volatility of the return on the Dollar-Euro‘spot’exchange rate, $\sigma_{d S/S}$  

The $\mathbf{z}$ -vector ‘contains’ the same $\$1$ -value, $V_{\$105m}$ for both the DAX and the FX position. This is because for a US investor, holding the DAX is equivalent to holding both $V_{\mathbb{S}}$ in the DAX plus $V_{\mathbb{S}}$ in foreign exchange (euros). The correlation matrix C contains the correlation coe\$cient between the return on the DAX and the Euro-dollar spot exchange rate.  

# 45.1.3 German and US Stock Portfolios  

Suppose (as above) a Mr Trump (a US investor) holds a portfolio of German stocks but the beta of the German stocks is $\beta_{p}^{G}\neq1$ and Mr Trump also holds a portfolio of US stocks with $\beta_{p}^{U S}\neq1$ . Assume the US investor holds $V_{\S}^{U S}$ dollars in US stocks and $V_{\S}^{G}$ dollars in German stocks (that is, $V_{\$123}^{G}=S V_{E u r o}^{G}$ , where $V_{E u r o}^{G}$ is the Euro-value of the German stock portfolio and $s$ is the current USD-Euro exchange rate). Assume the SIM holds within any single country, hence:  

$$
\sigma_{G}=\beta_{p}^{G}\sigma_{D A X}\qquad\quad\sigma_{U S}=\beta_{p}^{U S}\sigma_{S\&P}
$$  

where $\sigma_{S\&P}=$ standard deviation of the S&P 500 US stock market index. The change in the dollar value of Mr Trump’s portfolio is (approximately) linear in returns:  

$$
d V_{p}=V_{\S}^{U S}R_{U S}+V_{\S}^{G}(R_{G}+R_{S})
$$  

where $R_{G}={}$ return on German stock portfolio and $R_{S}=d S/S$ , the proportionate change in the spot FX rate. The USD-VaR for this portfolio is:  

$$
\begin{array}{r l}&{\quad V a R_{p}=\sqrt{Z C Z^{\prime}}}\\ &{\qquadZ=[V_{\mathfrak{s}}^{U S}(1.65)\sigma_{U S},~V_{\mathfrak{s}}^{G}(1.65)\sigma_{G},~V_{\mathfrak{s}}^{G}(1.65)\sigma_{S}]}\\ &{\mathrm{~and~}\mathbb{C}=\left[\begin{array}{l l l}{1}&{\rho_{U S,G}}&{\rho_{U S,S}}\\ {\rho_{G,U S}}&{1}&{\rho_{G,S}}\\ {\rho_{S,U S}}&{\rho_{S,G}}&{1}\end{array}\right]}\end{array}
$$  

This approach is easily extended to holding several foreign portfolios where for each foreign stock portfolio there are two entries in the Z vector – the VaR of the foreign stock portfolio and the VaR of the US-foreign currency, FX rate.  

Suppose Mr Trump has a US stock portfolio as well as German and Brazilian stock portfolios (which are unhedged). Then there may still be some risk reduction (and hence a low portfolio VaR) if some of the spot FX rates have low (or negative) correlations with either the US-dollar exchange rate, or with stock market returns in diferent countries. If Mr Trump hedges his spot FX positions (using the forward market) then clearly any spot-FX volatilities and the correlation between spot FX-rates and foreign stock returns do not enter the calculation of VaR. But we cannot say unequivocally whether an unhedged or a FX-hedged ‘world portfolio’ has a lower risk – it depends on the interplay of the correlation coe\$cients in the two scenarios.  

# 45.2 VaR FOR COUPON BONDS  

Changes in bond prices and yields are not linearly related but we can use duration to give an approximate linear relationship. This then allows us to apply the variance-covariance approach to measure the VaR of a portfolio of coupon paying bonds. The easiest way to incorporate coupon paying bonds into the VCV approach is to note that for a portfolio of coupon paying bonds:  

$$
\begin{array}{c c c}{{d V_{p}\approx-(V_{p}D_{p})d y}}&{{\mathrm{hence}}}&{{\sigma(d V_{p})\approx V_{p}D_{p}\sigma(d y)}}\\ {{}}&{{}}&{{}}\\ {{V a R_{p}=1.65\sigma(d V_{p})=V_{p}D_{p}(1.65)\sigma(d y)}}&{{}}\end{array}
$$  

where $D_{p}=\sum_{i=1}^{n}(V_{i}/V_{p})D_{i}$ is the portfolio duration, $V_{i}=$ dollar amount in each bond and $V_{p}=$ total dol=lar amount in the portfolio of bonds, $y=$ yield to maturity. One problem with the above approach is that it assumes parallel shifts in the yield curve – that is, all spot yields move by the same absolute amount – which is encapsulated in the change in the (single) yield (to maturity) $d y$ . Also the duration-approximation is not accurate for large changes in yields.  

# 45.2.1 VaR: Non-parallel Shifts in the Yield Curve  

Can we improve on this approach and calculate the VaR for a portfolio of coupon paying bonds when there are non-parallel shifts in the yield curve? The way to do this is to consider a single coupon paying bond, with $n$ -years to maturity, as a series of zero-coupon bonds. (This is extended to a portfolio of coupon paying bonds, below.) For a zero-coupon bond which has single cash fow ${C F}_{i}$ at $t_{i}$ , the current value (price) is:  

$$
V_{i}=C F_{i}~e^{-y_{i}t_{i}}
$$  

$y_{i}=$ (continuously compounded) spot yield for period $t_{i}$ . The proportionate change in value (price) of the zero-coupon bond is the ‘return’ on the bond, that is $R_{i}=d V_{i}/V_{i}$ . Diferentiating (45.11) we have a linear relationship between the return on the zero-coupon bond and the (absolute) change in yield:  

$$
R_{i}\equiv d V_{i}/V_{i}=-t_{i}d y_{i}=-D_{i}d y_{i}
$$  

where for a zero-coupon bond $D_{i}=t_{i}$ (i.e. a zero-coupon bond’s duration equals its maturity – measured in years). From (45.12):  

$$
\sigma_{R_{i}}=D_{i}\sigma_{d y_{i}}
$$  

A coupon paying bond is just a series of zero-coupon bonds and the value/price of a coupon bond with $n$ -cash fows ${C F}_{i}$ at time $t_{i}$ is2:  

$$
V_{p}=\sum_{i=1}^{n}V_{i}
$$  

Hence:  

$$
d{\boldsymbol{V}}_{p}=\sum_{i=1}^{n}d{\boldsymbol{V}}_{i}=\sum_{i=1}^{n}V_{i}(d V_{i}/V_{i})=\sum_{i=1}^{n}V_{i}R_{i}.
$$  

The dollar change in value of the coupon paying bond is (approximately) linear in the returns $R_{i}$ of its constituent zero-coupon bonds (for small changes in yields). We have ‘mapped’  

the non-linear ‘yield-bond price relationship’ into an (approximate) linear framework. In addition, if we assume yield changes $d y_{i}$ are normally distributed, we can use Equation $(45.14)^{3}$ to calculate the VaR (at the 5th percentile) for a coupon paying bond:  

$$
V a R_{p}=1.65\sigma_{d V_{p}}=\sqrt{Z c z^{\prime}}
$$  

where $Z=\{V a R_{1},V a R_{2},...,V a R_{n}\},V a R_{i}=V_{i}(1.65)\sigma_{R_{i}}$ and $c$ is the $(n\times n)$ correlation matrix of zero-coupon bond returns.  

In general we do not forecast the volatility of bond returns $\sigma_{R_{i}}$ directly, but instead forecast $\sigma_{d y_{i}}$ using the EWMA model. Then $\sigma_{{\boldsymbol{R}}_{i}}=t_{i}\sigma_{d y_{i}}$ provides a forecast of the standard deviation of (zero-coupon) bond returns for use in Equation (45.15). Similarly, we use the EWMA model to forecast the covariance $\sigma(d y_{i},d y_{j})$ between changes in spot yields from which we obtain the correlation coe\$cients (for use in the correlation matrix $C$ ):  

$$
\rho_{i,j}\equiv\rho(R_{i},~R_{j})=\sigma(d y_{i},d y_{j})/(\sigma(d y_{i}).\sigma(d y_{j}))
$$  

All of the above equations can be applied to a portfolio consisting of m coupon paying bonds. The cash fows from the m-bonds at each time period $t_{i}$ are aggregated to give the total coupon payments at this date, $C F_{i,T o t a l}=\sum_{j=1}^{m}C F_{i,j},$ . The current value of these coupons from all the bonds is then $V_{i,T o t a l}=C F_{i,T o t a l}~e^{-y_{i}t_{i}}$ and the analysis follows as above.  

# EXAMPLE 45.1  

# VaR of Bond Portfolio  

Total cash fows (coupons and any repayment of principal) from a portfolio of bonds are $\$10,000$ and $\$20,000$ at $t_{5}=5$ years and $t_{7}=7$ years, respectively. Hence the duration of these two cash fows are $D_{5}=5$ and $D_{7}=7$ . The current 5-year and 7-year spot yields (continuously compounded) are $y_{5}=3\%$ and $y_{7}=4\%$ , respectively.  

The daily standard deviation of the change in yields are $0.1\%$ per day and $0.2\%$ per day (respectively) and the correlation coe\$cient is $\rho=0.95$ . We want to calculate the 5-day VaR (at the 5th percentile). The value/price of the two zero-coupon bonds are:  

$$
V_{5}\equiv C F_{5}e^{-y_{5}t_{5}}=\S8,607.1\qquadV_{7}\equiv C F_{7}e^{-y_{7}t_{7}}=\S15,115.7
$$  

The standard deviation of the return on each zero-coupon bond and the individual VaRs are:  

$$
\begin{array}{l l l}{{\sigma_{R_{5}}}}&{{=D_{5}\sigma_{d y_{5}}=0.5\%,}}&{{\sigma_{R_{7}}\ =D_{7}\sigma_{d y}}}\\ {{V a R_{5}}}&{{=\S8607.1\left(1.65\right)5\left(0.001\right)=\S71}}\\ {{V a R_{7}}}&{{=\S15,115.7(1.65)7\left(0.002\right)=\S349.2}}\end{array}
$$  

(continued)  

(continued)  

The daily VaR for the bond portfolio is:  

$$
\begin{array}{r l r}&{}&{V a R_{p}=\left[V a R_{5}^{2}+V a R_{7}^{2}+2\rho V a R_{5}V a R_{7}\right]^{1}/2}\\ &{}&{=\left[(71)^{2}+(349.2)^{2}+2(0.95)\left(71\right)\left(349.2\right)\right]^{1/2}=417.2}\end{array}
$$  

In matrix notation $\pmb{Z}=[V a R_{5},V a R_{7}]$ , $c=2\times2$ correlation matrix, with $\rho=0.95$ and $V a R_{p}=\sqrt{Z c z^{'}}$ .  

# 45.2.2 Mapping Cash Flows  

A large investment bank may have coupon receipts on its bond portfolio virtually every week for the next 20–30 years. We cannot use current spot yields for every horizon $t_{i}$ over the next 30 years – there would be too many cash fows to deal with. To reduce the scale of the problem ‘standard vertices’ of say 1, 3, 6, and 12 months and 2, 3, 4, 5, 7, 9, 10, 15, 20, and 30 years, are used. All cash fows are ‘mapped’ onto these standard vertices and bond return volatilities $\sigma_{i}$ and correlations $\rho_{i,j}$ are provided only for these chosen vertices.  

For example, suppose an actual cash fow of $\$1000$ at $t=6$ (Figure 45.1) has to be apportioned between the standard vertices at $t=5$ and $t=7$ . One approach (see Appendix 45.C) is to allocate cash fows to adjacent standard vertices to ensure that:  

• Total market value of the cash fows allocated to adjacent vertices (e.g. 5 and 7 years) equals the market value of the original cash fow (i.e. $\$1000$ at $t=6$ years). • The two cash fows at $t=5$ and $t=7$ both have the same sign as the original cash fow. • The volatility of (present) value of the two cash fows at $t=5$ and $t=7$ equal the volatility of the (present) value of the original cash fow at $t=6$ .  

![](f1ff8409cacb53172830acf8d772563ffae9b85373db3bd9ab0cbcff49f71736.jpg)  
FIGURE 45.1 Mapping cash fows  

# 45.2.3 Swaps  

A pay-fxed, receive-foating interest rate swap is equivalent to a short position in a fxed rate bond and a long position in a FRN. The VaR for the fxed leg can therefore be analysed as a standard coupon paying bond. The value of the foating leg can be treated as a zero-coupon bond with a single known payment at the next payment date, discounted by the time to the next payment. Hence the VaR of the foating leg can also be calculated using the cash-fow mapping approach.  

# 45.2.4 Principal Components Analysis  

A useful alternative way of parsimoniously representing changes in say $k$ diferent spot yields is to use principal components analysis (PCA). PCA ‘represents’ the changes in all the $k$ spot yields by a few (usually about three) new variables called principal components (PCs).4 When computing the VaR of a bond portfolio we then use these three principal components, in place of the many $(=k(k-1)/2)$ correlations between the original $k$ spot yields.  

PCA is a statistical technique which takes a $(T\times k)$ matrix of changes in $k$ -spot yields $\mathbf{X}$ , and seeks to ‘explain’ the movement in all these yields using just the three principal components, ${\bf q}_{i}(i=1,2,3)$ . The q’s are linear combinations (i.e. weighted averages) of the ‘raw’ spot rate data in the $\mathbf{X}$ -matrix:  

$$
\mathbf{q}_{i}=\mathbf{X}\mathbf{c}_{i}\qquad(i=1,2,3)
$$  

where $\mathbf{c}_{i}$ is an estimated constant. (It is in fact the eigenvalue corresponding to the largest eigenvector of the $(\mathbf{X}^{'}\mathbf{X})$ matrix.) A major beneft of PCA is that the q’s are orthogonal (uncorrelated) with each other and hence their correlation coe\$cients are zero (by construction).  

It is generally found that about $95\%$ of the variation in, say, 15 spot yields (e.g. for years 1, 2, 3, . . . 15) can be ‘empirically explained’ by about three PCs. The frst PC is interpreted as representing parallel shifts in the yield curve, the second represents a twist in the yield curve, whereas the third (which explains the smallest proportion of the variation in the yield data) represents a ‘bowing’ in the yield curve (which occurs relatively infrequently). What is important for our VaR calculation is that the volatility of these 15 spot yields can be ‘linearly mapped’ into only three variables – the three PCs, ${\bf q}_{i}$ . The three PCs are uncorrelated with each other and this considerably reduces the dimensionality of the VaR calculations.  

# 45.3 VaR: OPTIONS  

The VaR for options can be dealt with in the VCV framework if we are willing to use the linear approximation given by the option’s delta. The change in value of a portfolio of call and put  

options on a specifc stock (e.g. AT&T) but with diferent strikes and time to maturity, is given by the portfolio delta:  

$$
d V_{p,1}=\sum_{i=1}^{n}N_{i}(d f_{i})=\sum_{i=1}^{n}N_{i}\Delta_{i}(d S)=\Delta_{p,1}d S_{1}
$$  

where $d f_{i}$ is the change in the price of the call or put options (on AT&T stock). If the options on AT&T all have the same delta $\Delta$ (i.e. same strike price and time to maturity) and there are $N_{o p}$ options held, then the portfolio delta simplifes to $\Delta_{p,1}=N_{o p}\Delta$ .  

Now suppose we have options on two diferent stocks (Microsoft and AT&T) then:  

$$
d V_{p}=\Delta_{p1}S_{1}(d S_{1}/S_{1})+\Delta_{p2}S_{2}(d S_{2}/S_{2})=k_{1}R_{1}+k_{2}R_{2}
$$  

The change in value of the options portfolio is (approximately) linear in the two stock returns and hence we can apply the standard VCV approach as in the following example.  

# EXAMPLE 45.2  

# VaR for Options Portfolio  

You hold 2,500 call options on Microsoft with $\Delta=0.4$ and 10,000 call options on AT&T with $\Delta=0.2$ giving portfolio deltas, $\Delta_{1}=2,500(0.4)=1,000$ and $\Delta_{2}=10,000(0.2)=2,000$ . The current stock prices are $S_{1}=110$ , $S_{2}=40$ with daily standard deviations $\sigma_{1}=2\%$ and $\sigma_{2}=1\%$ and correlation coe\$cient $\rho=0.3$ .  

What is the 5-day VaR (at the 5th percentile) using the delta approximation? From Equation (45.18):  

$$
\begin{array}{l}{{d V_{p}=1000(110)R_{1}+2000(40)R_{2}}}\\ {{d V_{p}=110R_{1}+80R_{2}=V_{1}R_{1}+V_{2}R_{2}}}\end{array}
$$  

where $d V_{p}$ is measured in thousands of dollars, hence:  

$$
\begin{array}{r l}&{V a R_{1}=V_{1}(1.65)\sigma_{1}=3.63\quad\mathrm{and}\quad V a R_{2}=V_{2}(1.65)\sigma_{2}=1.32}\\ &{\qquad\mathbf{Z}=[V a R_{1},V a R_{2}]=[3.63,1.32]}\end{array}
$$  

$$
\begin{array}{r l r}&{}&{{V a R}_{p}=\sqrt{Z C Z^{\prime}}=\left[{V a R}_{1}^{2}+{V a R}_{2}^{2}+2\rho{V a R}_{1}{V a R}_{2}\right]^{1}/2}\\ &{}&{=\left[(3.63)^{2}+(1.32)^{2}+2\left(0.3\right)3.63\left(1.32\right)\right]^{1/2}=4.2183}\end{array}
$$  

The 5-day VaR (at the 5th percentile) is therefore:  

$$
V a R_{p}=\sqrt{5}(4.2183)=9.4324~(\S9,432.4)
$$  

Options prices are actually non-linear functions of the underlying asset (e.g. stock price). Hence, if changes in the stock prices are large, the delta approximation and VCV approach may provide a very poor measure of VaR for options portfolios. Superior techniques such as MCS and historical simulation are therefore the usual methods used to calculate VaR for portfolios containing options (see Chapter 46).  

# 45.4 SUMMARY  

• When using the VCV method, for a well-diversifed stock portfolio containing n-stocks, use of the SIM simplifes the calculation. This is because the $n$ -variances and $n(n-1)/2$ correlations between the stock returns can be represented by the $n$ -betas (that make up the portfolio beta) and the volatility of the market return. Therefore $\sigma_{p}=\beta_{p}\sigma_{m}$ and $V a R_{p}=V_{p}\beta_{p}(1.65)\sigma_{m}$ .   
• When a domestic investor holds a portfolio of foreign stocks she essentially holds a two-asset portfolio, the foreign stock portfolio and an equal amount in the foreign currency. The VCV approach can then be used to calculate the VaR.   
• If we are willing to assume parallel shifts in the yield curve, the VaR of a portfolio of coupon-paying bonds can be reduced to the simple formula: $V a R_{p}=V_{p}D_{p}(1.65)\sigma(d y)$ .   
• For non-parallel shifts in the yield curve we can still apply the VCV approach to obtain the VaR for a portfolio of coupon-paying bonds (with $n$ -cash fows). We model the coupon paying bonds as a set of zero-coupon bonds. The duration approximation allows the return on these zero-coupon bonds to be expressed as a linear function of changes in all of the spot yields. The VaR of the bond portfolio then depends on the volatility and correlations between all the spot yields at various maturities.   
• In a large bond portfolio, coupon payments occur at many diferent time periods. To keep the VCV method tractable we have to ‘map’ these cash fows onto a smaller number of ‘standard’ time periods and calculate the VaR using only these standard time periods.   
• The VaR for a portfolio of options can be analysed in the VCV framework using the options portfolio deltas. But this may be a poor approximation to the true VaR if the change in the underlying asset prices are large. This is because the true options prices are non-linear functions of the underlying asset prices and the delta approximation is only accurate for small changes in the underlying asset price.  

# APPENDIX 45.A: VaR FOR FOREIGN ASSETS  

A US investor holds VG Euros in German stocks, which in USD is $V_{\$3}^{G}=S_{0}V_{E u r o}^{G}$ , where $S_{0}$ is the current Euro-USD spot exchange rate. The USD change in value of this portfolio is:  

$$
d V\equiv V_{1}-V_{0}=V_{E u r o}^{G}(1+R_{G})S_{1}-V_{E u r o}^{G}S_{0}
$$  

Let $R_{S}=(S_{1}/S_{0})-1$ be the (proportionate) change in the spot exchange rate (i.e. the return on foreign exchange). Substituting $S_{1}=(1+R_{S})S_{0}$ and rearranging:  

$$
\begin{array}{l}{{d V=V_{E u r o}^{G}(1+R_{G})(1+R_{S})S_{0}-V_{E u r o}^{G}S_{0}=V_{\P}^{G}[(1+R_{G})(1+R_{S})-1]}}\\ {{d V\approx V_{\P}^{G}(R_{G}+R_{S})}}\end{array}
$$  

where we have ignored the cross product terms, which are small. In (45.A.2b) we see that the USD investor is efectively holding equal dollar amounts $V_{\$123,456,789}^{G}$ in German stocks and in the Euro-USD exchange rate. Hence it follows directly from (45.A.2):  

$$
\sigma_{d V}=V_{\$6}^{G}\sqrt{(\sigma_{G}^{2}+\sigma_{S}^{2}+2\rho_{G,S}\sigma_{G}\sigma_{S})}
$$  

Therefore the USD-VaR for the US investor who holds the German portfolio is:  

$$
\begin{array}{r l}&{V a R_{p}(U S D)=1.65\sigma_{d V}=V_{\mathrm{{g}}}^{G}1.65~\sqrt{(\sigma_{G}^{2}+\sigma_{S}^{2}+2\rho_{G,S}\sigma_{G}\sigma_{S})}}\\ &{V a R_{p}=\sqrt{Z C Z^{\prime}}}\\ &{Z=[V_{\mathrm{{g}}}^{G}(1.65)\sigma_{G},~V_{\mathrm{{g}}}^{G}(1.65)\sigma_{S}]\quad\mathrm{and}\quad\mathbb{C}=\left[\begin{array}{c c}{1}&{\rho_{G,S}}\\ {\rho_{G,S}}&{1}\end{array}\right]}\end{array}
$$  

In addition, if we use the SIM then $\sigma_{G}=\beta_{G}\sigma_{D a x}$ where $\beta_{G}$ is the portfolio-beta of the German stock portfolio and $\sigma_{D a x}$ is the volatility of the German stock market index, the DAX.  

# APPENDIX 45.B: SINGLE INDEX MODEL (SIM)  

Using the single index model (SIM) we show that the standard deviation of a portfolio of $n$ -stocks is:  

$$
\sigma_{p}=\left[\sum_{i=1}^{n}w_{i}\beta_{i}\right]\sigma_{m}=\beta_{p}\sigma_{m}
$$  

where $\sigma_{p}=$ portfolio standard deviation, $\sigma_{m}=$ standard deviation of the market portfolio and $\begin{array}{r}{\beta_{p}=\sum_{i}\dot{w}_{i}\beta_{i}}\end{array}$ is the ‘beta’ of the stock portfolio. The SIM for each stock return is:  

$$
R_{i}=\alpha_{i}+\beta_{i}R_{m}+\varepsilon_{i}
$$  

Assumptions:  

$$
\begin{array}{l}{E(\varepsilon_{i})=0}\\ {E(\varepsilon_{i}^{2})=\sigma^{2}(\varepsilon_{i}),}\\ {E(\varepsilon_{i}\varepsilon_{j})=0\mathrm{for}\{\mathrm{i}\neq\mathrm{j}\}}\\ {\mathrm{cov}(R_{m},\varepsilon_{i})=0}\end{array}
$$  

It follows that :  

$$
\begin{array}{r l}&{E R_{i}=\alpha_{i}+\beta_{i}E R_{m}}\\ &{\sigma_{i}^{2}=\beta_{i}^{2}\sigma_{m}^{2}+\sigma^{2}(\varepsilon_{i})}\\ &{\sigma_{i j}=\beta_{i}\beta_{j}\sigma_{m}^{2}+E(\varepsilon_{i}\varepsilon_{j})=\beta_{i}\beta_{j}\sigma_{m}^{2}\quad\mathrm{~since~}\quad E(\varepsilon_{i}\varepsilon_{j})=0\mathrm{~for~}i\neq j}\end{array}
$$  

The portfolio return and variance are:  

$$
\begin{array}{l}{{\displaystyle R_{p}=\sum_{i}w_{i}R_{i}\quad\mathrm{~where~}\quad w_{i}=V_{i}/V_{p}\quad\mathrm{~and~}\quad V_{p}=\sum_{i=1}^{n}V_{i}}}\\ {{\displaystyle\sigma_{p}^{2}=\sum_{i}w_{i}^{2}\sigma_{i}^{2}+\sum_{i\neq j}\sum_{m_{i}}w_{j}\sigma_{i,j}}}\end{array}
$$  

The formula for portfolio variance requires $n$ -variances and $n(n-1)/2$ covariances. For example for $n=150$ this amounts to 11,325, inputs to estimate. To reduce the number of inputs required we utilize the SIM. Substituting from Equation (45.B.2) in (45.B.5a):  

$$
\begin{array}{l}{{\displaystyle R_{p}=\sum_{i}w_{i}R_{i}=\sum_{i}(w_{i}\alpha_{i}+w_{i}\beta_{i}R_{m}+w_{i}\varepsilon_{i})=\alpha_{p}+\beta_{p}R_{m}+\varepsilon_{p}}}\\ {{\displaystyle\alpha_{p}=\sum_{i}w_{i}\alpha_{i},\quad\beta_{p}=\sum_{i}w_{i}\beta_{i},\mathrm{and}\varepsilon_{p}=\sum_{i}w_{i}\varepsilon_{i}.}}\\ {{\displaystyle\sigma_{p}^{2}=\beta_{p}^{2}\sigma_{m}^{2}+\sigma^{2}(\varepsilon_{p})}}\end{array}
$$  

Equation (45.B.7) may be interpreted as, ‘Total Portfolio $\operatorname{Risk}=\mathbf{M}$ arket Risk $+$ Specifc Risk’. Examining the specifc risk term more closely and assuming $w_{i}=1/n$ , that is an equally weighted (i.e. well diversifed) portfolio:  

$$
\sigma^{2}(\varepsilon_{p})=\sum_{i}w_{i}^{2}\sigma^{2}(\varepsilon_{i})+\sum_{i\neq j}\sum w_{i}w_{j}E(\varepsilon_{i}\varepsilon_{j})=\sum_{i}w_{i}^{2}\sigma^{2}(\varepsilon_{i})=(1/n)\overline{{\sigma}}^{2}(\varepsilon_{i})
$$  

where we have used the key assumption of the SIM namely, $E(\varepsilon_{i}\varepsilon_{j})=0$ . The average specifc risk is defned as $\overline{{\sigma}}^{2}(\varepsilon_{i})\equiv(1/n){\sum_{i}}\sigma^{2}(\varepsilon_{i})$ and as $n\rightarrow\infty$ this term goes to zero ( $\mathrm{.}n=35$ randomly selected stocks is usually su\$cient to ensure this last term is relatively small). Hence under the SIM and assuming a well-diversifed portfolio:  

$$
\sigma_{p}=\left[\sum_{i=1}^{n}w_{i}\beta_{i}\right]\sigma_{m}=\beta_{p}\sigma_{m}
$$  

A crucial assumption in the SIM is $E(\varepsilon_{i}\varepsilon_{j})=0$ – the covariance of frm specifc ‘random shocks’ to stock- $i$ and stock- $\cdot j$ are contemporaneously uncorrelated, across all stocks. This is reasonable for stocks in diferent sectors (e.g. oil and IT) but not for stocks in the same sector (e.g. Shell and BP). However, in a well-diversifed portfolio even though there may be some small positive correlations between some $\varepsilon_{i}$ and $\varepsilon_{j}$ for daily returns, nevertheless portfolio specifc risk still falls quite rapidly as $n$ increases and it is small relative to market (beta) risk. To see this note that from (45.B.8) that if $E(\varepsilon_{i}\varepsilon_{j})\neq0$ then:  

$$
\sigma^{2}(\varepsilon_{p})=\frac{1}{n}\overline{{\sigma}}^{2}(\varepsilon_{i})+\frac{n-1}{n}\overline{{C o v(\varepsilon_{i},\varepsilon_{j})}}
$$  

where $\overline{{\sigma}}^{2}(\varepsilon_{i})$ is the average variance of the frm’s specifc risks and $\overline{{C o v(\mathfrak{c}_{i},\mathfrak{s}_{j})}}$ is the average covariance of the (contemporaneous) specifc risks across frms:  

$$
\overline{{\sigma}}^{2}(\varepsilon_{i})=\frac{1}{n}\sum_{i=1}^{n}\sigma^{2}(\varepsilon_{i})
$$  

and  

$$
\overline{{C o v}}(\varepsilon_{i},\varepsilon_{j})=\frac{1}{n(n-1)}\sum_{i=1}^{n}\sum_{\substack{j=1\atop\mathrm{for~i\neqj}}}^{n}E(\varepsilon_{i}\varepsilon_{j})
$$  

From (45.B.11a) the variance term goes to zero as $n$ increases so for large $n$ , the variance of portfolio specifc risk $\sigma^{2}(\varepsilon_{p})$ equals the average covariance between specifc risks across diferent stocks, $\overline{{C o v(\mathfrak{c}_{i},\mathfrak{s}_{j})}}$ . In a well-diversifed portfolio where stocks are held across many diferent sectors (and countries), the average covariance of ‘specifc risk’ across frms is likely to be small relative to market risk, $\beta_{p}^{2}\sigma_{m}^{2}$ . Hence Equation (45.B.9) is a reasonable approximation. Of course, if our portfolio is not well diversifed (e.g. we hold only energy stocks) then the assumption of the SIM that $E(\varepsilon_{i}\varepsilon_{j})=0$ will be incorrect and $\overline{{C o v(\mathfrak{c}_{i},\mathfrak{c}_{j})}}$ may be quite large. In this case our simplifed expression for portfolio risk $\sigma_{p}=\beta_{p}\sigma_{m}$ ceases to hold and all the $n(n-1)/2$ covariances $E(\varepsilon_{i}\varepsilon_{j})$ are required for an accurate calculation of $\sigma_{p}$ .  

# APPENDIX 45.C: CASH FLOW MAPPING  

# Mapping  

A numerical example is the best way to illustrate this problem. Suppose we have an actual cash fow of $\$1000$ at $t=6$ years and we need to map this onto the ‘vertices’ at $t=5$ and $t=7$ (see Table 45.C.1).  

TABLE 45.C.1 Data   


<html><body><table><tr><td>Time/Vertices</td><td>Yield</td><td>Price volatility = (1.65o)</td><td>Correlation matrix</td></tr><tr><td>Year 5</td><td>Y5 = 6.5%</td><td>5 = 0.3</td><td>1</td></tr><tr><td>Year 7</td><td>y7 = 6.7%</td><td>97 = 0.6</td><td>0.99</td></tr></table></body></html>  

To fnd the proportions of the actual cash fow of $\$1000$ at $t=6$ , which we should apportion to vertices $t=5$ and $t=7$ we proceed as follows:  

1. The PV of the actual cash fow using $y_{6}$ is  

$$
V_{6}=100/(1+y_{6})^{6}=\mathfrak{G}68.15
$$  

2. The yield at $t=6$ we take to be a linear interpolation of $y_{5}$ and $y_{7}$  

$$
y_{6}=(1/2)0.065+(1/2)0.067=0.066(6.6\%)
$$  

3. The volatility at $t=6$ is a linear interpolation of $\sigma_{5}$ and $\sigma_{7}$ :  

$$
\sigma_{6}=\left(1/2\right)0.3+\left(1/2\right)0.60=45
$$  

4. We apportion the cash fow at $t=6$ , between $t=5$ and $t=7$ , to ensure positive cash fows at each vertex $\cdot V_{5}$ and $V_{7}>0\dot{}$ and that the volatility of $V_{5}+V_{7}$ is equal to $\sigma_{6}$ :  

$$
\begin{array}{r l}&{V_{5}=\gamma V_{6}\qquad\mathrm{and}\qquadV_{7}=(1-\gamma)V_{6}}\\ &{\gamma^{2}\sigma_{5}^{2}+(1-\gamma)^{2}\sigma_{7}^{2}+2\gamma(1-\gamma)\rho\sigma_{5}\sigma_{7}=\sigma_{6}^{2}=0.45}\end{array}
$$  

We have estimates of $\sigma_{5},\sigma_{7},\rho$ (Table 45.C.1) and from Equation (45.C.2) we obtain two solutions $\gamma=0.496$ or $\gamma=3.38$ (see below). We ignore the solution $\gamma=3.38$ since it violates positive cash fows at both vertices (i.e. $1-\gamma<0.$ ). Hence for $\gamma=0.496$ :  

$$
\begin{array}{r l}{}&{{\cal V}_{5}=\gamma(\S68.15\mathrm{m})=\S33.80\mathrm{m}}\\ {}&{{\cal V}_{7}=(1-\gamma)(\S68.15\mathrm{m})=\S34.35\mathrm{m}}\end{array}
$$  

The results are summarised in Table 45.C.2.  

Solution for  

The left-hand side of (45.C.2) is a quadratic equation in $\gamma$ of the form:  

$$
\alpha\gamma^{2}+b\gamma+c=0
$$  

with $a=\sigma_{5}^{2}+\sigma_{7}^{2}-2\rho\sigma_{5}\sigma_{7}$ , $b=2\rho\sigma_{5}\sigma_{7}-2$ and $c=\sigma_{7}^{2}-\sigma_{6}^{2}$ . The solution of Equation 45.C.5 for $\gamma$ is: 0.496 which implies that 49.6 percent of the 6th year cash fow should be allocated to year-5.  

TABLE 45.C.2 Mapping cash fow at $t=6$ to vertices at $t=5$ and $t=7$   


<html><body><table><tr><td colspan="8">Actual cash flow: $100m at 6 years</td></tr><tr><td></td><td>(1) Term</td><td>(2) Actual cash flow</td><td>(3) Yield </td><td>(4) PV</td><td>(5) Price vol.</td><td>(6) Allocation weights, </td><td>(7) Flows</td></tr><tr><td>Vertex 5 years</td><td>5 years</td><td></td><td>Y5 = 6.5%</td><td></td><td>0.3</td><td>0.496</td><td>$33.80m</td></tr><tr><td>Cash flow</td><td>6 years</td><td>$100m</td><td>Y6 = 6.6%</td><td>$68.15m</td><td>0.45</td><td></td><td></td></tr><tr><td>Vertex 7 years</td><td>7 years</td><td></td><td>y7 = 6.7%</td><td></td><td>0.6</td><td>0.504</td><td>$34.35m</td></tr></table></body></html>  

# EXERCISES  

# Question 1  

Show how the single index model (SIM) can lead to considerable simplifcation when calculating the value at risk (VaR) over a 10-day horizon, for a portfolio of 20 domestic stocks with $\$10,000$ in each stock. Clearly state any assumptions you make and their importance in determining the practical strengths and weaknesses of the SIM.  

# Question 2  

What is ‘mapping’ and why is it useful in calculating the VaR for a portfolio consisting of coupon paying bonds?  

# Question 3  

You are a US resident who holds a portfolio of UK stocks of $\mathtt{\ d100m}$ . The current USD/GBP exchange rate is 1.5 USD/GBP, the correlation between the return on the UK portfolio and the USD/GBP exchange rate is $\uprho=0.5$ . The return on the FTSE All-Share index has a standard deviation of $1.896\%$ per day and the volatility of the USD-GBP spot rate is $\sigma_{F X}=3\%$ per day. Using the variance-covariance VCV method calculate the daily US dollar VaR at the 5th percentile.  

# Question 4  

You are a US resident with $\mathsf{\epsilon}_{\mathrm{t100m}}$ in the DAX-index and $\$1000$ face value in a US zero-coupon bond which matures in one year. The current spot FX rate is $S=0.6$ (USD/Euro) and the US spot interest rate is $r=3\%$ . The daily standard deviations on the FX-rate, the DAX, and the US bond price are $\sigma_{\mathrm{{S}}}=3\%$ , $\sigma_{\mathrm{DAX}}=2\%$ , and $\sigma_{\mathrm{B}}=0.5\%$ , respectively. The correlation coe\$- cients are $\rho_{\mathrm{S,DAX}}=-0.5,\rho_{\mathrm{S,B}}=0$ , $\rho_{\mathrm{B,DAX}}=0.2$ . Using the variance-covariance (VCV) method calculate the daily VaR of your portfolio (at the 5th percentile) and the worst-case VaR.  

# Question 5  

A zero-coupon bond pays £1,000 in 2 years’ time. You have the following information:  

Current yield $y=8.25\%$ ., standard deviation of change in yield $\sigma_{d y}=1.009\%$ per day.  

(i) Calculate the market value of the zero-coupon bond. (ii) Calculate the daily VaR for this bond (at the 5th percentile). (iii) Calculate the 10-day and 25-day VaR.  

# Question 6  

You hold coupon bonds which pay $\$10,000$ in 1 year’s time and $\$120,000$ in 2 years’ time. The 1-year and 2-year spot yields are $3\%$ p.a. and $4\%$ p.a. respectively (continuously compounded). The volatility of the daily change in yields is $\sigma(d y_{1})=0.001$ $0.1\%$ per day) and $\sigma(d y_{2})=0.002$ $(0.2\%$ per day).  

The correlation between the change in the 1-year and 2-year yields is 0.8.  

Use the variance-covariance method (VCV) to calculate the daily VaR of this coupon bond (at the 5th percentile).  

Question 7 A coupon paying bond has the following cash fow profle   


<html><body><table><tr><td>Year</td><td>1</td><td>2</td><td>3</td></tr><tr><td>Cash flow ($)</td><td>400</td><td>450</td><td>500</td></tr><tr><td>Spot rate (% p.a.)</td><td>7.84</td><td>7.96</td><td>7.98</td></tr><tr><td>Stdv of bond price changes (% per day)</td><td>0.23</td><td>0.20</td><td>0.25</td></tr></table></body></html>  

Spot yields are compound rates. The correlation between changes in the price (present value) of the 1-year, 2-year and 3-year cash-fows are $\mathsf{\rho}_{12}=0.8$ , $\uprho_{13}=0.7$ , and $\uprho_{23}=0.6$ .  

(a) Calculate the market value of each cash fow (i.e. price of the zero-coupon bonds).   
(b) Calculate the (one day) VaR for each cash fow taken separately.   
(c) Calculate the VaR of the coupon paying bond.  