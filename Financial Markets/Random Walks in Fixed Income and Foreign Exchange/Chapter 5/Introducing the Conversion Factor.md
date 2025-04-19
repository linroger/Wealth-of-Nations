---
tags:
  - conversion_factor
  - credit_spread
  - cross_currency
  - issuer_choices
  - yield_curve
aliases:
  - Conversion Factor
  - Issuer's Choices
key_concepts:
  - Conversion factor definition
  - Credit spread impact
  - Cross-currency basis effect
  - Issuer's decision factors
  - Tenor and currency
---

# Chapter 5 Introducing the Conversion Factor

Maybe you've never heard of the conversion factor.' You are in good company;. many of my colleagues had not, and it was news to me when I first investigated it a few years ago. Though it isn't a new concept, it is a surprising and somewhat unexpected consequence of combining credit spreads with different yield curves, and. has significant consequences for issuers and investors..

# The Issuer's Choices

When choosing to issue, the modern treasurer has a bewildering set of choices. The following is a simplified list of the various decisions that the issuer needs to make before settling on a currency of issue..

# Tenor

Internal needs will determine the tenor of the issue. But this choice may eliminate some currencies in which certain tenors are more readily available for historical reasons. In most cases, the currency of choice, however, is not independent from the companies' operating environment, with FX debt often met by operating income sources in the same currency, reducing the need to hedge cash flows.

# Credit Spread

This is perhaps the critical question. The credit spread is typically defined as the difference between the interest rate on a corporate's bond, and the interest rate of. the swap curve in the same currency. It can vary from one currency to another. Usually, credit spreads will be somewhat wider for currencies that are not the home currency of the corporate, but this may not be so for large multinationals, or sometimes specific industries. Central banks directly intervening in corporate bond markets can introduce another distorting factor. If a cheaper borrowing rate relative to the. local market is available in a different currency, it is worth a look..

# Cross-Currency Basis

If there were no cross-currency basis, then this would have the effect of eliminating. any difference in the local and foreign swap curves, leaving only the spread factor. However, the existence of the basis means that the rates at which FX hedges can be done are not exactly those which eliminate this difference; they can be as large as $1\%$ different, and are often $0.5\%$ different. So the basis may enhance the spread ef-. fect or reduce it.

# Conversion Factor

This factor is often the one that no one has ever heard of! We discuss the conversion factor in more detail in the following section, as it is a factor which ranges from very close to zero to about $10\%$ , and is applied to the spread. It is due to different yield curves in the different currencies.

# Fees and Charges

Capital costs, regulatory issues and XVA charges mean that fees are complex to calculate and depend at least partly on the relative credit rating of the banks managing. the issue and the corporation issuing the bond. In this chapter, we ignore these. charges but it is worth noting that they can be significant..

# What is the Conversion Factor?

The conversion factor comes from the relative cost of credit in different yield environments and the structure of interest rates for the two currencies in question. It is not connected with the FX rate between the two currencies, but is purely a function of the level of interest rates and the shapes of the yield curve.

(1) The conversion factor is the number of basis point per annum in one currency, which equals 1 basis point in the other currency.
(2) The conversion factor is the factor which equates the PV's of identical future cashflows in different currencies.

It arises because credit spreads in the post-crisis world are so much more significant than they were before. A highly rated corporate whose credit spread is close to zero (that is, it can borrow at a rate close to the prevailing local swap rate in the market) need not worry about conversion factors. As long as its bonds are highly rated in both its home currency and the currency it wants to issue debt in, then nothing more is needed, and the cross-currency basis swap level will be the only significant consideration.

However, this may not be the case! A credit spread of some hundred basis points is nothing unusual for some issuers, and this is where the conversion factor becomes important.

We can think about the issuance situation of a corporate with a large credit. spread either as a completely different yield curve, or as the local swap curve with. a factor added on. As the latter is the market convention, the conversion factor arises as an approximation to the perhaps more mathematically correct approach. of using issuer-specific yield curves and forward rates for each currency under. consideration.

# Simplest Possible Example - 1-Year Bond, Zero Basis, USD Corporate

Let's take a look at an unrealistic but simple example for the sake of clarity.

EUR issue - swap rate $1\%$ , credit spread $2\%$ , thus coupon $=3\%$ USD issue - swap rate $5\%$ , credit spread $2\%$ , thus coupon $=7\%$ The single coupon is paid at the end of the year.

If we assume that the basis is zero, then the corporate cannot gain an advantage by issuing in Europe where rates are lower, and then hedging the FX risk. The US corporate, if it hedges the FX risk it acquires by issuing at. $1\%$ in EUR, will come back to. the home value of $5\%$ via the FX hedge.

Now, as the credit spreads are the same, there should be no difference between issuing in either currency, right? Wrong!

We need to think about the Present Value (PV) of the credit spread. In EUR, we would discount the spread using the. $1\%$ swap rate - so ignoring any day count issues and assuming that all rates are in annual terms, we have.

$$
P V_{E U R}=\frac{2\%}{1+1\%}=1.98\%
$$

However, in UsD, there is a different swap rate, so we have

$$
P V_{U S D}=\frac{2\%}{1+5\%}=1.90\%
$$

To equate the two PVs, we must increase the USD spread by a factor of $1.98\%/1.90\%=$ 1.039. This is the conversion factor. So now the total UsD spread is $2.08\%$ , from the point of view of the EUR corporate..

So this means that unless the corporate can find an advantage of more than 8bp from other factors, it's not worth issuing in USD. If, for example, the credit spread were lower in USD, at perhaps $1\%$ , then indeed it could be worth doing, though the

conversion factor would eat into that differential, transforming the effective EUR credit spread to $1.04\%$ from the point of view of the EUR issuer.

# More Realistic - Using the Yield Curve

If only life were as simple as this example. But bonds pay coupons at different frequencies, and swap rates vary with the tenor. What's important to realise is that you have to find the relevant conversion factor for the coupon stream of the bond. Not only does the conversion factor vary with the tenor, but it will also vary with the payment frequency (though to a lesser extent). So although it's popular to quote a 10y conversion factor, it should strictly be a 10y conversion factor for annual payments'. Let's have a look at these features.

The easiest way to calculate the conversion factor between two cashflow streams. is to look at the PV of the sum of 1 basis point at each payment date in each currency.. In practice, this is as simple as calculating a discount factor for each payment date, adding them up for each currency, and taking the ratio of the sum. An example is shown in Table 5.1.

As can be seen, the longer dated conversion factor can add another $9\%$ Of spread value to the total cost of the issuance at the current time.

It is easy to check the calculation - for the 5-year conversion factor for annual. payments, add up the first 5 discount factors for each currency and divide the USD. result by the EUR result. However, if we do the calculation for 6-month payments (out only to 5 years this time to fit the data in!), then the results are slightly differ-. ent. See Table 5.2 which illustrates this point..

If we compare the 5y conversion factor in both tables, we see that it is 1.0524 for. the annual payment case, and 1.0525 for the semi-annual payment case. Though very small for these low-interest rate environments, for longer tenors and higher differentials, it could become more significant..

# Another Way to Think about It

Why does the conversion factor arise? One final way in which it might be useful to think of it is a consequence of the individual credit curve of a corporate vs the swap. curve. Forward FX rates, and indeed all FX hedge valuations, are calculated using. the swap curves in different currencies. But the credit curve of a corporate will (al-. most always) trade above the swap curve. So the FX hedge cost does not take into account this differential, which is the credit spread. If it did, we would have no need to calculate conversion factors. But then different companies would have different forward rates and liquidity for any single credit curve would be very low. It is.

<html><body><table><tr><td>10Y N 9 Z Date</td><td>2.3564 2.3087 2.2529 2.0266 1.9203 1.7875 1.6185 1.4042 Swap Rates</td><td>07/04/2027 0.8220 07/04/2026 0.8415 07/04/2025 0.8611 07/04/2024 0.8808 07/04/2023 0.9005 07/04/2022 0.9199 07/04/2021 0.9338 07/04/2020 0.9570 07/04/2019 0.9739 07/04/2018 0.9886 07-Apr-17 Friday DiscountFactor</td><td>EUR</td><td>10Y N Date</td><td>0.7360 0.6270 0.5160 0.1550 0.0320 -0.0650 -0.1535 -0.2210 Swap Rates</td><td>07/04/2027 07/04/2026 07/04/2025 07/04/2024 07/04/2023 07/04/2022 07/04/2021 07/04/2020 07/04/2019 07/04/2018 07-Apr-17 Friday</td><td>0.9497 1.0908 0.9647 1.0844 0.9782 1.0774 0.9896 1.0697 0.9983 1.0613 1.0043 1.0524 1.0072 1.0431 1.0076 1.0335 1.0063 1.0241 1.0035 1.0151 ConversionFactor DiscountFactor</td></tr></table></body></html>

<html><body><table><tr><td rowspan="5">USD</td><td rowspan="8">66M 54M 42M 30M Z 18M Date</td><td rowspan="8">07/04/2027 07/04/2026 2.0266 07/04/2025 07/04/2024 1.9203 07/04/2023 07/04/2022 1.7875 07/04/2021 07/04/2020 1.6185 07/10/2019 07/04/2018 1.4042 07-Apr-17 Friday Swap Rates</td><td rowspan="8">0.9103 0.9199 0.9294 0.9388 0.9480 0.9570 0.9656 0.9739 0.9816 0.9886 DiscountFactor</td><td rowspan="8">66M 54M 42M 30M 18M EUR Date</td><td rowspan="8">0.1550 0.0320 -0.0650 -0.1535 -0.2210 Swap Rates</td><td rowspan="8">07/04/2027 07/04/2026 07/04/2025 07/04/2024 07/04/2023 07/04/2022 07/04/2021 07/04/2020 07/10/2019 07/04/2018 07-Apr-17 Friday</td><td rowspan="8">DiscountFactor</td><td rowspan="8">1.0017 1.0043 1.0061 1.0077 1.0076 1.0050 1.0035</td><td></td><td>1.0571 1.0525</td><td></td></tr><tr><td>1.0478 1.0431</td></tr><tr><td>1.0072</td></tr><tr><td>1.0383 1.0335</td></tr><tr><td></td></tr><tr><td>1.0071 1.0287 1.0063 1.0240</td></tr><tr><td>1.0194</td></tr><tr><td>1.0151 ConversionFactor</td></tr></table></body></html>

far better to calculate all hedges using the highly liquid swap curve and then separately account for credit spreads using conversion factors.

Still, we need to keep in mind that conversion factors calculated from swap. rates remain only an approximation, as the shape of the credit curves can vary as. well in the currencies under consideration. So theoretically, even if the swap rates. were the same in both currencies - that is, the calculated conversion factors were equal to 1 - the PVs of future cashflows in different currencies can vary..

# Examples of Conversion Factors

In the following Figures 5.1-5.4, we have plotted conversion factors for different currencies over time. DF denotes Discount Factor, so the reader can recalculate if desired.

![](41bd4ec70d2c3ed61242a86c7e930c0e01af58b9bc1671440c7802ca39ca42bd.jpg)
Figure 5.1: EURUSD conversion factor. Source: Commerzbank, Bloomberg.

It's clear that the conversion factor is affected by most events that impact perceptions. of the future yield environment. The EURcHF peg break is clear in early January 2015,. while the late 2016 election in the USA had a strong influence on the EURUsD factor given the sharp re-pricing of the US curve..

# Forecasting Conversion Factors

It could be useful for corporates to have some forecasts of conversion factor levels. For-. tunately, if we have forecasts available of market interest rates, we can use these to create discount factors (if the forecast rates curves are smooth enough), and from these, we can quickly derive the conversion factors. Ideally we would have rates forecast at every annual tenor to create the discount factors, but in reality, forecasts often miss out interim tenors like 7y and 8y. When this is the case, we linearly interpolate the rates to use in the discount factor calculation.

![](1b003006fba5450c2efa7491c80af2b46f633cf9c9896670e45404488ee719fd.jpg)
Figure 5.2: GBPUSD conversion factor. Source: Commerzbank, Bloomberg

![](7b1ff1d59ae518bb3d599ada144263e3dc0f21aee6a900b0b8cc09724a97942f.jpg)
Figure 5.3: EURCHF conversion factor. Source: Commerzbank, Bloomberg

While this is not a method that would be used in an accurate valuation scenario. (which would also use Libor rates, spreads, FRAs and so on), in this case it is probably. accurate enough. In Figures 5.5 and 5.6 we show the accurate discount curve from a test data set (created using Commerzbank's in-house valuation software DIVA) and the

![](8cc047365b7722a4defb3de1d0dd463d45f936e4c0060c83d414e7a6214aeb74.jpg)
Figure 5.4: GBPJPY conversion factor. Source: Commerzbank, Bloomberg

![](b869409145e269dbdd2bb36f6a3dadb05fb46de223065e0c31d3900c2f2afdd3.jpg)
Figure 5.5: Discount factor comparison. Source: Commerzbank, Bloomberg.

# e(GBP DF)/z(EUR DF)

Figure 5.6: Underlying data (sparse set to mimic). Source: Commerzbank, Bloomberg


<html><body><table><tr><td>12m</td><td>2y</td><td>5y</td><td>10y</td></tr><tr><td>1.11%</td><td>1.58%</td><td>1.70%</td><td>1.80%</td></tr></table></body></html>

approximate one, using the method which we also use for the forecasts. As can be seen, they are very close. The approximation formula for the discount factor (DF) for an n-year point which we use can be seen here, where ${\mathfrak{r}}_{\mathrm{n}}$ is the n-year interest rate.2

$$
D F_{n}=\frac{1-r_{n}\sum_{i=1}^{i=n-1}D F_{i}}{1+r_{n}}
$$

Because a set of forecast data is rarely complete, we used the 4 rates here as our test forecast rates and interpolated linearly as needed to create the discount factors. It is very close to the accurate method using the same data set.

Now we can proceed to use our Commerzbank forecast data to create a set of discount factors and conversion factors (Table 5.4). At the time of writing in 2017, we did not know how accurate the forecasts would be. Now, however, in 2020, we have the opportunity to see how well they worked!

Table 5.3 shows the forecasts as of April 2017 for EUR OIS and IRS levels, for end 2017 and end 2018.

Table 5.3: OIS and IRS Commerzbank forecasts, as of April 2017, rates in $\%$


<html><body><table><tr><td></td><td>12m</td><td>2y 3y</td><td>4y</td><td>5y</td><td>6y</td><td>7y</td><td>8y</td><td>9y</td><td>10y</td></tr><tr><td>EURend2017</td><td>-0.35%</td><td>0.00%</td><td>60.10%0.20%</td><td></td><td>0.30%</td><td>60.43%0.56%</td><td>0.69%</td><td></td><td>60.82%0.95%</td></tr><tr><td>EURend2017</td><td></td><td>-0.20%0.15%</td><td>0.25%0.35%</td><td></td><td></td><td>0.45%0.64%0.83%</td><td></td><td></td><td>1.02%1.21%1.40%</td></tr><tr><td>USDend2018</td><td></td><td>1.65% 2.05%</td><td></td><td>2.23%2.42%2.60%</td><td></td><td>2.61%2.62%</td><td>2.63%</td><td></td><td>2.64% 2.65%</td></tr><tr><td>USDend2018</td><td></td><td></td><td></td><td></td><td></td><td>2.35%2.70%2.78%2.87%2.95%2.95%2.95%2.95%2.95%2.95%</td><td></td><td></td><td></td></tr></table></body></html>

Source: Commerzbank, Bloomberg

These forecast factors are substantial; the longer tenors are introducing an additional $10\%$ to spread costs, which is at the highs of previous historical results. For corporates with substantial credit spreads, this is very much worth considering.

The graphs in Figures 5.7 and 5.8 show the forecast conversion factors by tenor, for end 2017 and end 2018 (in Figure 5.7), and we also combine this data with the previous historical data for the 10y conversion factor in Figure 5.8. We see that in April 2017, the conversion factor was forecast to rise to much higher levels. What actually happened, though? Well, at the current time of writing, we are able to see how well the forecast did - and the answer is: quite well! The black line on the same graph reveals that for once, the future was fairly well-predicted.

Obviously, we can't generalise from this single instance, but clearly this method of forecasting conversion factors works at least some of the time .

-.....................................................-........ 110 %96:10 %08101 %89101 %8110 %99110 %68300 %0010 %08:100 %92110 %08:310 %80110 %79001 .....-.......-.......- peye At d



<html><body><table><tr><td>10y</td><td>9 92.79% 94.58%</td><td rowspan="11">8</td></tr><tr><td></td><td>89.50% 78.99% 92.06% 81.15%</td></tr><tr><td>96.13% ></td><td>94.31% 83.35%</td></tr><tr><td>97.44%</td><td>96.21% 85.59%</td></tr><tr><td>98.51% 5 99.20%</td><td>97.77% 97.87% 86.42%</td></tr><tr><td>4 99.70% 3</td><td>98.61% 90.85% 89.28% 92.08%</td></tr><tr><td>Z 12m</td><td>99.25% 93.57% 96.01% 94.80%</td></tr><tr><td>w6 6m</td><td>99.70%</td></tr><tr><td rowspan="4">3m</td><td>98.38%</td></tr><tr><td>EUR 1yahead100.09%100.18%100.26%100.35%100.00% 98.89%</td></tr><tr><td>99.28%</td></tr><tr><td>98.91% 99.65% 99.45%</td></tr></table></body></html>

![](3ef7cdd665eff8dc09528c19892a2fa6430caed8a9c3d91e2c48155ea91fc54d.jpg)
Figure 5.7: Forecast conversion factors, by tenor. Source: Commerzbank, Bloomberg

![](e1ae746228773eb3003934d1795836d14cd65e38ea7e7d5bc0e5b720fefa1a39.jpg)
Figure 5.8: 10y EURUsD conversion factor, history and forecast. Source: Commerzbank, Bloomberge

# Translating Spreads across Currencies

We have said that the conversion factor affects the credit spread available to issuers.
who issue in non-domestic currencies, but how exactly does this work? Let us consider the case of a EUR issuer who would like to know how their credit spread.
would translate if they issued in UsD. To calculate what an additional spread for.
the USD asset on the USD curve would look like when translated back to EUR, we.
must add the USD spread, modified by the 1Oy conversion factor, to the basis..

Spread usD investment (EUR) $=$ Spread usD investment (USD)/Conversion Factor $^+$ basis

Clearly, as the spread increases, the conversion factor term becomes more important, but when spreads are close to zero, the basis is the only thing that matters. We illustrate this graphically in Figure 5.9.

![](1163676ed660c994278f38f652d7a6391615d2caf89338524ff919eb0dea43be.jpg)
Figure 5.9: Xccy basis and conversion factor currency decision for 2 spreads. Source: Commerzbank, Bloomberg

When SpreadusD investment (EUR) is less than Spreadusd investment (USD), the EUR will be the preferred investment on a currency-adjusted basis. Given that the basis is generally negative, looking at the left-hand graph, we see that for the case of low spreads, the EUR asset will be preferred..

From the right-hand graph, we can see the effect of introducing a credit spread. on the USD asset. The conversion factor now enters and its importance increases with. the credit spread; in Figure 5.10, we repeat the analysis for multiple values of Spread (USD) - suddenly, with this graph, the investor can make an informed choice about. currency, taking into account credit spread, conversion factor and the value of the xccy basis. The different lines on the chart are the borderlines between the USD or EUR asset being more favourable.

Today, we are in the top-right quadrant in the area of EUR preference. The num-. bers correspond to time periods indicated in Figure 5.11. Not only can these charts guide the investment decision in the current moment, but they can also help include views on the future. How does the investor expect spreads, the basis, and the curves to evolve? They can study the chart and decide which currency is preferred. We see for example that the current situation is well within the EUR preference zone, and there would have to be a substantial change in multiple parameters to. mean that the EUR choice was not the right one. For example, the conversion factor could become smaller than 1 - but that would entail the EUR yield curve being. higher than the UsD one, which is absolutely unlikely in the medium-term. Or the

EUR is preferred above and to the left of the lines. Lines indicate different USD credit spreads

![](dce74c5abf76ef15d3baf06b01ac175521c24743d4d41d32e56453d3f570152a.jpg)
Figure 5.10: Xccy basis and conversion factor currency decision for multiple spreads. Source: Commerzbank, Bloomberg

xccy basis could change sign, but that has never been the case except very briefly and to a tiny degree in 2014.

We should note that some of the areas of the graph are unlikely ever to be 'occupied' - would we ever see a strongly positive basis, for example, with a conversion factor less than 1? But if the market ever gets there, this chart can still be used to judge which currency to select.

We can compare the graph in Figure 5.10 to the time series in Figure 5.11. The numbers which match those in Figure 5.10 indicate which conditions prevailed at different times.

A degree of offset, not always apparent but worth remarking upon, is observ-. able between the conversion factor and the basis, and is particularly apparent at the current time; the drivers of this behaviour would be interesting to explore..

![](8fb184b2c311d8286b34e3cd94e973060bdff41af3141ac13e628c9d3f850f6b.jpg)
Figure 5.11: Xccy basis and conversion factor currency decision time series. Source: Commerzbank, Bloomberge
