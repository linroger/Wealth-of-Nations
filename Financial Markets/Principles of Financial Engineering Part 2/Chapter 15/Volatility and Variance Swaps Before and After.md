---
tags:
  - gfc
  - liquidity
  - market_makers
  - variance_swaps
  - volatility
aliases:
  - GFC
  - Variance Swaps
  - Volatility Swaps
key_concepts:
  - Convexity adjustment role
  - Liquidity in crisis
  - Market maker difficulties
  - Variance swap hedging
  - Volatility risk profiles
---

# 15.7 VOLATILITY AND VARIANCE SWAPS BEFORE AND AFTER THE GFC-THE ROLE OF CONVEXITY ADJUSTMENTS?  

As we have seen in Section 15.4, in theory, a market maker could sell a variance swap and hedge it by means of a static hedge with a portfolio of put and call options across a range of strike prices, weighted inversely proportional to the squared strike price.  

# 15.7.1 THE DIFFICULTY OF HEDGING VARIANCE SWAPS IN PRACTICE  

In practice, options across the whole range of required strike prices and maturities are either not available or not very liquid. Index options tend to be more liquid than individual stock options. As a result, dealers and market makers before the GFC concentrated on a limited number of strike prices near the spot level. Since the 1990s the over-the-counter market for variance swaps on indi-. ces and individual equities developed. However, what many dealers painfully learned during the GFC when markets dropped and volatility spiked is that liquidity is not constant and it tends to dis-. appear in crisis times. In September 2008, as markets plunged, market makers, who tried to rebalance their hedges in accordance with their models, found that liquidity dried up in listed option. markets and it was difficult and expensive to hedge exposures. The drop in liquidity was more. severe for single name options than for index options. Dealers who were short single-stock variance swaps suffered the most accordingly.  

# EXAMPLE  

hen volatility rises by the amount it did in late 2008 and you square it to calculate the payout of a   
variance swap, it's a nasty product to be short of-and a lot of dealers were short single-stock variance.   
The hedges they had put on just didn't perform in any way approaching how they would have wanted.   
Although those positions are theoretically hedgeable with listed options, it assumes that wherever the stock   
price is, you can buy strikes down to zero, but that is never the case. (a quote of Dean Curnutt, president of Macro Risk Advisors, a New York-based. derivatives asset management firm, and previously head of institutional equity derivatives sales at Bank of America, Structured Products, April 1, 2010, www.risk.net/1595196)  

One of the features of variance swaps is that they exhibit a constant vega irrespective of the level of the spot price. Since this vega increases linearly with the level of volatility, the dealer needs to buy more options to hedge the swap as volatility increases. This is possible in normal liquid markets, but in crises times when markets fall and risk aversion increases it is difficult to find liquidity options.  

The above example not only illustrates practical difficulties in hedging variance swaps but also the different risk profiles of volatility and variance swaps. The payoff of a variance swap is, as we saw earlier, equal to the difference between the realized variance (that is the square of the volatility) and a preagreed strike level, multiplied by the vega notional. Thus, the payoff of a variance swap is convex in volatility. What does this imply for an investor that is long a variance swap? It means that the investor will benefit from increased gains and reduced losses compared with an alternative exposure to volatility by means of a volatility swap. Similarly, for an investor that is short a variance swap it implies that losses are magnified compared to a volatility swap. Why would someone want to short a variance swap, then? The answer is that, the fair strike of a variance swap is higher than that of a volatility swap. This makes the selling of variance swaps more attractive compared to volatility swaps since the seller can sell at a higher price. Some investors that are long volatility prefer variance swaps to volatility swaps due to the additional convexity and the resulting higher profit potential when volatility suddenly increases. This investor clientele often chooses single-stock variance trades over index variance trades since volatility moves in single stocks tend to be more pronounced than in indices.  

The following reading illustrates one of the lessons learned from the GFC in equity derivatives.  

# EXAMPLE  

"The convexity in variance swaps was an appealing proposition for clients that tended to be long volatility. For the sell side, it involved a big bet on liquidity in vanilla options being continuously available to provide some degree of hedge. In retrospect, variance is not a product that works for the sell side in very volatile markets, [...].  

(Structured Products, April 1, 2010, www.risk.net/1595196)  

As the example illustrates, theoretical models assume that continuous hedging is possible in practice. This assumption does not hold in reality and especially in volatile markets hedging becomes difficult and expensive. Some market participants have therefore argued that the variance swap market grew too fast and did not pay attention to the underlying complexities associated with liquidity and hedging costs.  

# 15.7.2 CONVEXITY AND THE DIFFERENCE BETWEEN VARIANCE AND VOLATILITY SWAPS  

# 15.7.2.1 Source of the convexity adjustment  

As we have seen in Section 15.5.4, variance emerges naturally from hedged options trading. However, there is no simple replication strategy for synthesizing a volatility swap despite the preference for volatility quotes over variance quotes by many market participants. To move from variance swaps to volatility swaps prices a convexity adjustment is required. In other words, from a contingent claims or derivatives perspective, variance is the primary underlying and all other volatility payoffs, such as volatility swaps, should be viewed as derivative securities on the variance as underlying. Intuitively, volatility is the square root of variance and therefore a nonlinear function of variance. As a result volatility is theoretically and practically more difficult to hedge and value.  

To explain the difference between volatility and variances swap pricing, let's look at a naive strategy that approximates a volatility swap by statically holding a suitably chosen variance contract. In order to make the variance and volatility payoffs agree in value and volatility sensitivity (the first derivative with respect to $\sigma$ ), we can choose the following approximation:  

$$
\sigma-K_{\mathrm{vol}}\approx\frac{1}{2K_{\mathrm{vol}}}(\sigma^{2}-K_{\mathrm{vol}}^{2})
$$  

The above states that $(1/2K_{\mathrm{vol}})$ variance contracts with a strike $K_{\mathrm{vol}}$ can be used to approximate a volatility swap with a notional of. $(\$1/\mathrm{vol}$ point) for realized volatilities near $K_{\mathrm{vol}}$ . This naive approximation would also mean that the fair price of future volatility (the stroke for which the volatility swap has zero value) is simply the square root of the fair variance, that is,. $K_{\mathrm{vol}}=\sqrt{K_{\mathrm{var}}}$ Figure 15.10 plots the left-hand side and the right-hand side of Eq. (15.59) for different values of realized volatility and a strike price $K_{\mathrm{vol}}=16\%$ . The payoff of the volatility swap is represented by the dashed line and the pay-. off of the variance swap is represented by the solid parabola. The figure shows that the actual volatility swap and the corresponding approximation based on a variance swap different considerably when future realized volatility is far away from the strike price. We see that the naive approximation  

![](d43bf318f149c97c55399c4e5d03c2fb1e133a9744c4c5f3a9a109fac962bd3a.jpg)  

# FIGURE 15.10  

Payoff of variance and volatility swaps.  

represented by Eq. (15.59) does not work well since it leads to variance swap payoffs that are always greater than the volatility swap payoff. The difference between the two payoffs is called the convexity bias:  

$$
\mathrm{Convexitybias}\approx\frac{1}{2K_{\mathrm{vol}}}(\sigma^{2}-K_{\mathrm{vol}}^{2})
$$  

The implication of this is that due to the square term, which is always positive, the fair delivery price for volatility $K_{\mathrm{vol}}$ would lead to higher payoffs from a long variance swap than a long volatility swap position. One approach to correct for this is to lower the fair strike $K_{\mathrm{vol}}$ for a volatility contract so that it is lower than the square root of the fair stroke for a variance contract $K_{\mathrm{var}}$ $K_{\mathrm{vol}}<\sqrt{K_{\mathrm{var}}}$ . This could be graphically represented by a shift in the dashed line in Figure 15.10 to the left, so that it does not always lie below the parabola.  

So far we have discussed the static replication of variance swap by means of a volatility swap. In theory, the mismatch and convexity bias mentioned above could be addressed by dynamically trading variance swap contracts during the life of the volatility swap. The intuition for this is similar to the replication of a nonlinear stock option payoff by means of delta-hedging using the linear. underlying stock price. In practice, unfortunately, there is no liquid market for variance swaps that would allow such dynamic trading of the underlying. If a liquid variance swap market was to develop in the future, then our financial engineering principles provide us with guidance on how such a dynamic replication could be implemented. When we discussed the replication of call and put options we saw that the optimal hedge ratio depends on the assumed future volatility of the underlying (stock). Here the dynamic replication of a volatility swap also requires a model for the. volatility of volatility. In other works, the replication strategy would require holding continuous variance-delta equivalent of variance contracts to hedge the volatility derivative. Such a practical implementation would require an arbitrage-free model for the stochastic evaluation of the volatility surface. The next chapter will describe the volatility surface in more detail.  

# 15.7.2.2 The role of convexity in the volatility trading market during the GFC  

In response to the large losses on variance swaps, some banks, in 2009, decided to offer simpler volatility products to clients. In response to hedge fund client demand in Asia in the second quarter of 2009, BNP Paribas brought back volatility swaps which first traded in the late 1990s. Since the volatility swap has a payoff that depends on the volatility and not the variance, it does not have the same convexity as the variance swap. The downside is that it gives less of a profit to investors that long the volatility swap when volatility rises significantly.  

Another downside of volatility swaps is that they do not have the same theoretical replication as variance swaps.  

One of the few banks that continued to offer variance swap was Societe Generale. The bank was able to do this since it reduced risk in early 2008, earlier and by more than many of its competitors. Thus it was better placed to continue to offer variance swaps when the crisis worsened. As we discussed earlier long only clients find variance swaps attractive due to the convexity and additional profit and loss potential that goes with it. From the dealer or market maker perspective variance swaps are theoretically easier to hedge than volatility swaps since they can be replicated with vanilla options, although dealers use different hedging models and practices.  

Innovation in the variance trading has continued and in March 2009, SG CIB started offering an American variance swap. This product embeds an option that allows investors to close their swap position before maturity at its realized value only. The benefit to SG CIB is that the product gives it the right to exist in the trade, which means that it can sell volatility to the client at a lower price.  

In 2009, market participants were very risk averse and often too scared to trade volatility as an asset class. For those willing to take volatility risk, the American variance swap offered an alternative in a very uncertain environment.  

The above reading illustrates that the market for volatility works like any other market in the sense that it responds to supply and demand. Since 2009, market conditions have improved and volatility has dropped to precrisis levels. While the Vix reached a level of 80 on November 20, 2008, it then fell to around 40 by the end of March 2009 and traded around 11 by June 2014. If volatility was to remain at these pre-GFC levels, then variance swaps may be viewed again more favorably than volatility swaps again, since the breakeven points on the upside, beyond which variance are more profitable than volatility swaps, will fall. The return on the variance swaps for a market maker will depend on the level of volatility and the liquidity of stock options required to hedge variance positions.  

# 15.7.3 INTRODUCTION TO VOLATILITY AS AN ASSET CLASS  

Acceptance of implied volatility and implied correlation as an asset class is growing. The main players are (i) institutional investors, (ii) hedge funds, and (iii) banks. This increased liquidity facil-. itates the engineering of structured products with embedded volatility.  

# EXAMPLE  

It appears that institutional investors are migrating to four types of strategies for going long exposure to implied volatility. Among the largest institutional investors, variance swap-based strategies are the most popular.  

Variance swaps offer the easiest and most liquid way to get exposure to volatility. Institutional investors and hedge funds are the target audience for the new services offered in this field. These services enable customers to trade variance swaps through Bloomberg terminals. Volumes in the inter-dealer market and with clients prompted the move. Variance swaps are used to go long or short volatility on an index or equity with a selected maturity.  

Pure volatility instruments, such as volatility swaps and variance swaps, make sense for institutional. investors, because volatility is both a diversifier on the downside and a global hedge on an equity portfolio. Institutional investors such as pension funds and insurance companies clearly need to diversify. While. they are moving to other asset classes, such as hedge funds, they also do not want to reduce their exposure to equity markets, particularly if there is a good chance of equity markets performing well. With this in mind, they are increasingly turning to long-term volatility strangles..  

The main external driver of the current ongoing rise in volatility is M & A activity.  

Requests for forward volatility strategies to hedge structured products are also on the rise, particularly. among private banks. These strategies fit their needs, as dealers sold a lot of forward volatility certificates and warrants to them last year..  

(Thomson Reuters IFR, 2004)  

# 15.7.4 POST-GFC REGULATION, STANDARDIZATION AND EXCHANGE TRADED VOLATILITY PRODUCTS  

In addition to supply and demand the market for volatility is also influenced by regulation. OTC. derivatives regulation in Europe and the United States is pushing markets toward standardization and exchange trading.  

# 15.7.4.1 Variance futures  

The properties of the CBOE Volatility Index, or VIX, are now relatively well understood.13. The Vix has a negative correlation with the S&P500 and this correlation tends to increase in crisis times. Thus the VIX can be used as a hedge or a "tail risk' hedge against extreme negative events.. Unfortunately, the VIX is just a mathematical formula and not an investable index. It is not tradable and cannot be purchased. Fortunately there are several ways to benefit from a rise in the VIX by using exchange traded instruments: VIX futures, variance futures, VIX options, S&P options and volatility-related exchange traded funds (ETFs) and exchange traded notes (ETNs). There is also a myriad of over-the-counter products linked to the VIX..  

On December 10, 2012, the CBOE listed the S&P 500 Variance futures.  

The contract is not a variance swap since it depends on the realized variance of the S&P500, but it does allow investors to speculate on the realized S&P500 volatility. Figure 15.11 shows the open interest and volume of the S&P500 variance futures from 2012 until 2013.  

Below is a term sheet for the S&P500 Variance Futures  

<html><body><table><tr><td>Description:</td><td>S&P5ooVariancefutures areexchange-tradedfuturescontractsbasedontherealized varianceoftheS&P500CompositeStockPriceIndex(S&P500).Thefinalsettlement valueforthecontractwillbedeterminedbasedonastandardizedformulaforcalculating the realizedvariance of the S&P 5o0 measured from the time of initiallisting until</td></tr><tr><td>Contractsize:</td><td>expirationofthecontract.Thestandardformulainputsfordiscountfactor anddaily interestratearedeterminedby theExchange.</td></tr><tr><td>Tradinghours:</td><td>One contract equals one variance unit. 8:30 a.m.-3:15 p.m.(Chicago time). AllOrders,quotes,cancellations and OrdermodificationsforS&P5ooVariancefutures</td></tr><tr><td></td><td>during trading hours must be received by the Exchange by no later than 3:14:59 p.m. Chicago time andwillbe automatically rejected if received by theExchange during trading hours after 3:14:59 p.m.Chicagotime.</td></tr><tr><td>Contractmonths:</td><td>thelistedcontractmonthsforS&P500IndexoptionslistedonChicagoBoard Options Exchange,Incorporated (CBOE).</td></tr></table></body></html>  

![](0fc88a9dd02ecf7936ce77e58470540097f6e05d16d631e390e963e4f19f5b50.jpg)  
S&P500 VARIANCE FUTURES   
Source: CBOE  

# FIGURE 15.11  

Open interest and volume of the S&P500 variance futures.  

In addition to the S&P500 VIX and Variance futures, the CBOE offers futures on several other US equity indices such as  

VSW CBOE Short-Term Volatility Index Futures (VSW) VX CBOE S&P 500 Volatility Index (VIX) Futures  
