---
tags:
  - arbitrage
  - cross_currency_basis
  - currency_risk
  - fx_forward
  - interest_rates
aliases:
  - XCCY basis
  - basis
  - cross-currency basis swaps
key_concepts:
  - arbitrage conditions violation
  - cross-currency swap
  - currency hedging adjustment
  - forward FX rate
  - interest rate differentials
---

# Chapter 1 What Really is the Cross-Currency Basis?

The cross-currency basis - often just called the basis' - is a strange creature.' It is. referred to often enough in the financial markets that most participants think that they probably ought to know what it is. I was certainly one of them. 'Some credit. adjustment to currency hedging' was how I vaguely thought of it. However, the more one studies and understands it, the stranger and more important it becomes. It is nothing less than a violation of the arbitrage conditions governing the relationships between interest rates and foreign exchange rates, and before it was observed, it would have been thought of as impossible. This paper describes how to calculate the basis, discusses some potential drivers, and ends with some unexpected applications.

The story of cross-currency basis swaps originates with the start of the floating. currency market regime in the late 1970s and early 1980s, as corporations and in-. vestors with global reach sought methods of insuring themselves against sharp currency movements. Forward FX rate contracts became popular. The forward rate calculation is trivial (see equation (1)), and any deviation in the market from the calculated rate implied by interest rate differentials gives traders a chance to do arbitrage trades, which made such deviations unlikely..

And yet, since 2o08, such deviations have persistently emerged. It is these deviations, expressed in a spread to one of the Libor interest rates used to calculate the forward FX rate, which are known as the cross-currency bases. We plot the basis for EURUsD in Figure 1.1; it is remarkable how large and persistent it can be, given that before 2008, arbitrage activity maintained it at almost zero.

# The Calculation Underlying the Cross-Currency Basis Swap

A Quick Note on Terminology

An FX forward is a contract that locks in the price at which a counterparty can buy.
or sell a currency on a future date. The exchange rate is typically today's rate, ad-.
justed for the interest rate differential in the two currencies. If the interest rate in the local currency is higher than that of the UsD (or whatever the reference currency.
is), the FX forward will include a devaluation expectation..

![](b45f67bf50395a754e0752005806eeb6c71148300f252eab7242edae737b5a78.jpg)
Figure 1.1: 1y EURUSD xccy basis.. Source: Commerzbank Research, Bloomberg

In a cross-currency swap, the parties exchange a stream of cashflows in one cur-. rency for a stream of cashflows in another. The typical cross-currency swap involves. the exchange of both recurring interest and principal (usually at the end of the swap), and thus can fully cover the currency risk of a loan transaction. Conceptu-. ally, cross-currency swaps can be viewed as a series of forward contracts packaged. together. For much more detail on more of these, see Appendix 1.B..

# Perhaps the Simplest Formula in Financial Mathematics

The calculation to discover the forward rate is trivial. It is found using the following expression:

$$
{\frac{F}{S}}={\frac{1+r_{f}}{1+r_{d}}}
$$

where $F$ is the forward FX rate, $S$ is the spot (current) FX rate, $\mathbf{r_{f}}$ is the foreign interest rate and $\mathrm{r_{d}}$ is the domestic interest rate. The FX rate must be quoted as units of foreign currency per domestic currency - for example, 1.1 USD (US dollar) per EUR (Euro). EURUsD is the conventional way of naming this rate in the market.

This calculation arises very simply. There are two ways of getting from holding. the domestic currency now, to holding the foreign currency in the future, illustrated in Figure 1.2.

Method 1. Invest now for the period in question, at the domestic interest rate, then exchange at the end of the period..

Method 2. Exchange now so that you hold the foreign currency, and invest at the foreign currency rate for the period.

![](f38f00f97727e1ca1ee7f378cfe653034a9945b080419f551234687a9ed4098f.jpg)
Figure 1.2: Forward FX rate calculation.

Arbitrage pricing would tell us that Method 1 and Method 2 must be exactly the. same, apart from perhaps some small trading spread effects, or there will be a chance to 'round trip' the system and make some risk-free money (arbitrage). Conventionally, and in the pre-crisis world, this will only occur in a small and transient manner, as sharp-eyed traders look out for the chance and thus keep pressure on the forward. rate to comply with equation (1).

This type of situation has traditionally (pre-crisis) arisen in small and temporary forms, quickly eliminated by arbitrage trading. Thus this method of calculating the forward rate was thought to be completely robust. How could it possibly be incorrect in any substantial way?

But as we will see, even this apparently unbreakable piece of mathematics is vulnerable to unforeseen market effects. The existence of a non-zero cross-currency basis 'breaks' equation (1).

# How the Calculation Distorts No-Arbitrage Pricing

The relationship in equation (1) is protected by arbitrage constraints, which one would think, in this era where both humans and machines comb the market for strategies and opportunities, would be sufficient to ensure its integrity. However, market size and liquidity are not enough to ensure perfect efficiency. In Appendix 1.A, we show that the FX market has by some definitions been markedly inefficient since its origins as a floating rate, by allowing a profitable carry trade to persist. And we can present simple evidence that an acute distortion of equation (1) has occurred and moreover persists to this day.

Let us go back to the equation.

$$
{\frac{F}{S}}={\frac{1+r_{f}}{1+r_{d}}}
$$

If EUR is the domestic currency, and USD the foreign currency, then a quick rearrangement gives us the following equation:

$$
r_{d}={\frac{S}{F}}\times\left(1+r_{f}\right)-1
$$

Now, all of these rates are readily observable in the market. To check it out precisely, we calculated $\mathrm{r_{d}}$ using equation (2), and compared it to the market rate since. 2000. Before about 2008, the calculated value of $\mathrm{r_{d}}$ matches the value of $\mathrm{r_{d}}$ obtained from the time series EUsw1v3 Curncy (on Bloomberg), the EUR 1-year swap rate. But after that date, they vary considerably, sometimes by up to. $1\%$ . If we plot the difference in Figure 1.3, calculated using $\mathrm{r_{d}}.$ theoretical $\mathrm{~-~}\mathbf{r}_{\mathrm{d-market}}$ , then we obtain the grey line. We have added to the graph the quoted xccy (shorthand for crosscurrency) EURUSD 1y basis swap (black line)..

The degree to which the arbitrage pricing is violated is almost exactly equal to the market quantity known as the cross-currency basis swap.

![](c767ba8afc9f7592467f32bad36092f7cfb8055a18c3bf2578d233cc994d41c3.jpg)
Figure 1.3: Theoretical and actual EUR interest rate difference. Source: Commerzbank Research, Bloomberge

It's clear to see that apart from a few not-so-good data points, they are essentially the same. So what is going on?

Essentially, equation (1) is no longer holding, and has not held since 2008, even between EUR and USD, the world's largest currencies. This degree of violation is called the 'basis' or 'basis swap' and it is expressed as the difference between the non-USD interest rate (in this case, the 1-year EUR swap rate) implied by the FX forward, and the actual market value of this rate.

Here's a quick example taken from one of the more extreme recent periods (grey circle in the graph in Figure 1.3). The codes are the Bloomberg tickers for the rates, so that the interested reader can check the calculation.

# On 29th December 2011

EUR-USD xccy basis $=101.9\mathrm{bp}$ (EUBS1 Curncy) EURUSD spot FX rate $=1.296$ (EURUSD Curncy) EUR 1y swap rate $=1.094\%$ (EUSW1V3 Curncy) USD 1y swap rate $=0.691\%$ (USSA1 Curncy) EURUSD 1y FX forward $=1.304$ (EUR12m Index)

Using equation (2), we calculate the theoretical' EUR 1y swap rate as follows:
EUR 1y swap rate (theoretical) $\begin{array}{r}{=r_{d}=\frac{S}{F}\times\left(1+r_{f}\right)-1=1.296/1.304\times\left(1+0.691\%\right)-1}\end{array}$
EUR 1y swap rate (theoretical) $=0.073\%$
But the actual swap rate is not $0.0733\%$ , it is $1.094\%$ . The difference is
$0.073\%-1.094\%=-1.021\%=-102.1\mathrm{bp}$
And this is almost exactly equal to the quoted basis in the market, $-1.019\%$

Of course, that is not the only way to express the inequality. We could equally well plot the difference between the theoretical FX forward rate, derived from the spot rate and the interest rates available in the market, and the actual quoted rate, Ftheoretical $\begin{array}{r}{-\mathrm{F}_{\mathrm{market}}.}\end{array}$ Then we would create the following graph, as shown in Figure 1.4.

![](29f332a5430e03e9dc96f00b0038f9a2f8ee09eabe83dd8f547d15f97e56bf40.jpg)
Figure 1.4: Forward difference.. Source: Commerzbank Research, Bloomberg

And if we wanted, we could rotate the whole situation once more and arrive at a spot FX rate difference. Though this is probably not the best way to view the issue, a shift to the spot rate would be just as valid to explain the market mismatch.

We have illustrated the situation using the 1-year rates, only because they involve the least amount of arithmetic. But one may exactly repeat this analysis for tenors from $3\mathrm{m}$ to 30y, and the same relationships will hold. So however we look at it, the forward rate calculation is broken, and not even in a transient way - the basis seems to have moved in and is here to stay!

# So, What Actually is a 'Cross-Currency Basis Swap'?

It's worth explaining exactly what this means, and also what is meant when folks refer simply to the basis'. A cross-currency basis swap (often abbreviated to 'xccy basis swap') can formally be set out as in Figure 1.5. Here, we assume that an institution starts off with EUR funding, which it converts with a basis swap to USD funding. This could be a EUR-based issuer that has sold a EUR bond locally, and so already has EUR bond cashflows such as coupon and redemption, but would rather convert them to USD. Practically, most sub-1-year hedging is done using currency forwards (a single exchange at the final date), whereas longer term hedging tends to be done using swaps (final exchange plus interim interest rate exchanges).

The central figure is the contract known as the cross-currency basis swap, where. there are initial and final exchanges of capital (both at the spot exchange rate at the. start of the deal) and interim floating rate interest rate exchanges. At the start of. the deal, both currency legs will have the same value, but of course as FX rates vary, the value of the deal can change. Variations in interest rates will have only a small effect as the interest rate cashflows are all floating; the 'next' coupon is the only one which is known and fixed..

The quantity often somewhat confusingly referred to as the basis' is an adjustment to the central basis swap agreement. The basis is the result of supply and demand for USD cashflows. Strong demand for USD cashflows means that the EURIBOR interest rate available for the deal is not the one which will make the PV of the EUR and the UsD legs equal; it is a little less, and this difference is the basis. It is exactly what we calculated in equation (2). The reader can already see that a basis which can be larger than $1\%$ will be highly significant to issuers and investors.

# Conversion Factor

Before we go on to discuss the various drivers of the cross-currency basis, it is worth introducing one more effect that is often neglected. When we discuss the motivations of issuers and investors, the cost of issuance is strongly influenced by one

![](0ffca411d5c491dbe219edee6d5e8260c981ff7431de61de0a9a2cf6061d937b.jpg)
Figure 1.5: Cross-currency basis swap. Source: Commerzbank Research

additional item: the conversion factor. The conversion factor is the number of basis points per annum in one currency that equates to 1 basis point per annum in another.
currency - thus it varies with the tenor and structure of the interest rate curves of the.
two currencies. It is important to remember that it does not depend upon the FX rate,.
where 1 basis point in one currency is 1 basis point in the other, at all times..

Another way of thinking about the conversion factor is that it comes from differ-. ent convexities, or yield curve shapes, in the two currencies and is thus dependent both on interest rate curves and spread levels.

Where interest rate differentials are small, the conversion factor will make only a small difference to the rates - typically just 1 or 2 basis points - but where the differentials are large, the difference may be quite significant.

To convert from basis points in a non-EUR currency into basis points in EUR:

If the non-EUR rates $<$ EUR rates, then EUR conversion factor $>1$ If the non-EUR rates $>$ EUR rates, then EUR conversion factor $<1$

Or vs the USD,

If the non-USD rates $<$ USD rates, then USD conversion factor $>1$ If the non-USD rates $>$ USD rates, then USD conversion factor $<1$

The conversion factor of a particular tenor is given by the ratio of the sum of the discount factors up to that point of the different currencies - so for the 10-year point, it is the sum of all the EUR discount factors divided by the sum of all the USD discount factors. This tells us that the 1Oy EUR-to-USD conversion factor was 1.091 basis points on 20 February 2017, as in Table 1.1. Hence, a credit spread of 400bp over the EUR IRS swap curve translates into $400\times1.091=436\mathrm{bp}$ in USD. In order to. swap the EUR instrument into USD, you would need to further add the EUR/USD currency swap costs as well as the EUR basis swap cost of 39.5 bp (as of 20 February 2017). Finally, you might have to consider the Libor frequency of the EUR and USD legs. If the EUR leg is $6\mathrm{m}$ , as is market standard, and the USD leg is $3\mathrm{m}$ , as is also often the case, then the. $3/6$ EUR swap costs will also need to be added. If the two legs are the same, then this cost is zero.

Table 1.1: Example of conversion factor calculation as of 20 February 2017.


<html><body><table><tr><td colspan="10">Interestratesasof20Feb2017</td></tr><tr><td>Tenor 1y</td><td>2y</td><td>3y</td><td>4y</td><td>5y</td><td>6y</td><td>7y</td><td>8y</td><td>9y</td><td>10y</td></tr><tr><td>USD</td><td>1.30%</td><td>1.56% 1.75%</td><td>1.90%</td><td>2.01%</td><td>2.09%</td><td>2.18%</td><td>2.26%</td><td>2.32%</td><td>2.38%</td></tr><tr><td>EUR</td><td>-0.21% -0.15%</td><td>-0.07%</td><td>0.02%</td><td>0.13%</td><td>0.26%</td><td>0.38%</td><td>0.51%</td><td>0.64%</td><td>0.75%</td></tr><tr><td colspan="10">DiscountFactors</td></tr><tr><td>USD</td><td>0.991</td><td>0.976 0.959</td><td>0.940</td><td>0.920</td><td>0.900</td><td>0.879</td><td>0.859</td><td>0.838</td><td>0.818</td></tr><tr><td>EUR</td><td>1.004</td><td>1.007 1.008</td><td>1.008</td><td>1.005</td><td>0.999</td><td>0.990</td><td>0.978</td><td>0.964</td><td>0.948</td></tr><tr><td colspan="10">ConversionFactors</td></tr><tr><td></td><td>1.013 1.022</td><td>1.032</td><td>1.042</td><td>1.051</td><td>1.061</td><td>1.069</td><td>1.077</td><td>1.085</td><td>1.091</td></tr></table></body></html>

Source: Commerzbank Research

This example shows that the conversion factor element in cross-currency swaps made around $48\%$ (or 36bp) of the overall swap costs of 76.0bp if the credit spread. of the instrument is 400bp in February 2017.

We note that an advantage for an issuer is a disadvantage for an investor, and. vice versa. Thus, investors looking to buy bonds can apply exactly the same analysis to find where they may get the best value..

For a detailed discussion of the conversion factor, see Chapter 5.

# Where does the Cross-Currency Basis Come from?

In brief, the basis arises because issuers prefer to match the currency mix they have on the asset side with the currency mix on the liability side, while investors prefer to hedge their FX risk. If an issuer cannot obtain sufficient foreign currency funding (as during the 2008 financial crisis when European banks had to fund lots of dollar assets but had lost access to the dollar funding market), they can create synthetic foreign funding via domestic funding in combination with FX forwards (in the FX market) or basis swaps (which belong more to the rates market). This can create a mismatch in the supply/demand for foreign funding and the hedging instruments. As long as the access to foreign funding remains distorted between domestic and foreign issuers and market participants lack balance sheets or credit lines to arbitrage away the distortion, there will be pressure for the basis to exist. In general, this hedging need translates to demand for certain currencies, often the UsD. For a good explanation of these causes and effects, see Borio et al. (2016).

In Figure 1.6 is a rough illustration of the different potential sources of the basis.. It centres on issuance of debt in different countries and currencies. Note that the top. boxes and the bottom boxes balance' each other - if the top boxes dominate, the basis becomes more negative; if the bottom box effects grow, the basis becomes less. negative.

Some explanation of these terms is useful.

USD (EUR) payer swap: the owner of a cross-currency basis swap, which changes their net position from paying USD (EUR) floating rates to paying EUR (USD) floating rates.
Credit spread: the difference between rates which a company pays on its own curve (in USD, respectively EUR) and the IRS curve for the same currency. When. we hear that 'credit spreads are tight' it means that demand for corporate debt in that currency is high, so the cost of debt is relatively low..
Negative basis: the difference between the actual interest rate for a currency and the theoretical interest rate calculated using the FX forward rate, FX spot rate and (usually) the UsD interest rate. When the actual rate is less than the theoretical rate, the basis is negative.

![](6a9cd321bc22b8b8d4c975c7e0b627bfa33fca72dac1f006e396ecbf9cb784e5.jpg)
Figure 1.6: Potential sources of the xccy basis. Source: Commerzbank

Let's think of a situation in which an issuer finds themselves when they need to. issue debt. They want to do it in the most economical way. For a UsD issuer, the 'ground zero' or best possible level could be considered to be the IRS curve in USD (although some highly rated entities like GE can even trade inside the swap rate at the short end). The cost above that level is the credit spread due to their own issuer quality, or $\mathrm{USD}_{\mathrm{spread}}$ . Similarly, the cost of issuance to a Euro-area issuer is EURspread.

The cost of issuing in another currency, and then hedging the FX risk of the issue, will depend on the credit spread in the other country for companies of similar quality, the cross-currency basis, and the conversion factor.

So, now we have the full rationale, which companies must bear in mind when making their issuance choice:.

For the USD entity, they will issue in EUR (and buy USD payer xccy basis swaps) if

$$
\mathbf{USD_{spread}}>E\mathbf{U}\mathbf{R_{spread}}\star\mathbf{ConversionFactor}+\mathbf{xccybasis}
$$

This is the case for entities like SSSAs where the ECB PSPP is active.

For the EUR entity, they will issue in USD (and buy EUR payer xccy basis swaps) if

$$
\mathrm{EUR}_{\mathrm{spread}}>\mathrm{USD}_{\mathrm{spread}}\star\mathrm{ConversionFactor+xccybasis}
$$

This would most frequently be the case for higher-spread products (AT1 and T2, high-yield issuers) where the ECB is not active, and where for longer tenors the conversion factors are very favourable.

As an example, consider a US firm on 20 February 2017 whose bonds have a 200bp credit spread over the US swap rate. The subsidiary of the firm in Europe can issue bonds which have 1o0bp credit spread over the EUR swap rate. The basis is 39.5bp, and the conversion factor is 1.091.

$$
\begin{array}{r l}&{\mathbf{USD}_{\mathrm{spread}}=20\mathbf{0}\mathbf{b}\mathbf{p}}\ &{\mathbf{EUR}_{\mathrm{spread}}=100\mathbf{b}\mathbf{p}^{*}1.091+39.5\mathbf{b}\mathbf{p}}\ &{\phantom{\mathrm{=}}=\mathbf{148.6bp}=148.6\mathbf{b}\mathbf{p}}\end{array}
$$

# Thus, they'll be about 5obp better off if they issue in Europe.

The effect of this long-term behaviour is to skew the effective UsD interest rate.
higher. However, this skew will differ from one currency pair to the next as credit.
spread and other effects persist to different extents in different markets - thus the market 'expression' of this USD demand as a spread to the non-UsD interest rate.
Another way of putting it is that counterparties impose increasingly large spreads.
on the trade, which only ever seems to go one way!.

Euro-area supras and agencies are the prominent counterexample, as they. actively cover their EUR funding needs in the USD market and hence take advantage of the basis.

Another significant reason is currency mismatches on the balance sheets of large financial institutions. As yields change, balance sheets may be structurally biased towards or against specific currencies. FX derivatives like swaps will have to be used to cover any currency gaps between assets and liabilities, which will place pressure on equation (1) again. So here again, imbalances in the supply and demand for currency hedging result in a non-zero basis, as these institutions are usually fully FX-hedged.

Additionally, strategic hedging on the part of investors with foreign currency holdings can also apply pressure to widen (that is, make more negative) the basis. Once more, the hunt for yield sends the market into foreign territory. But portfolio allocation ratios, once established and prevalent, move slowly, and thus another persistent currency hedge position can exist.

The desirability of a currency is closely connected with yield, and one good in-. dicator of this is the FX carry trade. The G10 FX carry trade is the result of allocating funds to higher-yielding currencies by borrowing in the lower-yielding currencies. In Figure 1.7 we can see that this trade correlates closely with the EURUsD basis swap, showing that the basis is strongly influenced by yield - and thus ultimately central bank policies. However, as can be seen in the chart, during stress periods such as 2008 and $2011/12$ , the basis is highly volatile and can significantly decouple. from the carry/yield proxies.

5y EURUsD basis swap (bp, rhs) with G10 FX carry (index, Ihs)

![](226ab43975035e37904561783f0ac1f176bfd136bf2e1dfa4f27d30008deff79.jpg)
Figure 1.7: Cross-currency basis swap with FX carry.. Source: Bloomberg, Commerzbank Research

# What Keeps the Basis Swap from Being Arbitraged Away?

We can see why there might be one-way pressure on the forward rate or Libor rates, but traditionally, an equal and opposite pressure would be provided by arbitrage activity which would bring rates back in line with equation (1). Perhaps the important question is not Why does the basis swap exist?' because we know that pressures and temporary dislocations often occur in financial markets. The true question is, 'Why does it stay?'

There are quite a few reasons as to why it persists, and they all have to do with. the more stringent regulatory regime governing the markets since the crisis, which ultimately prevents markets from balancing supply and demand for FX hedges. We. list the more significant ones in the following section..

# Capital Cost of FX Derivatives

The regulatory burden of holding different deal types on books has changed. Derivatives like cross-currency swaps, which are used to arbitrage the currency imbalances described in the previous section, all involve capital flows - often substantial - at the end date. These will require large amounts of risk capital to be held against them. Thus, there will be a limit to how many may be done, and there may be a cost to doing them, as the risk capital used to protect them will be in safe, low-yielding in. struments. Arbitraging will thus entail a cost and will have a limited extent for most institutions.

# Counterparty Risks and Credit Limits

Arbitrage activities require counterparties and the credit quality of the counterparties limits the exposure that one institution can have to others. Thus, large-leverage and. high-risk deals can only occur with a limited set of counterparties and to a limited degree. In that regard, the varying cost and availability of repo funding across juris-. dictions limit the extent to which leveraged investors can arbitrage the basis away..

# Clearing

Cross-currency swaps are not eligible for clearing with many of the world's larger exchanges. Non-cleared derivatives tend to attract a higher cost of funding, and the introduction of bilateral variation margining for uncleared trades makes it difficult to execute trades, as numerous legal CSA amendments have not yet been signed. Though there are currently some exceptions made for the currency market, generally the delays to implement clearing for these deal types impose yet another limit on their number and extent.

# Horses for Courses

Of course, there are a few institutions that can do the arbitrage to a degree. But that. degree will vary. For a highly rated cash rich organisation, which could issue bonds in USD and take advantage of the basis to do a swap to the end date to deliver value. in a different currency, the cost of placing bonds is important. For a large hedge fund, the price and availability of funding to provide the large arbitrage cashflows will be paramount.

For a useful discussion of the causes of the basis, see Du, Tepper and Verdelhan (2016), which also argues that the dominant reason for its persistence are regulation-driven balance sheet costs.

# How Could an Institution Make Money from the Cross-Currency Basis Swap?

This is the burning question! There is no definitive answer, as different institutions will have very different situations, needs and relative advantages. But the graph in Figure 1.9 suggests that at least for some folks, for some of the time, there is money to be made.

We have calculated a yield pickup' for 1y government bonds. We assume that. the investor is based in Germany and can hold (and short via repo if necessary) bonds in Germany, the USA, Japan, the UK and Australia, with a similar rating or perceived credit risk. The yield pickup is the bond interest rate differential hedged for the 1y pe-. riod via the cross-currency swap market, including the basis. Thus the pickup is given by

$$
\Delta_{\mathbf{bond}}-\Delta_{\mathbf{swap}}+\mathbf{basis}
$$

where $\Delta_{\mathrm{bond}}$ and $\Delta_{\mathrm{swap}}$ are the 1y yield differentials for the relevant instruments in each currency. Writing it in this way clearly illustrates where the dislocations arise. If the spread of bond yield to swap was the same in both currencies, the first two terms would cancel out. If then the basis were zero, there would be no pickup at all. So it is due to differential market views on credit and to the basis. Figures 1.8 and 1.9 are the time series of this yield pickup since the end of 2o08 for the different currencies. The second graph focuses on the EURUSD case, showing $\Delta_{\mathrm{bond}}$ and $\Delta_{\mathrm{swap}}$ and the basis separately.

We see that the time series contain different correlation 'zones'. The start of the.. series in sees both JPY and USD with a negative basis from the EUR investor's point of view; in 2oo8, clearly both were seen as safe havens from the crisis storm. In 2011, however, the JPY correlates more strongly with AUD than USD, and only the USD is seen as the true safe haven in the first of the Greek debt crises. More recently, both USD and JPY maintain a negative basis, but short-range movement of the JPY basis can correlate with more risky currencies. Finally, we see that all four currency bases are going lower vs the EUR, quite possibly indicating a general nervousness about the Euro area in a time of multiple elections, where political surprises and reversals are becoming the norm.

Pickup for a EUR based investor, using 1y foreign govt bonds, in %

![](6adcdd71717f87f5519b6057a311b3d0ea443734eed0c91243a532404ef0b284.jpg)
Figure 1.8: Yield pickup, with potential arbitrage opportunity levels. Source: Commerzbank, Bloomberge

Swap-bond differences for 1y EUR and UsD govies. The addition of the basis makes a significant difference.

![](2b5c3dddc10848d3167099ec67acad0ac7246d0d4d5b3882fff1576a72f6f0c8.jpg)
Figure 1.9: EURUSD yield pickup components $(\%)$ Source: Bloomberg, Commerzbank Research

Is this pickup really available in the market? Not entirely - this assumes no repo. costs and ignores credit issues and the cost of capital. But nevertheless, it is rarely lower than 30bp for any currency and is often greater than 50bp. For different institu-. tions, there could be opportunities at some level..

# Appendix 1.A: The FX carry trade

A Historical View - UIP and CIP

# UIP -- The First to Fall

The first way in which the FX market declined to obey market expectation was Uncovered Interest Rate Parity (UIP). In the early days of the floating FX rate regime, it was assumed that spot rates would, on average, follow the path laid out by the forward rates. The forward rate path predicts (from equation (1)) that the higher nominal interest-bearing currency will depreciate relative to the lower interest-bearing currency. This does not on the face of it seem unreasonable - investors in higheryielding (higher inflation) currencies are compensated for the currency weakening. by higher interest rate income. Put differently, higher interest rates exist due to higher levels of risk (regarding inflation and central bank expectations, for example), thus, it is plausible to assume that more risky currencies will depreciate relative to less risky ones. Uncovered Interest Rate Parity is said to hold if currencies follow, on average, the forward rate path..

It is useful for market participants, risk managers and quants if UIP does hold. This means that the arbitrage pricing is correct on average and does not allow for systematic trading strategies to deliver profit, and it means that the middle office risk management of long-term positions within financial institutions can use the same valuation models as the front office traders.

But this does not hold. The devaluation of currencies implied by their interest. rate regimes does not, on average, occur. As the evidence mounted that UIP is violated - this was first pointed out in 1984 (see Fama [1984]) - and that forward rates have no predictive power over the path of spot rates, the market and various aca-. demic institutions reluctantly had to admit that this particular assumption was in-. valid. We summarise the evidence in Figure 1.10, which was taken from James,. Fullwood and Billington (2015) and has since been updated..

This is the result of pursuing a systematic rules-based, quarterly carry-trading. strategy in all liquid G10 currency crosses (heavy black line). A carry trade is where the trader takes a position against the forward rate (same as doing a short forward trade), borrowing in the lower-yielding currency to lend in the higher-yielding one. If the spot rate does move to the forward rate, then the trader will make no profit. If the spot rate stays the same and does not move over the course of the deal, the. trader will make exactly the forward interest rate differential (known as forward points) - this 'perfect carry trade' is represented by the fine grey dashed line. The. central heavy grey dashed line is the actual average path of the spot FX rates.

As can be clearly seen, the actual carry trade has almost identical results (with some noise) to the 'perfect' carry trade. This is the same as saying that on average,.

Average carry trade returns from all G 10 crosses

![](0e60874ab6ca4f3a6e34c07b843120256a497e26d7ec824076d6a19054312637.jpg)
Figure 1.10: Carry trade returns.

FX rates do not move toward the forward rates - they are more likely to be the same as the spot rate at the start of the deal..

So UIP bites the dust. What about CIP?

# CIP -- Surely Invulnerable?

Covered Interest Rate Parity (CIP) was thought to be a much harder nut to crack. Covered Interest Rate Parity is said to hold if equation (1) holds. However, as we have shown, the existence and persistence of the non-zero cross-currency basis clearly shows that indeed, CIP has fallen as well.

# Appendix 1.B: The Cross-Currency Toolkit

# The Three Elements

There are different financial products available to allow investors and issuers to adjust their currency exposures. The most liquid and widely used are:

- FX swaps - FX outrights (or forward outrights) - Cross-currency basis swapse

Each serves different sections of the market and is useful in different ways. In the following section, we explain the mechanics of each and their major uses..

# FX Swap

Figure 1.11 is a schematic of the cashflows involved in an FX swap between parties A and B. We assume we have a principal amount. $P$ in EUR, and that the current. spot FX rate is S USD per EUR, with a forward rate. $F$

![](d4f4790d30d6734472da8cba2861d95dcf9f87bdae45b7506a30af13ddda0dec.jpg)
Figure 1.11: FX swap. Definition of FX swap: Party A borrows Currency 1 to lend Currency 2

Usual Maturity: up to 1y

Uses: FX swaps are mostly a liquidity and treasury management tool. Users are:
-Asset Managers: investors in overseas markets who don't want currency risk.. Lenders of domestic currency vs the foreign currency they need to fund.
- Bank Treasurers: wish to lower their cost of funding and liquidity in different currencies
Central Banks: manage their liquidity profiles
- Corporate Treasurers: act like banks for their own short-term funding, and manage their treasury position in different currencies.

Note that the basis is embedded into the forward rate, so though it is not explicit in the diagram, it is certainly included.

# FX Outright (Forward Outright)

In Figure 1.12, we show the cashflows involved in an FX Outright (often called Forward Outright) between parties A and B. We again assume we have a principal amount $P$ in EUR, and that the current spot FX rate is S USD per EUR, with a forward. rate $F.$ Though simple in concept, in execution this tends to be done as a swap plus a spot transaction.

![](28d0481bbe27d6912c8fcecceaa33d278bb91a368049383bce8db965f41fe8f6.jpg)
Figure 1.12: FX outright. Definition of FX swap: Party A and Party B exchange Currency 1 for Currency 2 at a future date.

In fact, it is usually done as a spot trade plus a swap, as in Figure 1.13.

![](52c08bf6813c02b0a9c487db0d03b6cbbd194dfc7cf33800073e789f5d9ad69a.jpg)
Figure 1.13: Spot trade plus swap.

Usual Maturity: below 1y or 2y

Uses: This market tends to be extensively used by corporates and exporters, to cover trade and repatriation flows.

As before, the basis is embedded in the forward rate.

# Cross-Currency Basis Swap

In Figure 1.14, we now include the interim interest payments included in a crosscurrency basis swap.

![](425d866b31e6997d813ba42134135de18b9ffb0d9b3b11bf75b389f8ad6a9142.jpg)
Figure 1.14: Cross-currency basis swap.

Definition of FX cross-currency basis swap: where two parties borrow from, and simultaneously lend to, each other an equivalent amount of money denominated in two different currencies for a predefined period of time, including floating interim interest payments, usually 3m.

Usual Maturity: up to 30y in some cases, though up to 10y is more usual

Uses: Primarily used by debt issuers

- SSAs: natural multi-currency users. Different locations will have different currency mixes.

-Corporates: Some large corporates can act like SSAs. Others may use EUR or USD as funding currencies, swapping back to USD.

- Banks: Treasuries minimise cost of funding and liquidity. They vary according to location. Some derivative desks manage the currency risk of different counterparties with xccy swaps.

- Asset managers hardly ever use this market due to the high cost of capital and regulatory constraints. As they would be the natural arbitrageurs in this space, the non-zero basis can persist.

The basis is explicit in the EUR Libor flows.
