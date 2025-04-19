---
tags:
  - bid_ask_spread
  - bond_markets
  - decimalization
  - interest_rates
  - market_conventions
aliases:
  - Bid-Offer Spread
  - Decimalization
  - Market Conventions
key_concepts:
  - Bid and ask prices
  - Bond market quotes
  - Decimalization impact
  - Interest rate quotes
  - Market conventions
---

# 2.5 MARKET CONVENTIONS  

Market conventions often cause confusion in the study of financial engineering. Yet, it is very. important to be aware of the conventions underlying the trades and the instruments. In this section, we briefly review some of these conventions..  

Conventions vary according to the location and the type of instrument one is concerned with. Two instruments that are quite similar may be quoted in very different ways. What is quoted and the way it is quoted are important.  

As mentioned, in Chapter 1 in financial markets there are always two prices. There is the price at which a market maker is willing to buy the underlying asset and the price at which he or she is. willing to sell it. The price at which the market maker is willing to buy is called the bid price. The. ask price is the price at which the market maker is willing to sell. In London financial markets, the. ask price is called an offer. Thus, the bid-ask spread becomes the bid-offer spread..  

As an example consider the case of deposits in London money and FX markets, where the convention is to quote the asking interest rate first. For example, a typical quote on interest rates would be as follows:  

<html><body><table><tr><td>Ask (Offer)</td><td>Bid</td></tr><tr><td>S</td><td>58</td></tr></table></body></html>  

In other money centers, interest rates are quoted the other way around. The first rate is the bid, the second is the ask rate. Hence, the same rates will look as such:.  

<html><body><table><tr><td>Bid</td><td>Ask (Offer)</td></tr><tr><td>5% 54</td><td></td></tr></table></body></html>  

A second characteristic of the quotes is decimalization. The Eurodollar interest rates in London. are quoted to the nearest $\frac{1}{16}$ or sometimes ${\frac{1}{32}}.$ But many money centers quote interest rates to two decimal points. Decimalization is not a completely straightforward issue from the point of view of brokers/dealers. Note that with decimalization, the bid-ask spreads may narrow all the way down to zero, and there will be no minimum bid-ask spread. This may mean lower trading profits, everything else being the same.  

# 2.5.1 WHAT TO QUOTE  

Another set of conventions concerns what to quote. For example, when a trader receives a call, he or she might say, "I sell a bond at a price of 95," or instead, he or she might say, "I sell a bond at yield $5\%$ ." Markets prefer to work with conventions to avoid potential misunderstandings and to economize time. Equity markets quote individual stock prices. On most stock exchanges including the NYSE, the quotes are to decimal points.  

Most bond markets quote prices rather than yields, with the exception of short-term T-bills. For example, the price of a bond may be quoted as follows:  

<html><body><table><tr><td>Bid Price</td><td>Ask (Offer) Price</td></tr><tr><td>90.45</td><td>90.57</td></tr></table></body></html>  

The first quote is the price a market maker is willing to pay for a bond. The second is the price. at which the market maker dealer is willing to sell the same bond. Note that according to this, bond prices are quoted to two decimal points, out of a par value of 100, regardless of the true denomina-. tion of the bond.  

It is also possible that a market quotes neither a price nor a yield. For example, caps, floors, and swaptions often quote "volatility" directly. Swap markets prefer to quote the "spread' (in the case of USD swaps) or the swap rate itself (Euro-denominated swaps). The choice of what to quote is not a trivial matter. It affects pricing as well as risk management..  
