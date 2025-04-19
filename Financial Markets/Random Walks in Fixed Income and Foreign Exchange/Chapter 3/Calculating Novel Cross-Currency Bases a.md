---
tags:
  - cross_currency_basis
  - fx_hedged_pickup
  - government_bonds
  - interest_rates
  - xccy_basis
aliases:
  - Cross-currency basis
  - FX Hedged Pickup
  - Hedged Pickups
  - XCCY basis
key_concepts:
  - FX hedged pickup
  - cross currency basis
  - currency quote convention
  - government bond yields
  - xccy basis calculation
---

# Chapter 3 Calculating Novel Cross-Currency Bases and FX Hedged Pickups

The cross-currency (xccy) basis is, in the post-crisis world, an essential part of any overseas investment or funding decision.' Sensitivity to credit risk and quality mean that relationships among interest rates, FX rates and FX forwards have become far more complex, with opportunities arising and disappearing as the markets evolve. Chapter 1 and Chapter 2 have illustrated how some investors can discover opportunities in overseas bond markets which can even be fully FX hedged, the so-called 'hedged pickups', when rate differentials and the xccy basis align to deliver a positive return.

However, not all liquid crosses have a corresponding quoted xccy basis. Almost. all quoted xccy bases are to the USD, with just a few to the EUR. So if an opportunity arises in, say, GBPJPY, it is more difficult to spot and may go unnoticed by market participants who could take advantage of it..

Fortunately, it is possible to calculate almost all of these cross rate xccy bases, and from them, their hedged pickups. These calculations, while not the same as market quotes, are excellent indicators of where opportunities may be found in these liquid but less explored crosses.

# What is the FX Hedged Pickup?

The FX hedged pickup is the gain (or loss) which may be secured by shorting one bond, going long of another, and hedging the FX risk. Here we consider government bonds and two hedge types: (1) the full hedge for the tenor of the bonds, and (2) a short $3\mathrm{m}$ or 6m hedge after it is assumed that the bonds would be sold. It's impor-. tant to remember that (2) entails more risk, as changes in the value of the bonds are not hedged in this case. In the pre-crisis days, when there was in essence only one 'yield curve' and no xccy basis, there would have been little or no pickup available. In the post-crisis world, the curve has split into many, depending on credit levels,. and the xccy basis is often substantial, and so these pickups can be significant.

In essence, the FX hedged pickup is found using the following expression:

Pickup $=$ Delta Bond - Delta Swap $+/-$ Basis

For example, for a EU investor who would like to short their own government debt and buy US government debt instead due to higher yields:

Delta Bond $=$ US bond yield -- EU bond yield

Delta Swap $=$ USA swap rate - EUR swap rate

Finally, the xccy basis must be included. This is always quoted as a spread to the non-USD (or if USD is absent from the pair, the non-base currency), so it may be added or subtracted depending on the currency quote convention.

For the short-dated rolling pickup, the interest rate and the xccy basis will be 3m or 6m. The bond yields may be any liquid tenor. For the more complete 'maturity matched' hedge, the tenor of all the instruments must match. This latter transaction is inherently more of a true hedge, as the rolling hedge is short-term and may be derailed by changes in the underlying value of the bonds.

# Finding xccy Bases

Which xccy bases are already easily available as quotes and time series? Tables 3.1-3.3 show which tenors and crosses are available to USD, EUR and JPY.

Table 3.1: Available series for xccy basis swaps to the USD.


<html><body><table><tr><td></td><td>EUR</td><td>USD</td><td>GBP</td><td>JPY</td><td>AUD</td><td>CAD</td><td>CHF</td><td>SEK</td></tr><tr><td>3M</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>6M</td><td></td><td></td><td></td><td></td><td><</td><td><</td><td></td><td></td></tr><tr><td>1Y</td><td></td><td></td><td><</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>2Y</td><td></td><td></td><td></td><td><</td><td></td><td></td><td></td><td>√</td></tr><tr><td>3Y</td><td></td><td></td><td></td><td><</td><td></td><td></td><td></td><td>人</td></tr><tr><td>4Y</td><td></td><td></td><td></td><td></td><td><</td><td></td><td></td><td></td></tr><tr><td>5Y</td><td></td><td></td><td><</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>6Y</td><td></td><td></td><td></td><td></td><td></td><td><</td><td></td><td></td></tr><tr><td>人</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>人</td></tr><tr><td>8Y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td><</td></tr><tr><td>9Y</td><td></td><td></td><td><</td><td></td><td><</td><td><</td><td></td><td></td></tr><tr><td>10Y</td><td></td><td></td><td><</td><td><</td><td></td><td></td><td><</td><td></td></tr></table></body></html>

Table 3.1 (continued)


<html><body><table><tr><td></td><td>EUR</td><td>USD</td><td>GBP</td><td>JPY</td><td>AUD</td><td>CAD</td><td>CHF</td><td>SEK</td></tr><tr><td>15Y</td><td></td><td></td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td></td></tr><tr><td>20y</td><td></td><td></td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td><td></td></tr><tr><td>30Y</td><td>√</td><td></td><td>√</td><td>√</td><td></td><td>√</td><td>√</td><td></td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

Table 3.2: Available series for xccy basis swaps to the EUR.


<html><body><table><tr><td>EUR</td><td></td><td>USD</td><td>GBP</td><td>JPY</td><td>AUD</td><td>CAD</td><td></td><td>SEK</td></tr><tr><td>3M</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x</td></tr><tr><td>6M</td><td></td><td></td><td></td><td>x</td><td>X</td><td></td><td>x</td><td>x</td></tr><tr><td>1Y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>2Y</td><td></td><td></td><td>√</td><td></td><td></td><td>√</td><td></td><td>√</td></tr><tr><td>3Y</td><td></td><td></td><td>√</td><td></td><td>√</td><td>√</td><td></td><td>√</td></tr><tr><td>4Y</td><td></td><td></td><td></td><td>√</td><td>√</td><td>√</td><td></td><td>√</td></tr><tr><td>5Y</td><td></td><td></td><td>√</td><td></td><td></td><td>√</td><td>√</td><td></td></tr><tr><td>6Y</td><td></td><td></td><td></td><td></td><td>√</td><td></td><td></td><td>x</td></tr><tr><td>人</td><td></td><td></td><td>√</td><td></td><td>√</td><td>√</td><td>√</td><td></td></tr><tr><td>8Y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>x</td></tr><tr><td>9Y</td><td></td><td></td><td></td><td></td><td>√</td><td><</td><td>√</td><td>x</td></tr><tr><td>10Y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>15Y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>√</td></tr><tr><td>20y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>30Y</td><td></td><td></td><td></td><td></td><td>X</td><td></td><td></td><td></td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

It's clear that the data vs the USD is a more complete set than that vs the EUR, and that the short-dated (3m and 6m) xccy basis swaps are very poorly represented for anything except the USD. Thus the short-dated 'rolling' FX hedged pickups to anything except the USD would be impossible to calculate unless there were some other way of deriving the 3m and 6m xccy bases. The data for JPY investors is very sparse indeed - and as deals involving, for example, AUD or GBP vs JPY are hardly uncommon, this makes it potentially useful to investigate.

Table 3.3: Available series for xccy basis swaps to the JPY.


<html><body><table><tr><td></td><td>EUR</td><td>USD</td><td>GBP</td><td>JPY</td><td>AUD</td><td>CAD</td><td>CHF</td><td>SEK</td></tr><tr><td>WE</td><td></td><td></td><td>×</td><td></td><td>×</td><td>X</td><td>×</td><td></td></tr><tr><td>6M</td><td>x</td><td></td><td>X</td><td></td><td>X</td><td>X</td><td></td><td>X</td></tr><tr><td>1Y</td><td></td><td></td><td>×</td><td></td><td>×</td><td>X</td><td></td><td>X</td></tr><tr><td>2Y</td><td></td><td>√</td><td>×</td><td></td><td></td><td>X</td><td>x</td><td>X</td></tr><tr><td>3Y</td><td>√</td><td></td><td></td><td></td><td>×</td><td></td><td>X</td><td>x</td></tr><tr><td></td><td></td><td></td><td>X</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>5Y</td><td></td><td></td><td>×</td><td></td><td></td><td>X</td><td></td><td>X</td></tr><tr><td>6Y</td><td></td><td></td><td>×</td><td></td><td>×</td><td></td><td></td><td></td></tr><tr><td>人</td><td>√</td><td>√</td><td>×</td><td></td><td></td><td>X</td><td>x</td><td>X</td></tr><tr><td>8Y</td><td></td><td></td><td></td><td></td><td>×</td><td></td><td></td><td></td></tr><tr><td>9Y</td><td></td><td></td><td>x</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>10Y</td><td></td><td></td><td>×</td><td></td><td>×</td><td>X</td><td></td><td></td></tr><tr><td>15Y</td><td></td><td></td><td></td><td></td><td>X</td><td></td><td></td><td>X</td></tr><tr><td>20y</td><td></td><td></td><td></td><td></td><td></td><td>X</td><td>X</td><td>X</td></tr><tr><td>30Y</td><td>√</td><td></td><td></td><td></td><td>X</td><td></td><td>X</td><td>X</td></tr></table></body></html>

Source: Bloomberg, Commerzbank Research

How can we fill in some of these data series? First of all, there is a useful additive property of basis swaps. We may say that.

$$
X C C Y_{A B}=X C C Y_{C A}-X C C Y_{C B}
$$

where A, B and C are currencies, and XCCY is the basis swap. So for USD, EUR and JPY, we have

$$
X C C Y_{J P Y-G B P}=X C C Y_{U S D-J P Y}-X C C Y_{U S D-G B P}
$$

Thus we can use the USD basis swaps to construct many of the missing JPY ones.. We can see that the relationship holds well in the case of EUR, USD and JPY, where the EURJPY basis swap is available both by construction and quoted in the market.. In Figure 3.1, we graph the quoted and the constructed rates for the 10y case..

How many of the currency crosses can we fill in now with this new technique? Tables 3.4 and 3.5 are the 'new' versions of the available series for the EUR and the JPY.

This is much better - for EUR we have a complete set, but we still lack the important short-dated basis swaps for the JPY crosses. But all is not lost. These can be derived from spot FX rates, forward FX rates and short-dated interest rates. As an example, to find the EURJPY $3\mathrm{m}$ basis, we can do the following:

![](3937090efee705c446eddca28b32dc355163b0518926d3118c3dc5bb327efd4c.jpg)
Figure 3.1: Constructed and quoted EURJPY 10y xccy basis in bp. Source: Bloomberg, Commerzbank Research

Table 3.4: Available series for xccy basis swaps to the EUR, with basis series reconstruction from other bases.


<html><body><table><tr><td></td><td>EUR</td><td>USD</td><td>GBP</td><td>JPY</td><td>AUD</td><td>CAD</td><td></td><td>SEK</td></tr><tr><td>3M</td><td></td><td></td><td>√</td><td></td><td>√</td><td>√</td><td></td><td></td></tr><tr><td>6M</td><td></td><td></td><td></td><td></td><td><</td><td>√</td><td>√</td><td></td></tr><tr><td>1Y</td><td></td><td></td><td></td><td></td><td>√</td><td>√</td><td></td><td>√</td></tr><tr><td>2Y</td><td></td><td></td><td>√</td><td></td><td>√</td><td>√</td><td></td><td>√</td></tr><tr><td>3Y</td><td></td><td></td><td></td><td>√</td><td>√</td><td>√</td><td></td><td>√</td></tr><tr><td>人</td><td></td><td></td><td>√</td><td></td><td>√</td><td>√</td><td></td><td>√</td></tr><tr><td>5Y</td><td></td><td></td><td></td><td></td><td>√</td><td></td><td></td><td>√</td></tr><tr><td>6Y</td><td></td><td></td><td></td><td></td><td>√</td><td>√</td><td>√</td><td></td></tr><tr><td>人</td><td></td><td></td><td></td><td></td><td></td><td></td><td>√</td><td></td></tr><tr><td>8Y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>√</td></tr><tr><td>9Y</td><td></td><td><</td><td></td><td></td><td></td><td></td><td></td><td>√</td></tr><tr><td>10Y</td><td></td><td></td><td></td><td></td><td>√</td><td></td><td></td><td></td></tr><tr><td>15Y</td><td></td><td></td><td></td><td></td><td><</td><td></td><td>√</td><td>√</td></tr><tr><td>20y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>√</td></tr><tr><td>30Y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

Source: Bloomberg, Commerzbank

Table 3.5: Available series for xccy basis swaps to the JPY, with basis series reconstruction from other bases.


<html><body><table><tr><td></td><td>EUR</td><td>USD</td><td>GBP</td><td>JPY</td><td>AUD</td><td>CAD</td><td>CHF</td><td>SEK</td></tr><tr><td>3M</td><td>x</td><td>√</td><td></td><td></td><td></td><td>X</td><td>X</td><td></td></tr><tr><td>6M</td><td></td><td>√</td><td></td><td></td><td></td><td>X</td><td></td><td></td></tr><tr><td>1Y</td><td>√</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>2Y</td><td>√</td><td></td><td></td><td></td><td></td><td></td><td>√</td><td>√</td></tr><tr><td>3Y</td><td>√</td><td></td><td></td><td></td><td></td><td></td><td>√</td><td>√</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>√</td><td></td><td></td></tr><tr><td>5Y</td><td>√</td><td>√</td><td></td><td></td><td>√</td><td></td><td></td><td></td></tr><tr><td>6Y</td><td></td><td></td><td><</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>7Y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>8Y</td><td></td><td></td><td></td><td></td><td><</td><td></td><td></td><td></td></tr><tr><td>9Y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>√</td></tr><tr><td>10Y</td><td>√</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>15Y</td><td></td><td></td><td>√</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>20y</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>√</td></tr><tr><td>30Y</td><td>√</td><td></td><td></td><td></td><td></td><td>√</td><td></td><td></td></tr></table></body></html>

Source: Bloomberg, Commerzbank

$$
\mathrm{EURJPYbasis}=100\times\left[\left(\frac{F}{S}\times\left(1+\frac{r_{d}}{400}\right)-1\right)\times400-r_{f}\right]
$$

where $\mathrm{F}=3\mathrm{m}$ forward FX rate for EURJPY ${\mathrm{S}}=$ spot rate for EURJPY $\mathbf{r}_{\mathrm{d}}=$ domestic interest rate (EUR) $\mathbf{r}_{\mathrm{f}}=$ foreign interest rate (JPY)

Finally, now we can fill in the last lines on the JPY table of data availability.

Now we can graph xccy bases that are not usually quoted. As an example, we give GBPJPY 10y and 3m xccy bases in Figure 3.2, and CHFJPY in Figure 3.3. These are certainly rates used in international trade, but there is usually no time series data available.

![](56ba07797b480baf7824ae6b12ee8f260513306aae988c06f37b63f0f27949b1.jpg)
Figure 3.2: Xccy basis for GBPJPY in bp Source: Commerzbank, Bloomberg

![](aefb0f1f277eb991ada890b41740f991ebd3838d84a39536d5f04b6cd17f9d58.jpg)
Figure 3.3: Xccy basis for CHFJPY in bp. Source: Commerzbank, Bloomberg

What is remarkable about both these graphs is that the basis can be pretty. large - over a per cent in the case of the 3m CHFJPy. While, with these reconstructed rates, one needs to bear in mind that they may be noisy, the excessions. do seem to mirror market events - for example, one of the largest spikes in the CHFJPY 3m basis occurs early in 2015 when the SNB ceased to maintain the pegged FX rate.

For other examples of these unusual xccy basis time series, see Appendix 3.A, where we have graphed a selection of tenors for the EUR and JPY crosses. Please note that as some rates are reconstructed from others, particularly the 3m rates, they can be rather noisy, but the levels and dynamics will contain useful information. For completeness, we also include the UsD bases, which are available in the market but are interesting for comparison purposes.

# Calculating FX Hedged Pickup

Now that we have the full set of xccy bases, perhaps we can generate a similar set of FX hedged pickups - which may represent opportunities for some investors. In Figures 3.4 to 3.7, we graph the FX hedged pickups, both rolling and matched maturity, for some JPY crosses (assuming from JPY based entity, so going short the JPY bond). It can be seen that some are at significant levels.

![](b3af552b67413cde09f178130a9e499ed5aa29072a350a486355f58fe9b2d416.jpg)
Figure 3.4: FX hedged pickup for EURJPY in. $\%$ Source: Bloomberg, Commerzbank Research

![](ed1729e88e378070ca2e064e3b5ca8fe14bdfdddd012a9456a1676aa382df432.jpg)
Figure 3.5: FX hedged pickup for USDJPY in $\%$ Source: Bloomberg, Commerzbank Research

![](d8685d918cebf590ea2c8f3eea337569558b0f50bc9d4d812c57cffa01affc2c.jpg)
Figure 3.6: FX hedged pickup for GBPJPY in $\%$ Source: Bloomberg, Commerzbank Research

![](77b04277939db7c302476858c39aadfd8dc1e49241b175944a67109bd5f0706d.jpg)
Figure 3.7: FX hedged pickup for AUDJPY in $\%$ Source: Bloomberg, Commerzbank Research

The potential value in some of these pickups is considerable. All values are annualised and thus, for example, the 30y EURJPY pickup is currently at almost $-1\%-$ indicating that one could short EUR government bonds, buy JPY government bonds, lock in a 30y FX hedge, and generate nearly $1\%$ of pickup per year. It's important to remember that this would be dependent on multiple factors - only an entity with good enough market access and credit would be able to attempt this, and the various rates are calculated rather than market quotes, so it would be advisable to check them carefully in the market. But as indications of potential value, these results are extremely interesting. In Appendix 3.B, we have graphed FX hedged pickups to the EUR, USD and JPY. These are not the only possible crosses; in theory, all others within the currency set are obtainable.

# Appendix 3.A: Xccy Bases

![](6d6daffb9e48095d33df7ff4f8b2abefa6f0fd4dc5fd29555da445b923667108.jpg)
To the EUR

![](f3ace0643b521c5ec924be66e4bdec2bf86bc4e76aedd70033856a4f088e522d.jpg)
Figure 3.8: Xccy basis for EURUSD in bp (to the EUR).

![](6a107476b1302e52c162430849dd6e55b320ce06368e28637e0b37044a0cbeef.jpg)
Figure 3.9: Xccy basis for EURJPY in bp (to the EUR).
Figure 3.10: Xccy basis for EURGBP (to the EUR).

![](21645fed4a28bbc96295bdf3aa98a3a2c08022891d09338b0c7f700af6c02850.jpg)
Figure 3.11: Xccy basis for EURAUD (to the EUR).

![](2147cff60b88dadfdbfcfd888d8b095369f0433c36359741f5c6fe6f2f1dee8e.jpg)
Figure 3.12: Xccy basis for EURCAD (to the EUR).

![](bf245fef26b94dfc869cb387ea9d52b8c4bd38c4c344181cd07e07bfda7305cb.jpg)
Figure 3.13: Xccy basis for EURCHF (to the EUR).

![](7de07ac704e5844d2aa2088dd06e846b12fe36d4a1415ea343c1c2bbae4e0acd.jpg)
To the USD

![](cfe231889602d6dc01b7c80ab3a22f8fbf84559e0e8326d15a407214855d93b8.jpg)
Figure 3.14: Xccy basis for EURUSD (to the USD). Source: Bloomberg, Commerzbank Research

![](b84bb6b3f83ab4a3babc686aa15aab3cc8dea82a67bd5dc4d0d1c376c4ca72ab.jpg)
Figure 3.15: Xccy basis for USDJPY (to the USD). Source: Bloomberg, Commerzbank Research
Figure 3.16: Xccy basis for USDGBP (to the USD). Source: Bloomberg, Commerzbank Research

![](3c1595b745f1a22610f8d1f26d813b50eca49f2be4d49f1ac900ba5b5a2e803e.jpg)
Figure 3.17: Xccy basis for USDAUD (to the USD). Source: Bloomberg, Commerzbank Research

![](2153e0c94abbd205df0b3bdcff2f856afc3023549d6a990bac4ee6aee8a21c13.jpg)
Figure 3.18: Xccy basis for USDCAD (to the USD). Source: Bloomberg, Commerzbank Research

![](86e203c83e43d74dbf2e1d6e0f759e5c26b43939cea68fbe586bbca129df807f.jpg)
Figure 3.19: Xccy basis for USDCHF (to the USD). Source: Bloomberg, Commerzbank Research

![](faf4c4308695fcd0b74cb63a74f95aea755bc14a14e56b9e7a11d9d7a23073d1.jpg)
To the JPY

![](d6ee6c15bd06305eaffc7d61c9994b8f781c91305943d8924d23cac0130b9a5e.jpg)
Figure 3.20: Xccy basis for EURJPY (to the JPY). Source: Bloomberg, Commerzbank Research

![](59f1a6d7d64a63d32b6e0caa7664f5a61a4b06968e57d2004dcb198ae3fa34b3.jpg)
Figure 3.21: Xccy basis for USDJPY (to the JPY). Source: Bloomberg, Commerzbank Research
Figure 3.22: Xccy basis for GBPJPY (to the JPY). Source: Bloomberg, Commerzbank Research

![](781986b96b97355be041a0211d038923ad9cf3f53e54c9c00641c04b6fc23121.jpg)
Figure 3.23: Xccy basis for AUDJPY (to the JPY). Source: Bloomberg, Commerzbank Research

![](e857711a5123c4fe078e45937a1c5119efffb666e99e9df452d09372f8d2cda1.jpg)
Figure 3.24: Xccy basis for CADJPY (to the JPY). Source: Bloomberg, Commerzbank Research

![](1249ee4af99ffe7fe582c056ff6b2c66530c9a8aa357ff41ab3d44ce257891b0.jpg)
Figure 3.25: Xccy basis for CHFJPY (to the JPY). Source: Bloomberg, Commerzbank Research

# Appendix 3.B: FX Hedged Pickups

# To the EUR

![](c59c494ac818b3b419d4ae4379dc380ea4ddf344c2d08988cb805782b57cae9d.jpg)
Figure 3.26: FX hedged pickup for EURUSD (to the EUR). Source: Bloomberg, Commerzbank Research.

![](c142dfbc194f8966df98371d8f907a5ffb804bdde489535f508f9ac1135ea03d.jpg)
Figure 3.27: FX hedged pickup for EURJPY (to the EUR). Source: Bloomberg, Commerzbank Research.

![](b7678360bcd9dfd46f273ea7d83d1529f6365d77c7c6af1f16696d7dffce880c.jpg)
Figure 3.28: FX hedged pickup for EURGBP (to the EUR). Source: Bloomberg, Commerzbank Research

![](8be4b6af8a9b097fcf08d2283a3ab00810b1a74cf4011dbb2219c5515e8fa589.jpg)
Figure 3.29: FX hedged pickup for EURAUD (to the EUR). Source: Bloomberg, Commerzbank Research.

![](2a49d0a5108534cd9456137b97313a3df312aa995adb048cbab95aa12e6ca64c.jpg)
Figure 3.30: FX hedged pickup for EURCAD (to the EUR). Source: Bloomberg, Commerzbank Research.

![](d2a59cbf82b50ca08fcb07d629b80306becbf1766acf0b0910ee9256711c402e.jpg)
Figure 3.31: FX hedged pickup for EURCHF (to the EUR). Source: Bloomberg, Commerzbank Research.

![](4188a2c6a4941128ae388142ef4861c0ab8b57c0dbe9a7934ab9dd1ac3d5fb3b.jpg)
To the USD
Figure 3.32: FX hedged pickup for EURUSD (to the USD). Source: Bloomberg, Commerzbank Research

![](6327fd3f47664a7b8f5a4047d3c4434188fdb92fddf6b2e81ea989ca3ea6c20c.jpg)
Figure 3.33: FX hedged pickup for USDJPY (to the USD). Source: Bloomberg, Commerzbank Research

![](090071b0891f6d15a436ed25d453c11636bb5019b0f046f5aadd1efae97a4f4b.jpg)
Figure 3.34: FX hedged pickup for USDGBP (to the USD). Source: Bloomberg, Commerzbank Research.

![](1c1075a0e943f2d88087fbbe2c254597df2c83088e3d104d0386b7805d244c06.jpg)
Figure 3.35: FX hedged pickup for USDAUD (to the USD). Source: Bloomberg, Commerzbank Research

![](a6e493517eddcdf18b778c80094b99009887aeef39dd7be970e4804756be1a36.jpg)
Figure 3.36: FX hedged pickup for USDCAD (to the USD). Source: Bloomberg, Commerzbank Research.

![](19fcd30597d5826f045a9380ea612d6e639a06edd338336dae50e593d2561e24.jpg)
Figure 3.37: FX hedged pickup for USDCHF (to the USD). Source: Bloomberg, Commerzbank Research

![](c8b52f91e38ec7af181534ed1b9c789bd0cbe91c17b443bfce101613cadc5951.jpg)
To the JPY
Figure 3.38: FX hedged pickup for EURJPY (to the JPY). Source: Bloomberg, Commerzbank Research.

![](c21b1f7157f69e308255c5f4065a971ebec0d6f9290283ecea6c7ef9db31b1c5.jpg)
Figure 3.39: FX hedged pickup for USDJPY (to the JPY). Source: Bloomberg, Commerzbank Research

![](c1aa15588f75ab8201685e50065ed62a93ed3dc8086d32b153936127ed3bfb07.jpg)
Figure 3.40: FX hedged pickup for GBPJPY (to the JPY). Source: Bloomberg, Commerzbank Research.

![](213c9c632674430801ad88117ba31eaa0b30e27259e704aa30d53faaee3e6406.jpg)
Figure 3.41: FX hedged pickup for AUDJPY (to the JPY). Source: Bloomberg, Commerzbank Research

![](9581d2f9072deab40a9e30cb4d0af29d7ee9bb49795e5b937240c46cdeff5579.jpg)
Figure 3.42: FX hedged pickup for CADJPY (to the JPY). Source: Bloomberg, Commerzbank Research

![](25a52736a63b3516232374c04873a1318886283544cdb2f8c16a1f0fd4d08165.jpg)
Figure 3.43: FX hedged pickup for CHFJPY (to the JPY). Source: Bloomberg, Commerzbank Research
