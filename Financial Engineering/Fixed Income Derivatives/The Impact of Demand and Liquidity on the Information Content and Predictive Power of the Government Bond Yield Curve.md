---
tags:
  - government_bonds
  - interest_rates
  - liquidity
  - market_expectations
  - yield_curve
aliases:
  - Forward Rates
  - Spot Yield Curve
  - Term Structure
  - UK Gilt Market
key_concepts:
  - Government bond yield curve
  - Impact of liquidity
  - Market interest rate expectations
  - Money market swap yield curve
  - Predictive power of yield curve
---

# The Impact of Demand and Liquidity on the Information Content and Predictive Power of the Government Bond Yield Curve

## The Impact of Demand and Liquidity on the Information Content and Predictive Power of the Government Bond Yield Curve: An Illustration From the UK Gilt Market

Abstract  

Use of the government term structure to ascertain the market’s expectation of future interest rates is well established. This reflects the fact that the spot yield curve is the geometric average of the same maturity structure implied forward rates. The predictive power of the spot curve is illustrated using examples from the past, in conjunction with the money market swap yield curve. Low levels of liquidity resulting from an excess of demand over supply in government bonds may reduce the predictive power of the term structure, or render its information content inaccurate, due to an artificial effect on the shape of the yield curve, and the example used to illustrate this suggests that in these cases the swap yield curve should be used to determine market expectations of future interest rates.  

# I Introduction  

The pricing of financial instruments in the debt market revolves around the yield curve. Participants assume that a unique interest rate exists for a debt instrument of any specific term to maturity, thus enabling a continuous function to be constructed that describes the specific spot interest rate for each maturity. This  term structure of interest rates  is used for a number of purposes by central government monetary authorities and by analysts and economists. In the United Kingdom for example the yield on government bonds is used as the benchmark for interest charges to local authorities and public sector bodies. Yield curve data may also used as one of the parameters for a general interest rate model (for example, Cox, Ingersoll, Ross 1985, Heath, Jarrow, Morton 1992).  

Although the use of yield curves is quite common as part of monetary policy analysis, central banks such as the US Federal Reserve and the Bank of England have only recently begun to use  forward  interest rates as an indicator for monetary policy purposes. A forward rate is an interest rate applicable to a debt instrument whose term begins at a future date, and ends at a date beyond that. Although there is a market in forward rates, the prices at which forward instruments are quoted are derived from spot interest rates. That is,  implied  forward rates are calculated from the spot yield curve, which is in turn modelled from the prices of instruments in the market, usually government bills and bonds. This implies that the shape and position of the spot curve reflects market belief on future interest rates, which is why it is used to calculate forward rates. The information content and predictive power of a spot term structure is based on this belief. Forward rates may be estimated using any one of a number of models. They can be interpreted as reflecting the market’s expectations of future  short-term  interest rates, which in turn are indicators of expected inflation levels. The same information is contained in the spot yield curve, however monetary authorities often prefer to use forward rates as they are better applied to policy analysis. Whereas the spot yield curve is the expected average of forward rates, the forward rate curve reflects the expected future time period of one short-term forward rate. This means that the forward curve can be split into shortterm and long-term segments in a more straightforward fashion than the spot curve.  
As it is used as a predictive indicator, the spot yield curve needs to be fitted as accurately as possible. This is an area that has been extensively researched (see McCulloch 1975, Deacon and Derry 1994, Schaefer 1981, Waggoner 1997, Nelson and Siegel 1987, Svensson 1994, 1995  inter alia ). Invariably researchers use the government debt market as the basis for modelling the term structure. This is because the government market is the most liquid debt market in any country, and also because (in a developed economy) government securities are default-free, so that government borrowing rates are considered risk-free. The purpose of this paper is to indicate how the yield curve in a government market may lose some of its information content and predictive power, that is, indicate misleading signals, due to the impact of demand and liquidity on government yields and spot rates. When this happens, better results may be obtained by using another market yield curve, which we hope to illustrate by using the interest-rate swap yield curve. Section II describes the justification for using the spot yield curve as vehicle for deriving forward rates, allowing us to conclude that a spot curve has predictive content. Section III uses some historical examples of where curves predicted future short-rates, while section IV demonstrates the impact of high demand and depressed yields to suggest that the predictive power may be diminished in special situations. Section V is the conclusion of the paper.  

# II Bond market information  

Central banks and market practitioners use interest rates prevailing in the government bond market to extract certain information, the most important of which is implied forward rates. These are an estimate of the market’s expectations about the future direction of short-term interest rates. Forward rates may be calculated using the discount function or spot interest rates. If spot interest rates are known then the bond price equation can be set as:  

$$
P\!=\!\frac{C}{\left(1+r s_{1}\right)}\!+\!\frac{C}{\left(1+r s_{2}\right)^{2}}\!+\!....+\!\frac{C+M}{\left(1+r s_{n}\right)^{n}}
$$  

where  

$C$  is the coupon  $M$  is the redemption payment on maturity (par)  $r s_{t}$  is the  spot interest rate  applicable to the cash flow in period   $t\left({t=}1,...,n\right)$  .  

The bond price equation is usually given in terms of  discount factors , with the present value of each coupon payment and the maturity payment being the product of multiplying them by their relevant discount factors. This allows us to set the price equation as shown by (2).  
$$
P=C_{_{t=1}}^{^{n}}d f_{t}+d f_{n}M
$$  

where  $d f_{t}$   is the  $t\cdot$  -period discount factor   $({\mathfrak{t}}{=}1,...,m)$   given by (3) below.  

$$
d f_{t}=\frac{1}{\left(1+r s_{t}\right)^{t}}\,,\qquad\quad t=1,.......,m
$$  

A discount factor is a value for a discrete point in time, whereas markets often prefer to think of a continuous value of discount factors that applies a specific discount factor to any time  $t$  . This is known as the  discount function , which is the continuous set of discrete discount factors and is indicated  by   $d f_{t}=\delta\!\left(t_{t}\right)$  .  

The discount function relates the current cash bond yield curve with the spot yield curve and the implied forward rate yield curve. From (3) we can set:  

$$
d f_{t}=\left(1+r s_{t}\right)^{-t}.
$$  

As the spot rate   $r s$   is the average of the implied short-term forward rates  $r f_{1},\,r f_{2},\,......r f_{t}$  we state:  

$$
\begin{array}{r l}&{1\mathbin{/\,d f_{1}}=\bigl(1+r s_{1}\bigr)=\bigl(1+r f_{1}\bigr)}\\ &{1\mathbin{/\,d f_{2}}=\bigl(1+r s_{2}\bigr)^{2}=\bigl(1+r f_{1}\bigr)\bigl(1+r f_{2}\bigr)}\\ &{1\mathbin{/\,d f_{n}}=\bigl(1+r s_{n}\bigr)^{n}=\bigl(1+r f_{1}\bigr)\bigl(1+r f_{2}\bigr)......\bigl(1+r f_{n}\bigr)}\\ &{1\mathbin{/\,d f_{t}}=\bigl(1+r s_{t}\bigr)^{t}=\bigl(1+r f_{1}\bigr)\bigl(1+r f_{2}\bigr)......\bigl(1+r f_{t}\bigr)}\end{array}
$$  

From (4) we see that   $1+r s_{t}$   is the geometric mean of   $(1+r f_{1}),(1+r f_{2}),.....,(1+r f_{t}).$  .  

Implied forward rates indicate the expected short-term (one-period) future interest rate for a specific point along the term structure; they reflect the spread on the marginal rate of return that the market requires if it is investing in debt instruments of longer and longer maturities. The relationship between forward rates and bond prices is given by (5) below.  

$$
P(t)=\exp\!{\Big|}-\mathbf{\Pi}_{0}^{t}r f(m)d m\!{\Big|}
$$  

where  

$P(t)$  is the price of a zero-coupon bond with term to maturity of  t  
We can use (5) to derive the implied forward rate between any two points along the term structure. For example the implied forward rate now, between points in time of  $m$   and   $t$   is given by (6).  

$$
\boldsymbol{r}f_{0}=\sum_{m}^{t}\boldsymbol{r}f(m)d m
$$  

In order to calculate the range of implied forward rates we require the term structure of spot rates for all periods along the continuous discount function. This is not possible in practice because a bond market will only contain a finite number of coupon-bearing bonds maturing on discrete dates. While the coupon yield curve can be observed, we are then required to “fit” the observed curve to a continuous term structure. Note that in the UK gilt market for example, there is a zero-coupon bond market, so that it is possible to observe spot rates directly, but for reasons of liquidity, analysts prefer to use a fitted yield curve (the  theoretical  curve) and compare this to the observed curve.  

There are a number of models that one may use to fit the spot rate term structure. One-factor models (see Vasicek 1997, Dothan 1978, Cox, Ingersoll, Ross 1985) model the one-period short rate to obtain a forward yield curve. The simplest method uses a binomial model of probabilities to model the forward rate. Multi-factor models (see Harrison, Pliska 1981, Heath, Jarrow, Morton 1992) express analytically the entire yield curve in terms of two forward rates (or “spanning” rates). For an analysis of the information content of both methodologies see Edmister and Madan (1993), who conclude that the multi-factor models provide more accurate results. Essentially the information content of the yield curve is best estimated using a multi-factor model, and is more accurate at the longer end of the curve whatever methodology is used. Edmister and Madan also conclude that modelling the short-end of the curve will suffer from distortions resulting from government intervention in short-term interest rates.  

The Bank of England uses the Svensson yield curve model, a one-dimensional parametric  yield curve model. This is similar to the Nelson and Spiegel model and defines the forward rate curve   $\ensuremath{\boldsymbol{r}}\!f(m)$   as a function of a set of unknown parameters, which are related to the short-term interest rate and the slope of the yield curve. The model is summarised in Appendix I. Anderson and Sleath (1999) assess parametric models, including the Svensson model, against spline-based methods such as those described by Waggoner (1997).  
# III Observations of yield curves  

The previous section set out the justification for using the government term structure as indicators of expected future interest rates. It showed that as the current spot term structure reflects the market’s view of future interest rates, practitioners and analysts may use it to calculate implied forward interest rates. These may then be taken to be the market’s prediction of future short-term interest rates.  

The conventional explanation behind the  shape  of the yield curve is that it reflects the long-term interest rate to be the geometric average of expected future short-term rates, so that a positively sloped yield curve will result whenever the market expects future short-term rates to rise, and an inverted yield curve will result when investors expect short-term rates to fall. Interest-rate expectations themselves are a function of future rates of inflation. This is known as the  expectations hypothesis . Coupled with the  liquidity preference theory , which states that the long-run trade-off between the desire of borrowers to trade at the long-end and lenders to trade at the short-end is a positively sloping yield curve, this is the main market argument why a yield curve may assume a certain shape. Finally the existence of “humps” along certain points is explained by the  segmentation hypothesis , and there is evidence to suggest that the investment preferences of specific groups of investors, who will be interested in particular points of the curve, results frequently in the certain parts of curve being expensive relative to other parts, resulting in humps along the curve. None of the theories is a completely satisfactory explanation for the shape of the gilt yield curve from July 1997, which we return to shortly.  

A negative yield curve is generally interpreted as signalling a recession, during (or ahead of) which the central bank will ease the money supply in an effort to boost economic activity. The market prices debt instruments based on its belief that future short-term interest rates will decline, hence the inverted curve. Of the four recessions in the United States in the last thirty years (generally taken to be the periods November 1973- March 1975, January 1980 - July 1980, July 1981 - November 1982, July 1990 - March 1991), all but the first have been marked by inverted curves. Indeed all post-war recessions bar one in the US have been marked by an inverted yield curve ahead of them (see  The Economist  1998).  

We aim to show in this section that while the predictive power of the government yield curve has been generally accurate, with the resulting future swap and government curves being observed in the form predicted, where the curve shape is distorted due to market conditions, the information content may disappear or be misleading. An obvious indicator is given when the yield curve is inverted. To begin consider the observed yield curves for January and June 1990 in figures 1 and 2.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/43be71083843bdd5fcdaa90d998c1ba7741244f4d5f6575d774bd61d655c1789.jpg)  

The yield curve for the first date suggests declining short-term rates and this is indicated by the yield curve for June 1990. The prediction is approximately accurate. Consider the same curves for June 1991 and January 1992, shown as figures 3 and 4 respectively. In this case the money market has priced swaps to give a different shape yield curve; does this mean that the money market has a different view of forward rates to government bond investors? Observing the yield curves for January 1992 suggests not: the divergence in the swap curve reflects credit considerations that price long maturity corporate rates at increasing yield spreads. This is common during recessions, and indeed the curves reflect recession conditions in the UK economy at the time, as predicted by the yield curves during 1990. Another indicator is the continuation of the wide swap spread as the term to maturity increases to ten years, rather than the conventional mirroring of the government curve. Note also that the short-term segment of the swap curve in June 1991 (figure 3) matches the government yield curve, indicating that the market agreed with the short-term forward rate prediction of the government curve.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/110c45fdfc5c287a6a9c7e0154b4e25fd4e1f44e2192ffbb1598fd17d4533750.jpg)  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c0b215c46d8acb91c15af7fe79187119a83e9fb716453d77f97e2812e9049547.jpg)  
Both yield curves had reverted to being purely positive sloping by January 1993.  

The illustrations used up to now are examples where the government yield curves were found to be accurate predictors of the short-term rates that followed, more so than the swap curve. This is to be expected: the government or  benchmark  yield curve is the cornerstone of the debt markets, and is used by the market to price all other debt instruments, including interest-rate swaps. We noted at the start that this reflects both the liquidity of the government market and its risk-free status.  

# IV The impact of demand and lower liquidity  

During July 1997 the gilt yield curve moved from positive sloping to inverted. This reflected two new considerations: that the long-term outlook for inflation was now relatively benign, given that monetary policy was now the responsibility of the Bank of England,  and that sterling was expected over the medium-term to join the EU’s euro currency. Both were the result of actions or indications made by the newlyelected Labour government. However the shape of the yield curve may have been considered to be an anomaly as both the above considerations are medium- to longterm issues; and therefore do not explain curve inversion at the short-end. This state was preserved until July 1999, when the curve turned positive out to the 6-7 year end, and remained inverted beyond that. However this also reflected other singular factors.  
The institutional demand for gilts has been steadily increasing, and this has been depressing yields at the long end, independent of inflation or EMU considerations. This is in large part a result of the Minimum Funding Requirement, a segment of the Pensions Act 1995, which has been effective since 1997. This sets out a minimum level of investment in government bonds for institutional investors such as pensions funds. The demand has been highest for long-dated gilts. There has also been increased demand from investors seeking to hedge minimum annuity levels for contracts sold at a time when yields were significantly higher (BoE 1999). The strong demand for gilts, together with lower supply of long-dated gilts (which has been continuing, as the government targets a budget surplus), has led to yields being depressed to historically low levels. For example during much of 1999 30-year gilt yields were lower than 30-year government yields in the US, Germany and France, a situation not observed for over 30 years. The fall in gilt yields has also widened the swap spread. For example at the start of the year, ten-year swap spreads in the UK were over 80 basis points, compared to half this level in Germany. In the absence of recession conditions, this spread cannot be said to reflect credit considerations, but rather the depressed level of government yields.  

Does the demand for gilts, and the lack of supply at the long-end, have any effect on the usefulness of the yield curve with regard to its information content? Lower supply will contribute to lower liquidity in the market. The market for sterling interest-rate swaps is invariably very liquid, so the curve may be used to analyse perceptions of forward rates. Figure 6 shows the two curves in January 1999.  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a8d5391b8988f0209e360e46731beb135a2d4db2f2826f400a33ca78175b6437.jpg)  
Figure 6  
At the beginning of 1999 market interest-rate swap levels declined, reflecting that sterling base rates fell in January and February 1999. This resulted in a positive sloping swap curve, compared to the inverted government bond curve as shown in figure 6. This implied therefore that the market was predicting  higher , as opposed to lower, short-term future interest rates, contrary to the forward rates that would be implied by the government curve. Unlike the situation in 1991, which reflected a recession and widening credit spreads, this was shown to be an accurate prediction as shown by figure 7, the corresponding yield curves for April 1999. Both yield curves are at absolute higher levels, although the swap curve now is also inverted, suggesting the market now agreed that short-term rates were expected to fall in the near future.  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/851beb79c64de966df9ffc306662a648b535657e65015f40a98396440ae6a682.jpg)  

It is possible to use other yield curves to imply that the low liquidity and depressed yields for government bonds lowered the information content of the government curve. Figure 8 shows the short-term implied forward rates calculated using gilts and German government bonds (which now are denominated in euros), as well as implied forward rates derived from sterling and euro swap rates, in April 1999. The forward curves are derived using the Svensson model. The implied forward rates calculated using the gilt curve lie below those implied by German government bonds, which is expected given the relative position of the spot curves; however we note that the sterling swap implied forward rates are closer to the euro forward rates, and showed convergence at the long end (when rates might be expected to be moving to euro levels as sterling prepared for EMU entry). This implied that the market belief was reflected more accurately in the swap yield curve than the government yield curve, which was artificially depressed due to high demand and low supply of long-dated gilts.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/db9f71edf085ca866d6f1c04ad66e3177e8d4169eb50492e98dc88cf072ad00d.jpg)  

# V CONCLUSION  

The liquid and risk-free characteristics of the government bond market are primary reasons why traded yields and the spot term structure are used to derive implied forward rates, which are then used as an indication of the market’s expectation of future interest rates. We have observed that where, due to special circumstances leading to low liquidity, the information content of the government curve may be diminished, to the point where the Libor curve should then be used to derive views on future interest rates. Although the observation is for one point in 1999, we would expect the anomaly to be short-lived, as liquidity levels return to more normal levels, so that the yields reflect market expectations more accurately.  
# APPENDIX I  

The Nelson and Spiegel yield curve model states that the implied forward rate yield curve may be modelled along the entire term structure using the following function:  

$$
r f\big(m,\beta\big)=\beta_{0}+\beta_{1}\exp\big|\,\frac{-\,m}{t_{1}}\,\big|+\beta_{2}\bigg(\frac{m}{t_{1}}\big|\exp\!\bigg(\frac{-\,m}{t_{1}}\bigg)\,
$$  

where  

$\beta\!=\!\big(\beta_{o},\beta_{1},\beta_{2},t_{1}\big)!$    is the vector of parameters describing the yield curve, and   $m$   is the maturity at which the forward rate is calculated. There are three components, the constant term, a decay term and term reflecting the “humped” nature of the curve. The shape of the curve will gradually lead into an asymptote at the long end, the value of which is given by   $\beta_{0}$   , with a value of   $\beta_{0}+\beta_{1}$   at the short end. The Svensson model is a version of this, with an adjustment to allow for the humped characteristic of the yield curve. This is fitted by adding an extension, as shown by A2 below.  

$$
r f(m,\beta)=\beta_{0}+\beta_{1}\exp\!\mid\frac{-m}{t_{1}}\!\mid+\beta_{2}\!\left(\frac{m}{t_{1}}\right)\exp\!\left(\frac{-m}{t_{1}}\right)+\beta_{3}\!\left(\frac{m}{t_{2}}\right)\exp\!\left(\frac{-m}{t_{2}}\right)
$$  

The Svensson curve is modelled therefore using six parameters, with additional input of   $\beta_{3}$   and  $t_{2}$  .  

# REFERENCES  

Anderson. N., Sleath, J., “New estimates of the UK real and nominal yield curves”,  Bank of England Quarterly Bulletin , November 1999, pp.384-392 Cox, J., Ingersoll, J., Ross, S., “A Theory of the Term Structure of Interest Rates”,  Econometric a  53, 1985, pp.385-407Dothan, U., “On the term structure of interest rates”,  Journal of Financial Economics  6, 1978, pp. 59-69 Deacon, M., Derry, A., “Estimating the term structure of interest rates”,  Bank of England Working Paper , No. 24. July 1994 Bank of England,  Quarterly Bulletin , August 1999 The Economist,  Admiring those shapely curves , 4 April 1998, p.117 Edmister, R.O., Madan, D.P., “Informational Content in Interest Rate Term Structures”,   The Review of Economics and Statistics  75 (4), pp.695-699 November 1993 Harrison, J., Pliska, S., “Martin gales and Stochastic Integrals in the Theory of Continuous Trading”, Stochastic Processes and their Applications  11, 1981, pp. 215-260 Heath, D., Jarrow, R., Morton, A., “A New Methodology for Contingent Claims Valuation”, Econometric a  60, 1992, pp. 76-106 M astro nikola, K., “Yield curves for gilt-edged stocks: a new model”,  Bank of England Discussion Paper (Technical Series) , No. 49, 1991 McCulloch, J., “The Tax Adjusted Yield Curve”,  Journal of Finance  30, June 1975, pp.811-829 Nelson, C., Siegel, A., “Parsimonious modelling of yield curves”,  Journal of Business , Volume 60, 1987, p.473 Schaefer, S., “Measuring a tax-specific term structure of interest rates in the market for British government securities”,  The Economic Journal , Volume 91, June 1981, pp. 415-438 Svensson, L., “Estimating forward interest rates with the extended Nelson & Siegel method”, Sveriges Riksbank Quarterly Review , 1995: 3, p.13 Waggoner, D., “Spline methods for extracting interest rate curves from coupon bond prices”, Working Paper , No. 97-10, 1997, Federal Reserve Bank of Atlanta Vasicekk, O., “An Equilibrium Characterization of the Term Structure”,  Journal of Financial Economics  5, 1977, pp. 177-188  
