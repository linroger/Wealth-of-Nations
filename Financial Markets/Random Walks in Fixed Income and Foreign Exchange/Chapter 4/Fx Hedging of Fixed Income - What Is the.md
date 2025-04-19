---
tags:
  - cross_currency
  - fixed_income
  - fx_hedging
  - fx_risk
  - maturity_matched
aliases:
  - FX Hedge Strategies
  - FX Hedging
  - Maturity-Matched Hedges
key_concepts:
  - Cross-currency basis
  - FX risk for fixed income
  - Foreign yield curve
  - Maturity-matched pickup
  - Unhedged positions
---

# Chapter 4 FX Hedging of Fixed Income - What is the Best Way?

In Chapter 1 and Chapter 3, we showed that in some cases, it may be possible to hedge the FX risk of some fixed income instruments and lock in a gain, for institutions with access to the right markets and credit ratings.' However, the science of hedging FX risk for fixed income instruments was not designed purely to take advantage of this type of opportunity, but rather to reduce risk on the overseas fixed income assets. In this chapter, we examine alternative ways of hedging these assets and show that it is possible to express the various alternatives in a coherent mathematical framework. We will also illustrate the risks of some popular partial hedge methods that are not all that they seem.

# FX Hedge Strategies

Before going into detail about the results of different hedge strategies and pickups, it is worth defining exactly what they are:

The maturity-matched pickup is equal to the cross-currency basis minus the swap spread differential of the assets minus the 3s/6s basis (as the EUR asset swap is usually quoted versus 6m). When holding the position to maturity, one already knows the return when entering into the trade (i.e. it is a full hedge). We have defined this case as maturity-matched' but it could also be called 'cashflow matched' or 'cross currency swap hedged' - the important thing is that it is. a complete hedge whose pickup is known and locked in from the start. The pickup from rolling hedges via a short-dated FX swap derives from the steepness of the foreign yield curve relative to the domestic curve, but it is not a full hedge. For example, a large increase in funding rates of the foreign currency. over the term of the trade would generate negative returns. In this sense, it is related to an interest rate carry trade. Unhedged positions - where the investor buys a higher-yielding instrument. funded by borrowing in a lower yielding one - are fully exposed to FX swings. In effect, they are an FX carry trade and thus are highly volatile..

# Maturity-Matched Hedges

# Reducing Uncertainty to the Minimum Level for the Whole Tenor

As a EUR-based (or JPY-based) investor, the higher yields currently available for US bonds across the tenor range are attractive. How could the EUR-based investor take advantage of this?

In a financial market with no capital charges or regulatory and XVA issues, it. would not be possible to preserve any kind of yield pickup by investing in a foreign bond and then hedging the FX risk. The theoretical' forward FX rate would, in the. pre-2008 crisis days, have almost exactly cancelled out the yield pickup, though there might have been some credit spread available. But even this was small.

Now, however, there exists in general a substantial cross-currency basis, meaning that the arbitrage relationship between FX spot and forward, and interest rates, has broken down to an extent, partly due to the demand for different currencies and partly due to regulatory activity that restricts arbitrage trades. The actual cross cur-. rency basis is usually expressed as a difference to the non-UsD interest rate of the currency pair, though it could equally be expressed as a spread to the USD rate or to the FX spot or theoretical forward rate. Additionally, credit spread differentials have become far more significant since the crisis, and may provide additional pickup in different industries and tenors.

We would execute the hedge in the swap market, which has slightly different rates from the government bonds (though they are correlated), and we would include the basis swap. The (US) basis swap is the extra cost of borrowing US dollars via a currency swap compared to what it should be purely according to interest rate differentials.

What, then, will the cost of hedging be? The mechanics of the package are thus:. the EUR-based investor exchanges EUR for USD, buys the USD bond, and puts on a maturity-matched FX hedge. Simplistically, assuming a 1-year period, and without worrying about coupon payments, we can write this as the following..

FX is the FX rate at the start of the deal $\mathrm{FR}_{1}$ is the 1-year forward FX rate for the bond maturity

$$
\begin{array}{c}{P=\mathrm{EUR~principal~amount~at~start~of~deal}}\ {P\times F X=\mathrm{USD~principal~amount~at~start~of~deal}}\ {P\times\displaystyle\frac{F X}{F R_{1}}=\mathrm{EUR~principal~amount~at~end~of~deal}}\end{array}
$$

As stated, we are not worrying about hedging the interest rate risk. Thus

$$
{\mathrm{EUR~hedge~cost}}=P-P\times{\frac{F X}{F R_{1}}}
$$

But from the arbitrage-based construction of the forward rate FR, we know that

$$
F X=F R_{1}{\frac{1+R_{1}}{1+R_{2}}}
$$

Where ${\mathrm{R}}_{1}$ is the EUR interest rate, and. ${\mathrm{R}}_{2}$ is the USD interest rate for the bond tenor. Thus, the EUR hedge cost is given by

$$
{\mathrm{EUR~hedge~cost}}=P-\left[{\frac{P}{F R_{1}}}\right]\left[F R_{1}{\frac{1+R_{1}}{1+R_{2}}}\right]
$$

$$
{\mathrm{EUR~hedge~cost}}=P\left[1-{\frac{1+R_{1}}{1+R_{2}}}\right]=P\left[{\frac{R_{2}-R_{1}}{1+R_{2}}}\right]\approx P[R_{2}-R_{1}]
$$

${\mathrm{R}}_{2}$ is the UsD swap rate, but now we actually need to adjust it by the basis swap amount. Thus

$$
{\mathrm{EUR~hedge~cost}}\approx P[R_{2}+R_{b a s i s}-R_{1}]
$$

Because (1) and (2) are approximately equal to each other, it can be calculated either. way, depending on the data that is available. One would usually use equation (2), as the basis swap is explicitly incorporated, but if one wished to use the spot and forward FX rates, then it is possible to express the quantity. $[\mathrm{R}_{2}{+}\mathrm{R}_{\mathrm{basis}}{-}\mathrm{R}_{1}]$ in terms of these FX rates as in equation (1), because the forward FX rate in the market does. incorporate the basis.

It's not difficult to extend this to the multi-year case. We know that for n years,

$$
F X=F R_{n}{\frac{\left(1+R_{1}\right)^{n}}{\left(1+R_{2}\right)^{n}}}
$$

So the total EUR hedge cost over the whole deal is given by

$$
{\mathrm{EUR~hedge~cost}}=P\left[1-{\frac{\left(1+R_{1}\right)^{n}}{\left(1+R_{2}\right)^{n}}}\right]\approx P\left[{\frac{n\left(R_{2}-R_{1}\right)}{1+n R_{2}}}\right]\approx P\times n\left[R_{2}-R_{1}\right]
$$

$$
{\mathrm{EUR~annual~hedge~cost}}\approx P[R_{2}-R_{1}]\approx P\left(1-\left[{\frac{F X}{F R_{n}}}\right]\right)/n
$$

if we use a binomial expansion and take only the first order. Once more, of course, we actually need to include the basis swap, so the actual annual cost will be $\mathrm{P}[\mathrm{R}_{2}{+}\mathrm{R}_{-}$ basis- $\left|{{\mathrm{R}}_{1}}\right|$

$$
{\mathrm{EUR~annual~hedge~cost}}\approx P[R_{2}+R_{b a s i s}-R_{1}]\approx P\left(1-\left[{\frac{F X}{F R_{n}}}\right]\right)/n
$$

So we may now calculate a hedged yield pickup, which is actually accessible to the. EUR-based investor. It is FX hedged and relatively risk-free. Note that equation (3),. where the hedge cost is expressed in terms of the FX spot and forward rates, is a

novel way of calculating hedge cost. It is useful in that it is an alternative way of arriving at the answer from other data series than those usually used..

# Practical Calculation of Maturity-Matched Yield Pickup

From now on, we can omit the principal amount. $P$ in expressions, as it will always. cancel on both sides of the equation and there is no loss of generality in expressing all quantities as percentages.

Once we have the hedge cost, we may derive the annualised yield pickup very simply, as the following:

$$
 {\mathrm{Yield~pickup}}=[B_{2}-B_{1}]-{\mathrm{Hedge}}{\mathrm{Cost}}
$$

As previously discussed, in a perfectly efficient market, this would be zero, but in the 'real world' it is often substantial..

In practice, we may derive this yield pickup three ways.

(1) Using bond yields, swap rates and cross-currency basis swap

$$
 {\mathrm{Yield~pickup}}=[B_{2}-B_{1}]-[R_{2}+R_{b a s i s}-R_{1}]
$$

(2) Using asset swap spreads, 3s6s basis swaps and cross-currency basis swaps

$$
\mathrm{Yieldpickup}=[A_{1}-A_{2}]-C_{1}+R_{b a s i s}
$$

(3) Using bond yields and spot and forward FX rates

$$
{\mathrm{Yield~pickup}}=[B_{2}-B_{1}]-\left(1-\left[{\frac{F X}{F R_{n}}}\right]\right)/n
$$

Where, for a EUR investor buying a USD government bond,

$\mathrm{B}_{1}=\mathrm{EUR}$ bond yield
$\mathrm{B}_{2}=\mathrm{USD}$ bond yield
$\mathrm{R}_{1}=\mathrm{EUR}$ swap rate
$\mathrm{R}_{2}=\mathrm{USD}$ swap rate
$\mathrm{R}_{\mathrm{basis}}=\mathrm{XCCY}$ basis swap
$\mathrm{A}_{1}=\mathrm{EUR}$ asset swap
$\mathrm{A}_{2}=\mathrm{USD}$ asset swap
$\mathrm{C}_{1}=3\mathrm{s}6\mathrm{s}$ basis
$\mathrm{FX=}$ spot foreign exchange rate
$\mathrm{FR}_{\mathrm{n}}=$ forward foreign exchange rate for tenor n
$\mathbf{n}=$ tenor in years

Note that the 3s6s basis (i.e. the difference between swap rates referenced to $3\mathrm{m}$ and 6m Libor) may sometimes be needed if the other interest rates differ in their coupon frequency, and that the asset swap spread is $\mathrm{A}_{1}-\mathrm{A}_{2}$ rather than $\mathrm{A}_{2}-\mathrm{A}_{1}$ because it is always quoted as a positive spread over the government bond. Additionally, one may. need to be careful of the sign of the basis swap, which is usually quoted as a spread to. the non-USD interest rate, so if the basis-adjusted EUR interest rate is lower than the actual rate, then the basis swap will be a negative number..

Having done all of this, we see in Figure 4.1 that the three ways of calculating the yield pickup match beautifully.

![](142ffc1d9ced50fe2db29c7d2905a9d9429f2bf966ef090cedd36dfe7b29d5f8.jpg)
Figure 4.1: Maturity-matched FX hedged yield pickup for 2y USD bonds vs EUR vs German bonds, in bp.. Source: Commerzbank Research, Bloomberge

# Historical Results for G10 Maturity-Matched Yield Pickup

It is interesting to see how the available yield pickup has varied over time, tenor. and currency pair. In Figures 4.2 and 4.4, we show the generic bond yields, and in Figures 4.3 and 4.5, we show the pickup for 2y bonds since 2009 - it can be seen that recently, Japan has held the most promise..

It's obvious that the 'pickup' is not always positive - the point one can make is. that a negative pickup from the perspective of one currency of a pair is a positive. one from the other currency's perspective. Thus, the 2017 positive pickup in Japan. was an opportunity for EUR investors; the negative pickup available in 2016 for USD vs EUR was attractive for USD investors..

The same effect is visible to a greater extent for longer tenors. In Figure 4.6 through Figure 4.9, we plot the same data for 10y bonds.

We see that the available yield pickup often comes close to $1\%$ , which is a considerable amount in this era of close-to-zero rates..

![](755770ac8ae200f04153ba1e40ae30a71504fffb28ad223a2182f31de50edb34.jpg)
Figure 4.2: Generic bond yields for 2y USD and EUR bonds, in $\%$ Source: Bloomberg, Commerzbank Research

![](a3cc55a0e783e0a9abe0a53e26715f511b649e9e6f2c18f7efe69e91ef4a2e0e.jpg)
Figure 4.3: Maturity-matched FX hedged yield pickup vs EUR for 2y USD and EUR bonds, in $\%$ Source: Bloomberg, Commerzbank Research

![](156027e07afb1fcc712e01f5cfebb36fbbcebbeb1f570728b728d552d3cb22ee.jpg)
Figure 4.4: Generic bond yields for 2y JPY and EUR bonds, in $\%$ Source: Bloomberg, Commerzbank Research

![](6a27192a2fdfbc7d939668a7852207553cfd8fd9c00861c5d840a5cbd79aa11b.jpg)
Figure 4.5: Maturity-matched FX hedged yield pickup vs EUR for 2y JPY and EUR bonds, in $\%$ Source: Bloomberg, Commerzbank Research

![](7f4a98386baf8753e33efc9397a1b2dbabb01d9717839340415bcfec0bf2e440.jpg)
Figure 4.6: Generic bond yields for 10y USD and EUR bonds, in $\%$ Source: Bloomberg, Commerzbank Research

![](8e3df41386fffef19e3cf7616578ba7ff188e0f9d8889c1ccee32015ad926196.jpg)
Figure 4.7: Maturity-matched FX hedged yield pickup vs EUR for 10y USD and EUR bonds, in $\%$ Source: Bloomberg, Commerzbank Research

![](6703b5115913568997e0361e2aea80261ed1c0b050af73b79ce2f632f7bc078e.jpg)
Figure 4.8: Generic bond yields for 10y JPY and EUR bond, in $\%$ Source: Bloomberg, Commerzbank Research

![](3802212aaed601e3ae7cf9e2c20a572bcd5b68fe12c8a00e5b0f203888dc5b82.jpg)
Figure 4.9: Maturity-matched FX hedged yield pickup vs EUR for 10y JPY bond, in $\%$ Source: Bloomberg, Commerzbank Research.

# Rolling Hedges

# Taking a Short-Term View

An investor may want to gain some pickup but not lock in an FX hedge for the whole lifetime of the bond. In this case, it's straightforward to do a short-dated FX hedge - 3m is a popular tenor - and roll the hedge if desired, to continue with the deal at the end of this period. But it's important to realise that this is a very different deal than the maturity-matched hedge.

It's popular to compare the annualised yield pickup between both deal types - but. it is essential to recall that for the maturity-matched case, that pickup is delivered for every year of the tenor of the bond, while for the 3m case, the pickup is only available.

for $3\mathrm{m}$ , and will be a quarter of the annualised amount. Comparing the two annualised. rates as if they were equivalent involves some absolutely heroic assumptions, as we do not know what the short-term rolling rate will be after the first roll date..

But if we assume that the short-term swap rates and cross-currency basis stay. the same for the life of the deal (which they have never done since the markets started trading), then the two may be compared. Certainly, the comparison is valid. for the first three months of the deal. If interest rates and bases were to develop ex-. actly as predicted by forwards, then the return of the maturity-matched and rolling. trade should be identical. As this is also a heroic assumption, the P&L of investors with rolling hedges is exposed to interest rate changes..

How do we calculate the rolling pickup? We have in fact done all the work ear-. lier. There are no asset swaps available for quarterly periods, but we can still use methods (1) and (3), as described here..

(1) Using bond yields, swap rates and cross-currency basis swaps

$$
 {\mathrm{Yield~pickup}}=[B_{2}-B_{1}]-[R_{2}+R_{b a s i s}-R_{1}]
$$

(3) Using bond yields and spot and forward FX rates

$$
{\mathrm{Yield~pickup}}=[B_{2}-B_{1}]-\left(1-\left[{\frac{F X}{F R_{n}}}\right]\right)/n
$$

In these expressions, for the $3\mathrm{m}$ rolling hedge of bonds of any longer tenor, the swap rates $R$ are the $3\mathrm{m}$ interest rates, the basis swap is the $3\mathrm{m}$ tenor, the FX rate is $3\mathrm{m}$ forward, and $n$ is actually $1/4$ as the hedge is for $\%$ of a year.

# Possible Actions at 'Roll Point'

Let's now consider what the investor might do once the short hedge comes to an end. The FX rate and the yield curves will have changed during the course of the hedge. Thus, for a EUR-based investor who bought a USD bond at the start of the hedge, the value of the USD bond has changed in EUR terms.

But the FX hedge will deliver a payment that will make up this difference pre-. cisely. So if the investor wishes to maintain their exposure as the same amount of EUR, they can use the FX hedge maturity to buy or sell an additional amount of the. USD bond which should result in a constant EUR exposure, and they can put in. place another rolling hedge, this time for the new amount of USD per EUR. But the new pickup available for the new rolling hedge will not be the same as the old. It may be completely different - better or worse - leaving the investor to regret or rejoice in his or her original decision to roll rather than hedge for the full maturity of the deal.

Additionally, maintaining a rolling hedge program with a constant EUR expo-. sure requires constant adjustment of the USD notional, although the FX hedges will cover this difference.

# Historical Results for G10 Rolling Yield Pickup

We plot the rolling pickup throughout history for the same set of G10 currencies for the 2y case. It is easy to see that there are significant differences between the matched maturity and rolling hedges (Figures 4.10-4.13).

![](a30ede4dd33798daf24e167ef819f87976e55915cdbef3df5b9c5130ee08cbf0.jpg)
Figure 4.10: Generic bond yields for 2y USD and EUR bond, in $\%$ Source: Bloomberg, Commerzbank Research

![](8272092479e4dd76025a378e892325a4da36c8ae46023b7fb41f73b216e60dcf.jpg)
Figure 4.11: 3m FX hedged yield pickup vs EUR for 2y USD and EUR bond, in $\%$ Source: Bloomberg, Commerzbank Research

![](ff4069ce4bc58410ec70e98c046738574f6977da675bd6b4e2ce2c6dd345fdff.jpg)
Figure 4.12: Generic bond yields for 2y JPY and EUR bond, in $\%$ Source: Bloomberg, Commerzbank Research

![](e69f872efd1f452196e736f1e17be19cef667664b554c03b8e66d47c47a0c5f9.jpg)
Figure 4.13: 3m FX hedged yield pickup vs EUR for 2y JPY and EUR bond, in $\%$ Source: Bloomberg, Commerzbank Research.

In the following section, we repeat the calculation for 10y bonds. The pickup often looks substantial, but it is worth remembering that this is the annualised fig. ure; in reality, for the 3m tenor it would be $\%$ of that amount (Figures 4.14-4.17).

What underlying drivers are we seeing for these changes? It's interesting to. look at what is causing the evolution in available pickup. For the 3m rolling hedge of the 1Oy EUR bond (top left), we see that the spread between the EUR and USD bonds was widest in 2018. And yet, the available rolling pickup, which initially increased along with the spread, has narrowed since 2015 and has even reversed direction. This reduction is driven by the short-dated differentials; since 2015, they. have been steadily moving lower, eroding much of the gain from the longer tenors..

![](fee0b90c6e5c72d699fbf0a804255a2deec12bfe86a5a3a0b62989befb802422.jpg)
Figure 4.14: Generic bond yields for 10y USD and EUR bond, in $\%$ Source: Bloomberg, Commerzbank Research.

![](552cc36740e215f47d883c5f4f65ceef2312092567d30b9bb8736d8cdbcb9ece.jpg)
Figure 4.15: 3m FX hedged yield pickup vs EUR for 10y USD and EUR bond, in $\%$ Source: Bloomberg, Commerzbank Research

![](115037a503fc0628a0737546584916057a25de4acd51f3d21b63d5ffb3165b9f.jpg)
Figure 4.16: Generic bond yields for 10y JPY and EUR bond, in $\%$ Source: Bloomberg, Commerzbank Research

![](670b8cf2bd01d9f5ffeb5ffc0d642a4c283aaf65c23749008b726c6e7643a644.jpg)
Figure 4.17: 3m FX hedged yield pickup vs EUR for 10y JPY and EUR bond, in $\%$ Source: Bloomberg, Commerzbank Research

# Rolling Pickup One Period On' and for the Tenor of the Instrument

Now, let us look at what really happens in the case of rolling hedges. In the following figures, we plot the 3m rolling hedged pickup for the EURUsD case, for a 2y and 5y bond. This is the grey line. Then we plot the next quarter actual pickup (black line). This is of course the current one shifted by 3m. Finally, we plot the average. 3m-hedged pickup for the tenor of the bond - for the 5y case, this ends early, as we need 5y of data to get the result (Figures 4.18 and 4.19)..

![](3f807cb5fe6cd75787376e0b02e26c176c99538f2c4639393020b3d3cb3c16b2.jpg)
Figure 4.18: Rolling FX hedged yield pickup vs EUR for 2y USD bond, in $\%$ Source: Bloomberg, Commerzbank Research

It's crystal clear that the assumption that the yield pickup from one $3\mathrm{m}$ period to the next could remain constant is ridiculous. Over the life of the deal, the average pickup of course becomes smoother for the longer deal tenors, and reflects more of a slow variation in interest rate differentials. But once more, the idea that it can be forecast by looking at the first rolling pickup is absolutely unrealistic..

![](c2b0c5d124d629c703e20bea4dd3790836ea97d30923b5d43e304777ad8dfba7.jpg)
Figure 4.19: Rolling FX hedged yield pickup vs EUR for 5y USD bond, in $\%$ Source: Bloomberg, Commerzbank Research

# Translation Effect

Finally, we can take a look at the case where the investor crosses their fingers and hopes that they can harvest the interest rate differential of the bonds without hedging. To do this, we can simply reuse equation (4), as follows:

$$
{\mathrm{Yield~pickup}}=[B_{2}-B_{1}]-\left(1-\left[{\frac{F X}{F R_{n}}}\right]\right)/n
$$

The beauty of our somewhat novel way of writing the yield pickup in terms of the FX rates is that if we want to understand the impact of the 'no hedge' case, we simply replace the forward rate. $\mathrm{FR}_{\mathrm{n}}$ with the spot rate at the end of the period - we can call it $\mathrm{FX_{n}}$ It is only worth looking at the 2y case, as otherwise we have less data at the end of the period to view, but it makes the point very well indeed. We need different scales for the two returns to be visible on the same graph - the maximum range for the hedged pickup is just over $1\%$ , but this is nearer. $30\%$ for the unhedged. case.

This is not surprising, looking at the dynamics of the spot rate in that period. But it serves to underline that there are very good reasons for all the attention given to hedging the FX risk of fixed income instruments - not to do so exposes the investor to risk levels an order of magnitude larger (Figures 4.20 and 4.21).

Note that the last two years of the two-year return in these figures are of course unavailable.

![](53840382e2a381bb288ca9da0da479547c5eee6d64fb567790b30a472f09424e.jpg)
Figure 4.20: Maturity-matched FX hedged yield pickup vs EUR with unhedged return for 2y USD bond, in $\%$ Source: Bloomberg, Commerzbank Research

![](567793af89eb24da5536bcbec0b38230b867499ed4468099fad3a565108a6854.jpg)
Figure 4.21: EURUSD spot exchange rate. Source: Bloomberg, Commerzbank Research

# Volatility Breakdown -- What is Driving the Performance?

It is interesting to look at the contributions to the overall volatility of the various different returns. We can do this empirically by looking at the data, but also our. equation (4) can be used quite elegantly to show theoretically where the dominant. volatility sources originate.

We have

$$
{\mathrm{Yield~pickup}}=[B_{2}-B_{1}]-\left(1-\left[{\frac{F X}{F R_{n}}}\right]\right)/n
$$

Using normal propagation of error techniques, we know that if

$$
f=a X-b Y
$$

where $a$ and $b$ are constants, and $A$ and $B$ are the sources of variation, then

$$
\sigma_{f}=\sqrt{a^{2}\sigma_{X}^{2}+b^{2}\sigma_{Y}^{2}-2a b\sigma_{X Y}}
$$

where

$\upsigma_{\mathrm{f}}=$ standard deviation of function $f$ $\upsigma_{\mathrm{{X}}}$ and $\upsigma_{\mathrm{Y}}=$ standard deviation of function $X$ and function $Y$ $\boldsymbol{\upsigma}_{\mathrm{XY}}=$ covariance of function $X$ and function Y

So by expressing the yield pickup in the manner here where the yield differential and FX contributions are separated, we can set

$$
\begin{array}{l}{{\mathrm{X}=[B_{2}-B_{1}]\mathrm{(yield~differential)}}}\ {{\mathrm{}}}\ {{\mathrm{}\mathrm{a}=1}}\ {{\mathrm{Y}=\left(1-\left[\frac{F X}{F R_{n}}\right]\right)/\mathrm{n}\mathrm{(FX~term)}}}\end{array}
$$

$\mathsf{b}=1$ (but don't confuse $b$ with B1 and B2)

We have set $a$ and $b$ equal to 1 so that the contributions are clear to see. Note that if the two variables $X$ and $Y$ are relatively uncorrelated then the covariance will be close to zero (i.e., the sum of the contributions from the differential and the FX term will be roughly equal to the covariance term). In Table 4.1, we tabulate the volatility contributions for different tenors of USD pickup for a EUR-based investor for the differently hedged cases.

We show both the standard deviation (s.d.), which is the traditional measure of volatility, and the variance, which is the square of the volatility. Although the standard deviation is more familiar, the contributions from the yield differential and the FX component are delivered via equation (4) where the s.d. is the root of the sum of the squares of the contributions and the covariance term, whereas the variances are additive so are perhaps easier to understand. Note that there is no 30y FX hedge data available.

What is interesting in Table 4.1 is the fact that the contributions to the volatility. of the pickup from the yield differential and the FX term are very similar indeed, especially for the shorter-dated bonds. The FX term becomes more important for longer tenors, as might be expected. However, especially for the short-dated case, the covariance term is extremely important. If there was no covariance (i.e., no correlation), then the s.d. would be larger. The positive correlation of the yield differential and the FX term mean that overall, the yield pickup volatility is lower than it. might be. This is hardly surprising, as the FX term is derived from the hedge, which in an arbitrage-free world would reduce the pickup to zero..

Table 4.1: Volatility contributions for matched maturity FX hedge, USD bonds, data since 2000, in $\%$


<html><body><table><tr><td colspan="4">Standard Deviation (s.d.) and variance (var) of contributions to yield pickup</td></tr><tr><td></td><td>2Y</td><td>5Y 10Y</td><td>30Y</td></tr><tr><td>s.d. of pickup</td><td>0.18%</td><td>0.24% 0.48%</td><td>一</td></tr><tr><td>s.d.ofyielddifferential</td><td>1.20%</td><td>1.03% 0.81%</td><td></td></tr><tr><td>s.d.of FX term</td><td>1.13%</td><td>0.87% 0.84%</td><td></td></tr><tr><td>Covarterm</td><td>2.69%</td><td>1.75% 1.13%</td><td></td></tr><tr><td>var of pickup</td><td>0.03%</td><td>0.06% 0.23%</td><td>-</td></tr><tr><td>var ofyielddifferential</td><td>1.44%</td><td>1.05% 0.65%</td><td></td></tr><tr><td>varofFXterm</td><td>1.29%</td><td>0.76% 0.71%</td><td></td></tr><tr><td>Covarterm</td><td>2.69%</td><td>1.75% 1.13%</td><td></td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

Table 4.2: Volatility contributions for rolling FX hedge, USD bonds, data since 2o00, in $\%$


<html><body><table><tr><td colspan="4">Standard Deviation (s.d.) and variance (var) of contributions to yield pickup</td></tr><tr><td></td><td>2Y 5Y</td><td>10Y</td><td>30Y</td></tr><tr><td>s.d. of pickup</td><td>0.44% 0.68%</td><td>0.82%</td><td>1.00%</td></tr><tr><td>s.d.ofyielddifferential</td><td>1.20% 1.03%</td><td>0.81%</td><td>0.68%</td></tr><tr><td>s.d. of FX term</td><td>1.30% 1.30%</td><td>1.30%</td><td>1.30%</td></tr><tr><td>Covar term</td><td>2.94% 2.29%</td><td>1.67%</td><td>1.17%</td></tr><tr><td>var of pickup</td><td>0.19% 0.46%</td><td>0.68%</td><td>1.00%</td></tr><tr><td>varofyielddifferential</td><td>1.44% 1.05%</td><td>0.65%</td><td>0.46%</td></tr><tr><td>varofFXterm</td><td>1.70% 1.70%</td><td>1.70%</td><td>1.70%</td></tr><tr><td>Covarterm</td><td>2.94%</td><td>2.29% 1.67%</td><td>1.17%</td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

Next, in Table 4.2, we show the same table for the rolling hedge. Here, also, the. covariance term is important. In this case, however, the FX term is relatively more important than the yield differential. Note that the FX term is the same in all cases, as they are all hedged with the rolling 3m strategy..

Finally, in Table 4.3, we show the unhedged case. Here, covariance is irrelevant, as everything is dominated by the FX volatility. This emphasises our point about the translation effect - the risks of not hedging dwarf any residual risks from an FX hedged strategy, no matter what it is.

Table 4.3: Volatility contributions for unhedged case, USD bonds, data since 2000, in $\%$


<html><body><table><tr><td colspan="4">Standard Deviation (s.d.) and variance (var) of contributions to yield pickup</td></tr><tr><td></td><td>2Y 5Y</td><td>10Y</td><td>30Y</td></tr><tr><td>s.d. of pickup</td><td>6.43% 3.54%</td><td>1.97%</td><td>一</td></tr><tr><td>s.d.ofyielddifferential</td><td>1.20% 1.03%</td><td>0.81%</td><td></td></tr><tr><td>s.d.of FX term</td><td>6.32%</td><td>3.45% 1.85%</td><td></td></tr><tr><td>Covarterm</td><td>-0.05%</td><td>0.41% 0.21%</td><td></td></tr><tr><td>var of pickup</td><td>41.38%</td><td>12.54% 3.87%</td><td></td></tr><tr><td>varofyielddifferential</td><td>1.44%</td><td>1.05% 0.65%</td><td></td></tr><tr><td>varofFXterm</td><td>39.89%</td><td>11.90% 3.43%</td><td></td></tr><tr><td>Covar term</td><td>-0.05%</td><td>0.41% 0.21%</td><td></td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

# Numerical Example

For those who would like to replicate some of these calculations, we give a detailed example in Table 4.4 (base data) and Table 4.5.

Table 4.4: Base data for calculation.


<html><body><table><tr><td></td><td colspan="2">GovtBond</td><td colspan="2">Swap Rate</td><td>FX xccy basis to Euro</td></tr><tr><td></td><td>Germany</td><td>USA</td><td>Germany</td><td>USA</td><td>USA</td></tr><tr><td>Tenor</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>3M</td><td></td><td></td><td>-0.318</td><td>0.953</td><td>-49.993</td></tr><tr><td>2Y</td><td>-0.731</td><td>1.1102</td><td>-0.268</td><td>1.326</td><td>-44.250</td></tr><tr><td>5Y</td><td>-0.396</td><td>1.8374</td><td>0.007</td><td>1.828</td><td>-44.500</td></tr><tr><td>10Y</td><td>0.382</td><td>2.4071</td><td>0.65</td><td>2.249</td><td>-43.125</td></tr><tr><td>30Y</td><td>1.125</td><td>3.1053</td><td>1.306</td><td>2.557</td><td>-24.250</td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

Note that the EUR swap rate in Table 4.4 is vs the 3m floating rate to match the US data. Using this data set, we construct a set of yield pickups in Table 4.5.

Table 4.5: Pickup results, 8th December 2016.


<html><body><table><tr><td></td><td colspan="3">YieldPickup</td></tr><tr><td></td><td colspan="3">USA</td></tr><tr><td>FXHedge</td><td>None</td><td>Rolling</td><td>Maturity matched</td></tr><tr><td>Tenor</td><td></td><td></td><td></td></tr><tr><td>2Y</td><td>1.84</td><td>0.07</td><td>-0.195</td></tr><tr><td>5Y</td><td>2.23</td><td>0.46</td><td>-0.032</td></tr><tr><td>10Y</td><td>2.03</td><td>0.25</td><td>-0.005</td></tr><tr><td>30Y</td><td>1.98</td><td>0.21</td><td>0.487</td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

Let's go through the top line of the pickup in Table 4.5 in detail.

1.84 is simply the difference between the EUR and USD government bond rates for the 2y tenor, so

$$
1.84=1.11-(-0.73)
$$

Then to this we can add the rolling hedge cost, which is the difference between the two swap rates, plus the cross-currency basis:

$$
0.07=1.84+\left(-0.318-0.953\right)+\left(-49.99\big/100\right)
$$

Note that the cross-currency basis swap number needs to be divided by 100, as it is quoted differently in Bloomberg.

Or we can use the maturity-matched hedge, as follows:

$$
-0.19=1.84+\left(-0.268-1.326\right)+\left(-44.25/100\right)
$$
