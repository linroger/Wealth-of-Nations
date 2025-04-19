---
tags:
  - cds
  - convexity
  - credit_markets
  - credit_skew_trade
  - gfc
  - index_arbitrage
  - liquidity
  - restructuring
aliases:
  - Credit Index Arbitrage
  - Index Arbitrage
key_concepts:
  - Convexity issue in credit
  - Credit skew trade
  - Index arbitrage in equity
  - Real-world complications
  - Restructuring risk valuation
  - Single-name CDSs
  - Synthetic futures contract
---

# 21.5 INDEX ARBITRAGE  

Index arbitrage is well known in equity markets. A stock index is made of a given and known number of stocks. The Index itself can be traded in the futures markets. The carry strategy applies and. by buying (short selling) the underlying stocks, one can create a synthetic futures contract which can be used to take arbitrage positions on the stock index.9  

By analogy one can define index arbitrage in credit as positioning in the index itself versus its. underlying reference names using the single-name CDSs. In equity markets, this strategy is reason-. able. In credit markets, it faces several complications even though theoretically it sounds similar. One issue is the liquidity of single-name CDSs. In an index consisting of 125 names, not all underlying. CDSs may be liquid. The bid-ask spreads for these individual CDSs may be too wide in many cases and trading the underlying against the index may become too costly.  

# 21.5.1 REAL-WORLD COMPLICATIONS  

There are two major issues that lead to different valuations in the index versus its constituents. The. first is the differential treatment of restructuring. The second is a technical issue and deals with the convexity of the index versus the underlying CDSs. Credit index arbitrage is possible, but only after taking into account such divergences explicitly.  

First note that as mentioned in Chapter 18, CDX indices trade with no restructuring. Yet, the. CDSs for most of the IG credits treat restructuring as a credit event.10 To correct for this valuation. difference, the value of the restructuring risk must be subtracted from the individual CDSs. This value, however, is not observed separately and has to be "estimated.".  

The convexity issue is more technical. Fixed-income instruments have convexity as discussed previously, whereas equity does not. This also differentiates index arbitrage in credit from the index arbitrage in equity. Consider the 5-year CDS with a CDS rate $\mathrm{cds}_{t}^{j}$ bps for the jth name in the reference portfolio. As the underlying CDS rate changes, the market value of the future CDS coupon payments will change nonlinearly since the fixed coupons will be discounted using discount factors that will be a function of survival probabilities." According to this, the CDS value would. be a nonlinear function of the $\mathrm{cds}_{t}^{j}$ , the CDS rate, which leads to convexity gains..  

On the other hand, an investor to the credit index receives a single coupon. The convexity of this cash flow will be different from the convexity of the portfolio of underlying CDSs, since the convexity of the average is different from the simple average of convexities. The effects of convexity and of restructuring should be taken out explicitly in order to come up with a fair value for the index.  

# 21.5.2 CREDIT SKEW TRADE  

We had seen earlier that volumes in single-name CDS trading have declined since the GFC. The following reading illustrates the interaction between regulation related to banks' capital require-. ments, index arbitrage activity, and liquidity in the single-name CDS market. Following the GFC. capital requirements for banks have increased and this has increased the funding costs for certain. trades. The index skew in the credit markets refers to the fair value or market value of the index. versus its theoretical value. The skew is the difference between the value of the index using all of the underlying credit names and where the index is actually trading. In general, a positive skew. implies that the skew is trading wider than its fair value..  

# EXAMPLE  

Credit index arb trades under threat  

Dealers look to sell legacy books ahead of introduction of leverage rule Dealers are concerned that credit index arbitrage activity could be largely killed off by the coming introduction of a leverage ratio restriction on banks, further draining liquidity from the single-name CDS market as well as punishing banks with large legacy books..  

Arbitraging the difference between CDS indices and their underlying single-name components-often referred to as "skew"-is a favourite trade of market makers and hedge funds.  

But this activity becomes hugely punitive under the proposed leverage ratio rules as they currently stand. Dealers will only be able to net out long and short positions if they match precisely when executed with the same counterparty or if they face a clearing house, effectively ruling out skew trading..  

"Skew is a big problem for the banks, and it could be a big problem for liquidity. Roughly a third of. liquidity in investment-grade CDS comes from skew activity. Funds are worried where the liquidity on single names comes from if that goes away," said the head of European credit trading at a major bank..  

Single-name CDS tend to lag credit spread movements on indices, which are investors' first port of call to hedge macro exposures. By lining up all the single-name CDS constituents in iTraxx Main versus the index itself, traders can pick up a handful of basis points for ironing out the discrepancy.  

It is a regular trade for sophisticated hedge funds, but dealers print skew packages as well to keep on their own books as a trading position, while also providing liquidity to the market. This type of activity has already become harder to carry off as liquidity in single-name CDS has dwindled since the financial crisis. These days, it is usually necessary to include multiple dealers in a package in order for a trader to line up all of the 125 single-name CDS in iTraxx Main in sufficient size, as banks' balance sheets have come under increasing pressure.  

Legacy issues  

Many dealers have large legacy skew books sitting on their balance sheets, which look set to get clobbered by the leverage ratio. The current proposals focus on gross notional derivatives exposures and have strict rules about netting down positions. Even though a skew package is market risk neutral--buying the single names versus selling the index-such positions do not net.  

(Thomson Reuters IFR, 10 January 2014, "Credit index arb trades under threat', by Christopher Whittall)  

The above reading illustrates the importance of index arbitrage or skew trading for single-name CDS liquidity. The liquidity in single-name CDS is driven not only by regulation and capital. requirements related to CDS markets but also to CDO and securitized products. The example shows the important role that regulation plays in the application of financial engineering principles and. real-world arbitrage strategies.  
