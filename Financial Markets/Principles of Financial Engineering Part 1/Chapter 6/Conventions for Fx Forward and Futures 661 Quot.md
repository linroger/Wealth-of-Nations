---
tags:
  - '#bid_ask_spread'
  - '#cme_currency_contracts'
  - '#eur_usd'
  - '#exchange_traded_derivatives'
  - '#forward_points'
  - '#fx_forward_quotes'
  - '#fx_futures'
  - '#fx_market_conventions'
  - '#otc_fx_market'
  - '#spot_exchange_rate'
---
# 6.6 CONVENTIONS FOR FX FORWARD AND FUTURES 6.6.1 QUOTING CONVENTIONS FOR FX FORWARD  

Forwards in foreign currencies have special quotation conventions. Markets do not quote outright. forward rates, but the so-called forward points. The related terminology and conventions are illustrated in the following example.  

# EXAMPLE  

Suppose outright forward EUR/USD quotes are given by and that the spot exchange rate quotes are as given by  

<html><body><table><tr><td>Bid Ask</td></tr><tr><td>1.0210 1.0220</td></tr></table></body></html>  

<html><body><table><tr><td>Bid</td><td>Ask</td></tr><tr><td>1.0202 1.0205</td><td></td></tr></table></body></html>  

Then, instead of the outright forward quotes, traders prefer to quote the forward points obtained by subtracting the corresponding spot rate from the outright forward:.  

<html><body><table><tr><td>Bid Ask</td><td></td></tr><tr><td>8</td><td></td></tr></table></body></html>  

In reality, forward points are determined directly from Eq. (6.5) or (6.7).  

Market conventions sometimes yield interesting information concerning trading activity and the. forward FX quotes is a case in point. Let $\boldsymbol{F}_{t_{0}}$ and $e_{t_{0}}$ be time $t_{1}$ forward and time. $t_{0}$ spot exchange rates respectively as given by Eq. (6.5). Using the expression in Eq. (6.5) and ignoring the bid-ask spreads, we can write approximately  

$$
F_{t_{0}}-e_{t_{0}}\cong\left(r_{t_{0}}^{\mathrm{d}}-r_{t_{0}}^{\mathrm{f}}\right)\left(\frac{t_{1}-t_{0}}{360}\right)e_{t_{0}}
$$  

where $r_{t_{0}}^{\mathrm{d}},r_{t_{0}}^{\mathrm{f}}$ are the relevant interest rates in domestic and foreign currencies, respectively.13. Forward points are the difference between the forward rate found using the pricing equation in formula (6.21) and the spot exchange rate:  

$$
F_{t_{0}}-e_{t_{0}}
$$  

They are also called "pips"' and written as bid/ask. We give an example for the way forward points are quoted and used.  

# EXAMPLE  

Suppose the spot and forward rate quotes are as follows:  

<html><body><table><tr><td>EUR/USD Bid</td><td>Ask</td></tr><tr><td>Spot 0.8567</td><td>0.8572</td></tr><tr><td>1 Year -28.3</td><td>-27.3</td></tr><tr><td>2 Year 44.00</td><td>54.00</td></tr></table></body></html>  

From this table, we can calculate the outright forward exchange rate $\boldsymbol{F}_{t_{0}}$  

For year 1, subtract the negative pips in order to get the outright forward rates:  

$$
\left(0.8567-{\frac{28.3}{10,000}}\right)\left/\left(0.8572-{\frac{27.3}{10,000}}\right)\right.
$$  

For year 2, the quoted pips are positive. Thus, we add the positive points to get the outright forward rates:  

$$
\left(0.8567+{\frac{44}{10,000}}\right)\left/\left(0.8572+{\frac{54}{10,000}}\right)\right.
$$  

Forward points give the amount needed to adjust the spot rate in order to obtain the outright forward exchange rate. Depending on the market, they are either added to or subtracted from the spot exchange rate. We should discuss briefly some related conventions.  

There are two cases of interest. First, suppose we are given the following forward point quotes (second row) and spot rate quotes (first row) for EUR/USD:  

<html><body><table><tr><td>Bid</td><td>Ask</td></tr><tr><td>1.0110</td><td>1.0120</td></tr><tr><td>12</td><td>16</td></tr></table></body></html>  

Next note that the forward point listed in the "bid' column is lower than the forward point listed in the "ask"' column. If forward point quotes are presented this way, then the points will be added. to the last two digits of the corresponding spot rate.  

Thus, we will obtain  

Note that the bid-ask spread on the forward outright will be greater than the bid-ask spread on the spot.  

Second, suppose, we have the following quotes:  

<html><body><table><tr><td>Bid</td><td>Ask</td></tr><tr><td>1.0110</td><td>1.0120</td></tr><tr><td>23</td><td>18</td></tr></table></body></html>  

Here the situation is reversed. The forward point listed in the "bid"' column is greater than the. forward point listed in the "ask" column. Under these conditions, the forward points will be subtracted from the last two digits of the corresponding spot rate. Thus, we will obtain.  

Note that the bid-ask spread on the forward outright will again be greater than the bid-ask spread on the spot. This second case is due to the fact that sometimes the minus sign is ignored in quotations of forward points.  

# 6.6.2 FX FORWARD VERSUS FX FUTURES  

The OTC FX market turnover has historically dwarfed trading volume of standardized FX products. on exchanges. According to the BIS, in 2013, the OTC FX market was about 17 times larger than the exchange-traded FX derivatives market. Although market participants typically use forward. instead of futures for FX trading, it is instructive to review contract specifications of FX futures..  

FX futures contracts exist on many currency pairs. The CME, for example, offers the following. currency contract: EUR/USD, JPY/USD, GBP, USD, CHF/USD, CDN/USD, AUD/USD, MXN/ USD, NZD/USD, RUB/USD, ZAR/USD, BRL/USD, and most recently RMB/USD and KRW/ USD. Major cross-rate contracts include EUR/GBP, EUR/JPY, EUR/CHF, GBP/CHF, and others..  

Exchange-traded currency futures have historically differed from OTC FX transactions in terms. of their standardization and flexibility or customization inherent in working with a dealer. However, derivatives exchanges are introducing greater degrees of flexibility in their trading prac-. tices. FX futures are predominantly traded electronically. The typical contract calls for delivery of. a specified currency, or a cash settlement, during the months of March, June, September, and December.  
