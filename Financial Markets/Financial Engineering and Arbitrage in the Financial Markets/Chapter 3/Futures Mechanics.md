---
tags:
  - futures_mechanics
  - interest_rate_futures
  - marking_to_market
  - physical_commodities
  - variation_margin
aliases:
  - Commodity Futures
  - Futures Trading
key_concepts:
  - Futures trading mechanics
  - Lock in purchase price
  - Physical commodity contracts
  - Two-way insurance contract
  - Variation margin calculation
---

# 3.2 FUTURES MECHANICS  

We will review the mechanics of futures trading and marking-to-market starting with physical commodities. This is an intuitive case: each contract represents a defined quantity of the commodity and the variation margin per contract settles the price change times the quantity of the commodity. Next, we move to interest rate futures where there is no "quantity, but the contract multiplier is chosen to mimic the settlement of interest payments on a principal amount. We will then cover stock indexes where the multiplier is an arbitrary number converting index points to dollars, but can be interpreted as defining the dollar amount of stocks in the cashand-carry arbitrage. Lastly, we will cover currencies. Currencies are physical commodities; contract sizes are defined with standard quantities..  

# 3.2.1 Physical Commodity Futures  

It is Thursday, October 29, 2009. On the Chicago Board of Trade (CBT  this was acquired by the Chicago Mercantile Exchange, CME, in July 2007), corn and soybean futures trade at the prices shown in Table 3.1..  

Suppose that, hoping to lock in the purchase price on 10,o00 bushels of corn, we bought two corn contracts at $206\%$ cents per bushel on Thursday before the close. Subsequent to that, we observe the progression of corn futures prices for delivery in December of 2009 as in Table 3.2.  

Table 3.1 Physical commodity contracts   


<html><body><table><tr><td></td><td>Open</td><td>High</td><td>Low</td><td>Settle</td><td>Openinterest</td></tr><tr><td colspan="6">Corn(CBT)5000bu;centsperbu</td></tr><tr><td>Nov2009</td><td>2013/4</td><td>2021/2</td><td>2011/2</td><td>202</td><td>2,429</td></tr><tr><td>Dec2009</td><td>206</td><td>207′/2</td><td>2051/2</td><td>2061/2</td><td>211,016</td></tr><tr><td>Mar2010</td><td>2183/4</td><td>2201/4</td><td>2181/4</td><td>219</td><td>112,379</td></tr><tr><td colspan="6">Soybeans (CBT)5,000 bu;cents per bu</td></tr><tr><td>Nov2009</td><td>4231/2</td><td>430</td><td>4231/4</td><td>4281/4</td><td>75,068</td></tr><tr><td>Mar2010</td><td>436/2</td><td>4431/4</td><td>4361/4</td><td>4411/4</td><td>28,917</td></tr></table></body></html>  

Table 3.2 Price path for corn starting at $206\%$   


<html><body><table><tr><td>Date</td><td>Dec09 futures price</td></tr><tr><td>Fri,Oct302009</td><td>2071/4</td></tr><tr><td>Mon,Nov022009</td><td>2063/4</td></tr><tr><td></td><td></td></tr><tr><td>Fri,Dec182009</td><td>210</td></tr></table></body></html>  

Since the price of corn is quoted in cents per bushel, and as each contract represents 5,000 bushels, each 1 cent change in the price of corn translates into a $\$50$ change in the total value of one contract $(5,000\times\mathbb{\S}0.01)$ . While not commonly used with physical commodities, for continuity of exposition, we can adopt the terminology of index futures and refer to the $\$50$ number as the multiplier. The variation margin (MTM) amounts for each day are computed in Table 3.3.  

Having bought two contracts on Thursday, we receive. $\$75$ into our account as the price rises to $207\%$ on Friday, we pay $\$50$ out of our account as the price drops to. $206\%$ on Monday, etc. As the price fluctuates we receive or pay cash daily between October 2009 and the final. settlement on December 18, 2009. If, on that day, the price is 210, then the net cash gain in our account is $\$350$ . The net (cumulative) variation margin on any day, which is the sum of. daily MTM settlement amounts, can be computed as the difference between that day's (final) price minus the original price times the number of contracts times the multiplier, as all the intermediate daily prices cancel out.  

If the purpose of buying two contracts at $206\%$ in October was to lock in the purchase price. of 10,o00 bushels of corn for delivery in December, then we have accomplished our goal. The corn will cost. $10,000\times\mathbb{\mathbb{9}}2.10=\mathbb{\mathbb{9}}21,000$ on December 18, but the $\$350$ gain will reduce our. net cost to $\$20,650$ , which translates to. $\$2.065$ per bushel.  

In fact, our net price will be $\$2.065$ no matter what the price of corn in December. Suppose the price fluctuations between October and December were as shown in Table 3.4. On December 18, 2009, we pay $10,000\times\$189.25=\$18,925$ for corn, but including the MTM loss on the futures of $\$1,725$ , our total cost is $\$20,650$ or $\$2.065$ per bushel. It is easy to see that the futures contracts provide a cash inflow or outflow (depending on the direction of the price movement) equal to the final spot price of corn minus the original lock-in price times the desired number of bushels of corn. The futures contracts act as a two-way insurance contract, insuring the. buyer against the price increase and the seller against the price decrease.  

Table 3.3MTM calculation for two contracts bought at $206\%$   


<html><body><table><tr><td>Date</td><td>Daily calculation</td><td>MTM (VM)</td><td>Net var. margin</td></tr><tr><td>Fri,Oct302009</td><td>2 × (207.25-206.50)× $50</td><td>+ $75.00</td><td>+ $ 75.00</td></tr><tr><td>Mon,Nov022009</td><td>2 × (206.75-207.25) × $50</td><td>$50.00</td><td>+$ 25.00</td></tr><tr><td>Fri,Dec182009</td><td>2 × (210.00-...)x $50</td><td></td><td>+ $350.00</td></tr></table></body></html>  

Table 3.4MTM calculation for two contracts bought at $206\%$   


<html><body><table><tr><td>Date</td><td>Settleprice</td><td>Daily calculation</td><td>MTM (VM)</td><td>Net var. margin</td></tr><tr><td>Fri,Oct302009</td><td>2083/4</td><td>2 ×(208.75-206.50) × $50</td><td>+ $225.00</td><td>+ $225.00</td></tr><tr><td>Mon,Nov022009</td><td>2021/2</td><td>2 × (202.50-208.75) × $50</td><td>$625.00</td><td>+ $400.00</td></tr><tr><td>Fri,Dec182009</td><td>1891/4</td><td>2 × (189.25-...)x $50</td><td></td><td>$1,725.00</td></tr></table></body></html>  

Of course, the original intention of going long two December contracts in October may not have been to lock in a purchase price of corn, but simply to speculate that the (futures) price will rise. In that case, the speculator has to sell the two contracts at some point to avoid taking delivery of the corn. If the price followed the path in Table 3.4, and the speculator chose to unwind at the close on December 18 (as many do), she would have lost $\$1,725$ through MTM settlements throughout the life of her position. She also could have exited her position, wholly or partially, anytime in between. For example, she could have sold one contract earlier. on Friday, October 30, as the price rose to $208\%$ , and the other at $189\%$ on December 18. Table 3.5 shows two ways to compute her total gain/loss: one by computing the net MTM on two contracts through October 30 plus the net MTM on one contract from October 30 to. December 18; and the second by computing the net MTM on one contract October 29 through October 30 plus the net MTM on one contract October 29 through December 18.  

The day-by-day calculation shows the real cash flows incurred (cash accounting); the contract-by-contract calculation follows accrual accounting of closed positions.  

To test the understanding of futures mechanics, let us solve the following scenario using the prices in Table 3.1. A soybean farmer wants to lock in the sale price of. $441\%$ cents per bushel on 30,000 bushels of soybeans in March 2010. He also thinks that March futures prices will drop to 420 by November 18, 2009, so, in addition to locking price, he wants to speculate on. another 10,ooo bushels. What should he do?.  

The strategy will be to sell eight contracts now, buy back two contracts in November, and. leave the remaining six contracts short until March. One outcome of the scenario is shown in Table 3.6.  

The farmer collects $30,000\times\:\mathbb{\S}4.765=\mathbb{\S}142,950$ for the corn minus the MTM loss of $\$10,575$ on the six contracts held to expiry, or the net of $\$132,375$ . The latter represents 30,000 bushels at $\$4.4125$ . In addition, the farmer made $\$2,125$ on two March contracts shorted in October and closed out (bought) in November.  

Table 3.5 Partial unwind of one of two contracts bought at $206\%$   


<html><body><table><tr><td>Date</td><td>Settleprice</td><td>Calculation</td><td>MTM (VM)</td><td>Net var. margin</td></tr><tr><td>By date</td><td></td><td></td><td></td><td></td></tr><tr><td>Fri,Oct30 2009</td><td>2083/4</td><td>2 × (208.75-206.50)× $50</td><td>+ $225.00</td><td></td></tr><tr><td>Fri,Dec182009</td><td>1891/4</td><td>1 x (189.25-208.75) × $50</td><td>$975.00</td><td>$750.00</td></tr><tr><td>Bycontract</td><td></td><td></td><td></td><td></td></tr><tr><td>Fri,Oct302009</td><td>2083/4</td><td>1× (208.75-206.50) × $50</td><td>+ $112.50</td><td></td></tr><tr><td>Fri,Dec182009</td><td>1891/4</td><td>1×(189.25-206.50)× $50</td><td>-$862.50</td><td>-$750.00</td></tr></table></body></html>  

Table 3.6 Short soybean strategy at $441\%$   


<html><body><table><tr><td>Date</td><td>Settleprice</td><td>Calculation</td><td>Netvar.margin</td></tr><tr><td>Speculativepart</td><td></td><td></td><td></td></tr><tr><td>Wed,Nov182009</td><td>420</td><td>-2 ×(420.00-441.25)× $50</td><td>+$2,125</td></tr><tr><td>Lock-inpart</td><td></td><td></td><td></td></tr><tr><td>Fri,Mar192010</td><td>476/2</td><td>-6×(476.50-441.25)× $50</td><td>$10,575</td></tr></table></body></html>  

# 3.2.2 Interest Rate Futures  

The mechanics of MTM settlement of interest rate futures are similar to those for physical commodity futures. The daily variation margin is equal to the number of contracts times the daily change in futures price, times the multiplier, which reflects the number of bonds in each contract. However, bonds and credit arrangements differ from stocks, currencies, and commodities in that they are rights to contractually defined future cash flows (interest and principal), thus the value of the bond can be equivalently stated in terms of price or yield-to-maturity. Yet, as the value of the commodity fluctuates, the two terms do not change one-for-one (due to convexity). Because of that, interest rate futures fall into two categories: contracts on  

long bond prices, and.   
short-term deposit rates.  

In bond price futures, buyers speculate on, lock in, and receive daily MTM settlements. off the price of a bond eligible to be delivered on the expiry date. In deposit rate futures,. buyers speculate on, lock in, and receive daily MTM settlements off the interest rate that will. be earned (paid) on a deposit of fixed maturity. For consistency, futures on interest rates are constructed to settle off variables that are artificially defined to resemble bond prices, but are really linear transforms of yields. Since real prices are not linear in yields, the two categories of interest rate futures settle the variation margin differently. In addition, most bond price. futures have special features granting short parties multiple delivery options (the time and type. of bond to be delivered is at the short's discretion). Deposit rate futures typically are free from such complications and treat both sides equally.  

# 3.2.2.1Bond Price Futures  

Bond price futures around the world are defined on the basis of actual or artificial bond prices,. not directly on interest rates. For example, on the LIFFE (part of NYSE Euronext group, merged in 2007) in London, the long gilt contract is for GBP 100,000 face value of the long bond issued by the UK government. On the Eurex (incl. the International Securities Exchange (ISE), acquired in 2007), one 10-year Euro-Bund futures contract represents EUR 100,000 of the euro-denominated bond of the German government. Like spot, bond futures prices are quoted as a percentage of par value. On the LIFFE, the gilt contract has a tick size of $0.01\%$ of par, so one tick is equivalent to GBP 10 $(=100,000\times0.01/100)$ . Similarly, on the Chicago. Mercantile Exchange (CME), one Treasury bond contract represents USD 100,o00 face value. of a 30-year Treasury bond and the futures price is quoted as percentage of par value, but with fractions in 32nds (tick size is. $1/32\%$ of par or $\$31.25$ , with half-tick price movements.  

allowed). To compute the variation margin for a given day, one first translates it to a straight percentage, then proceeds the same way as with gilts - that is, divides by 100, and multiplies by the size of the contract USD 100,000. For example, if we shorted five contracts at 112-03 $(=112–3/32$ ) and the price changed to 112-27 $(=112{-}27/32)$ , we would have a loss, or a negative variation margin amount, as shown:  

Calculation for price change to 112-27/32 Var. margin $=-5\times(112{-}27/32-112{-}3/32)\%$ of $\mathbb{S}100,000=-5\times(0.75/100)\times\mathbb{S}100,000=-\mathbb{S}3,750$  

Note that the multiplier, as defined before, is in this case equal to 1,000 $\times100{,}000/100)$ For example, a $0.75\%$ change in the price represents a $\$750$ variation margin per contract. If one wanted to speculate directly on a specific size of an interest rate change and not a bond price change, one would have to base one's bet on the current duration of the underlying bond. To bet on an interest rate increase of $1\%$ for $\$1$ million face value of bonds, one would have to short $[(1/\mathrm{Duration})\times10]$ bond contracts. As interest rates increase by $1\%$ , the value of each of the 10 contracts representing $\$100,000$ face value, for a total of $\$1$ million par value, would decrease by $[1\times$ Duration number of points], producing the desired dollar gain.  

All US Treasury bond and note contracts, and many other government bond contracts, are defined not on one underlying bond but on a set satisfying certain maturity and coupon criteria. (e.g. close in maturity and coupon to the 30-year. $6\%$ mark). The short party to the contract is. given an option to choose which of the eligible bonds to deliver to the long party on the futures expiry date. Each eligible bond is assigned a fixed conversion factor and the short party must deliver the face value equal to. $\$100,000$ times the conversion factor. The conversion factor, based on relative duration, is designed to make all eligible bonds equal in value at the $6\%$ yield. However, as it is a fixed number, the true values of the different bonds eligible to be delivered diverge, giving the short party the option to choose the cheapest-to-deliver alternative. Often, the identity of the cheapest-to-deliver bond changes as yields fluctuate throughout the life of the contract. The short party is also given additional timing options which complicate the. analysis of these contracts. The reason behind embedding the cheapest-to-deliver and timing. options in the contract is to ensure the maximum liquidity of the delivery instruments which. are considered fungible.  

# 3.2.2.2 Eurocurrency Futures  

# Background on Eurocurrency Deposits  

A Eurodollar deposit is a non-negotiable US dollar-denominated interest-bearing loan outside. the US regulators' purview. The interest rate is fixed and quoted on an $A c t/360$ basis and paid as add-on interest at the end. A variety of terms is available, ranging from overnight,. tomorrow/next, 1-day, 1-week, all the way to 12-months; the most popular being a 3-month. deposit with a 2-London-business-day settlement, followed by a 1-month term. The minimum amount is $\$10$ million. Eurodollar lending rates are fixed daily at $4\mathrm{pm}$ GMT by a group of London banks most active in this market in the form of a London Interbank Offered Rate,. or LIBOR, published by the British Bankers' Association (BBA) and widely distributed by wire services and newspapers; the bid on borrowed funds is referred to as LIBID. The LIBOR is the benchmark rate for unrestricted 3-month deposits and swap payment settlements. The Eurodollar market is the largest global money market by volume outstanding and turnover..  

It swamps the within-the-US market for interbank Certificates of Deposits (CDs), regulated by the Federal Reserve and insured by the Federal Deposit Insurance Corporation (FDIC). The interest calculation on the unregulated Eurodollar deposits works as follows. Suppose on Thursday, October 25, 2012, you call a London bank to borrow dollars at the LIBOR interest rate of $2.31\%$ for a term of 3 months. Your interest accrual period runs from October 25, 2012 to Friday, January 25, 2013, and your principal and interest payment date is due 2 business days later on Tuesday, January 29, 2013. As there are 92 days in the interest period, your total repayment per $\$1$ million borrowed is as shown:  

Calculation for a 92 day borrow at $2.31\%$ Repayment $\mathbb{S}1,000,000\times(1+0.0231\times92/360)=\mathbb{S}1,005,903.33$  

All major currencies have active unregulated short-term deposit markets. Given its "offshore" location, London is the main center for borrowing and lending in Eurodollars, Euroeuros, Euroyen, Euroswiss, and several other Eurocurrencies. The prefix Euro is unrelated to the euro currency and merely reflects the historical origin of the market for unregulated interbank deposit markets (Soviet dollar balances in Paris banks in the 1960s). Day-count calculations vary from currency to currency. Most banking regulations around the world allow participation in the Eurocurrency market by domestic banks through legally segregated bank facilities.  

# Eurodollar Futures  

The Eurodollar contract on the Chicago Mercantile Exchange (CME) is designed to allow speculating on, and locking in, the interest rate paid or received on a. $\$1$ million 3-month Eurodollar deposit starting on the futures expiry date and ending 90 days later. In order to. align the bond and deposit market language conventions, where buying a bond means lending and selling a bond means borrowing, the Eurodollar contract is quoted on an artificial price basis. The futures price, rather than being a true present value of the principal to be received 3 months later equal to $100/\left(1+L/4\right)$ , is instead defined as linear in the interest rate, but still. made to look like a discount bond price:.  

$$
F=100-L
$$  

where $L$ is the 3-month LIBOR rate with the percentage sign dropped. Buying one futures. contract at a price of 97.69 and holding it to maturity simply means locking in a LIBOR rate of $2.31\%$ $(100.00-97.69)$ on a $\$1$ million loan. Eurodollar futures are settled in cash, and. as there is no physical delivery of any deposit/loan balances, this price convention poses no. problems. At the final settlement on the expiry date - while the futures price $F$ is not the price of a 3-month $\$1$ million discount bond $-\:F$ is automatically set to equal 100 minus the LIBOR fixing rate for that day. Anyone speculating in Eurodollar futures is in fact betting on what the LIBOR rate will be on the expiry date, and the variation margin settlement is off the changes in anticipated LIBOR rates. Because the LIBOR rate is subtracted in constructing the futures price, speculating on the rate going up involves selling futures (to benefit from. the price decline) and speculating on the rate going down involves buying futures (to benefit from the price increase), which is consistent with the direction of bond futures buying and selling. Also, because the LIBOR rate is subtracted in constructing the futures price, hedgers. can always interpret $100-F$ as being the LIBOR rate, $L$ , that can be locked in on that day for a forward deposit starting on the futures expiry date.  

The CME has two LIBOR-based Eurodollar contracts, each defined in artificial $100-L$ price terms. Confusingly, the 1-month contract is referred to as the LIBOR contract and the 3-month contract is referred to as the Eurodollar contract. The CME also lists a similarly defined contract on 13-week T-Bills and 3-month yen deposits, and average price-based Fed Funds contract. The contracts can be traded electronically on the GLOBEX platform and the Eurodollar is cross-listed for floor trading on the Singapore Exchange (SGX). NYSE Euronext's LIFFE floor trades contracts on 3-month deposits denominated in euros, Swiss francs, pounds sterling, and yen, referred to as Euribor (euro LIBOR), Euroswiss, short sterling, and Euroyen contracts having, respectively, EUR 1 million, CHF 1 million, GBP 500,000, and JPY 100 million notional principals. The exchange also lists a shorter EUR 3 million Eonia contract on ECB required reserve balances. Both the CME and the LIFFE offer trading in bundles of successive month Eurocurrency futures, together with options on those futures. The mechanics of variation margin settlement are identical for Eurodollars, Euribor, and Euroswiss (\$25, $\notin25$ , and 25 francs per 0.01 tick); the short sterling and Euroyen requiring only size modifications (tick value being 12.5 for sterling and $\yen1230$ for yen). The settlement of 1-month dollar LIBOR futures and Eonia futures is identical to Eurodollars, i.e. $\$25$ or $\notin25$ per tick, as the size compensates for shorter maturity.  

# Marking-to-Market Variation Margin  

As the stated size of the Eurodollar contract is $\$1$ million, and as the commodity is defined as a 90-day LIBOR deposit, the variation margin settlement has to involve a day-count fraction correction. If LIBOR were to change from $2.50\%$ to $2.60\%$ , which translates into a futures. price change from 97.50 to 97.40, then the variation margin settlement for one long contract would be as shown:.  

Calculation for LIBOR change from $2.50\%$ to $2.60\%$ Var. mar $\begin{array}{l}{\mathrm{gin}=1\times(97.40-\check{9}7.50)/100\times(90/360)\times\S1,000,000}\ {=1\times(-0.10)\times\S2,500=-\S250}\end{array}$  

As the calculation shows, rather than relying on the $\$1$ million size of the contract, the easiest. way to view the mark-to-market settlement formula for Eurodollars is in terms a multiplier of $\$2,500$ per $1\%$ LIBOR change $(=1$ point futures price change). The exchanges define it even more simply by designating a tick size equal to $0.01\%$ LIBOR change, a minimum price. movement currently equal to half the tick for most contracts, and a multiplier equal to $\$25$ per tick. The tick is equivalent to a 1 bp change in LIBOR or 1/100 of the futures price change. For Euribor and Euroswiss contracts, substitute. $\notin25$ or CHF 25 for $\$25$ in the calculations below;. for short sterling and Euroyen contracts, substitute 12.50 or $\yen1,250$ for $\$25$ . Table 3.7 shows the Eurodollar futures for the close of day on Thursday, October 25, 2012.1  

The June 2013 contract closed at 97.48. That contract's underlying commodity is a $\$1$ million deposit placed on June 19, 2013 and redeemed on September 19, 2013. The implied interest rate for that deposit is $100-97.48=2.52\%$ The spot 3-month LIBOR rate on October 25, 2012 is $2.31\%$ , not reported in Table 3.7. For simplicity, we assume exactly 90 days in the June 19-September 19 period.  

Suppose at the close on Thursday, we go long (buy) 1 Eurodollar contract and over the following 2 business days we observe the futures prices shown in Table 3.8..  

Table 3.7  1- and 3-month Eurodollar futures on October 25, 2012   


<html><body><table><tr><td></td><td>Open</td><td>High</td><td>Low</td><td>Settle</td><td>Openinterest</td></tr><tr><td colspan="6">LIBOR 1-m0. (CME): $3,000,000; pts of 100%</td></tr><tr><td>Nov</td><td>97.76</td><td>97.80</td><td>97.74</td><td>97.77</td><td>25,544</td></tr><tr><td>Dec2012</td><td>97.77</td><td>97.81</td><td>97.77</td><td>97.80</td><td>5,875</td></tr><tr><td>Jan2013</td><td>97.91</td><td>97.92</td><td>97.91</td><td>97.92</td><td>3,069</td></tr><tr><td colspan="6">Eurodollar (CME): $1,000,000; pts of 100%</td></tr><tr><td>Nov</td><td>97.79</td><td>97.83</td><td>97.78</td><td>97.81</td><td>41,554</td></tr><tr><td>Dec2012</td><td>97.81</td><td>97.87</td><td>97.80</td><td>97.85</td><td>863,180</td></tr><tr><td>Jan 2013</td><td>97.86</td><td>97.88</td><td>97.86</td><td>97.87</td><td>7,080</td></tr><tr><td>Mar</td><td>97.71</td><td>97.80</td><td>97.80</td><td>97.85</td><td>628,766</td></tr><tr><td>Jun</td><td>97.41</td><td>97.51</td><td>97.41</td><td>97.48</td><td>588,920</td></tr><tr><td>Sep</td><td>96.98</td><td>97.12</td><td>96.98</td><td>97.09</td><td>396,280</td></tr><tr><td>Dec</td><td>96.50</td><td>96.63</td><td>96.47</td><td>96.60</td><td>378,297</td></tr><tr><td>Mar2014</td><td>96.14</td><td>96.25</td><td>96.14</td><td>96.24</td><td>243,043</td></tr></table></body></html>  

Table 3.9 shows that in order to compute the variation margin on one long contract using the $\$25$ per tick multiplier, we simply drop the decimal in the Eurodollar futures prices to convert the daily changes to basis point or tick differences.  

Just as in the corn example, the net variation margin (cumulative gain/loss) of. $\$175$ as of Monday could be computed alternatively from the difference of the Monday close and the original Thursday price:  

$$
1\times(9,755-9,748)\times25=\mathbb{\mathbb{\mathbb{S}}}175
$$  

When the 3-month LIBOR is $3.00\%$ on the last day of trading on June 19, 2013, the last futures price is set to $F=100-L=100.00-3.00=97.00$ , and the net variation margin over October through June is:  

$$
1\times(9,700-9,748)\times25=-\S1,200
$$  

Table 3.8 June 2013 Eurodollar price path starting at 97.48   


<html><body><table><tr><td>Date</td><td>June 2013 futures price</td></tr><tr><td>Fri,Oct262012</td><td>97.44</td></tr><tr><td>Mon,0ct29 2012</td><td>97.55</td></tr><tr><td></td><td></td></tr><tr><td>Wed, Jun19 2013</td><td>97.00</td></tr></table></body></html>  

Table 3.9 MTM calculation for 1 Eurodollar contract bought at 97.48   


<html><body><table><tr><td>Date</td><td>Daily calculation</td><td>MTM (VM)</td><td>Net var. margin</td></tr><tr><td>Fri,Oct262012</td><td>1× (9,744-9,748)× $25</td><td>-$100</td><td>$- 100</td></tr><tr><td>Mon,0ct292012</td><td>1 × (9,755-9,744)× $25</td><td>+ $275</td><td>$+ 175</td></tr><tr><td>Wed,Jun192013</td><td>1 x (9,700-...)x $25</td><td></td><td>-$1,200</td></tr></table></body></html>  

# Locking in a Future LIBOR Rate  

If the original reason we entered into the long contract at 97.48 was to lock in the rate of $2.52\%$ on a $\$1$ million 90-day deposit, and we deposit $\$1$ million at $3.00\%$ on June 19, as planned, then 3 months later we expect to receive interest on that deposit equal to:  

$$
1,000,000\times0.03\times90/360=\mathbb{\mathbb{\mathbb{S}}}7,500
$$  

If we include our loss of. $\$1,200$ on the futures contract, our effective interest rate $R$ earned can be implied from the analogous expression:  

$$
1,000,000\times R\times90/360=56,300=\mathbb{5}7,500-\mathbb{5}1,200
$$  

which turns out to be exactly $2.52\%$ ..  

$$
(7,500-1,200)/1,000,000\times(360/90)=(6,300)/1,000,000\times(360/90)=2.52\mathcal{U}
$$  

Suppose that instead of Eurodollar futures prices following the path in Table 3.8, LIBOR ended up at $2.00\%$ on the last day of trading on June 19. The final settlement price would. be $F=100-L=100.00-2.00=98.00$ . The mark-to-market calculations are shown in. Table 3.10.  

The net variation margin over October through June period is  

$$
1\times(9,800-9,748)\times25=\S1,300
$$  

If, on June 19, we deposit $\$1,000,000$ at $2.00\%$ , our future interest on that deposit will be:  

$$
1,000,000\times0.02\times90/360=\mathbb{\mathbb{\mathbb{S}}}5,000
$$  

Including our gain of $\$1,300$ on the futures contract, our effective interest earned is again  

$$
(5,000+1,300)/1,000,000\times(360/90)=(6,300)/1,000,000\times(360/90)=2.52\mathcal{U}
$$  

In fact, no matter what LIBOR is on June 19, our effective interest rate earned inclusive of the futures gain/loss is $\$6,300$ or $2.52\%$ . Locking in the rate of interest to be earned on any amount is easy with Eurodollar futures; to lock in the rate on $\$25$ million, we buy 25 contracts. Similarly, locking in the rate to be paid on borrowing is easy, we only need to short the. contracts.  

Suppose on October 25, 2012, you want to lock in a rate on a $\$20$ million future loan you hope to get on June 19, 2013, to be repaid on September 19, 2013. You can lock in the rate of $2.52\%$ by shorting 20 Eurodollar contracts now and waiting to borrow spot on June 19.  

Table 3.10 MTM for 1 Eurodollar contract, LIBOR ends at $2.00\%$   


<html><body><table><tr><td>Date</td><td>Settleprice</td><td>Daily calculation</td><td>MTM (VM)</td><td>Net var. margin</td></tr><tr><td>Fri,Oct262012</td><td>97.44</td><td>1 × (9,744 -9,748) × $25</td><td>-$100</td><td>100</td></tr><tr><td>Mon,Oct292012</td><td>97.55</td><td>1 × (9,755-9,744)× $25</td><td>+ $275</td><td>$+ 175</td></tr><tr><td>Wed,Jun192013</td><td>98.00</td><td>1 x (9,800-...)× $25</td><td></td><td>+ $1,300</td></tr></table></body></html>  

If, on June 19, 3-month LIBOR is at. $3.00\%$ and the futures price is at 97.00, then you have. a positive total cash flow from your futures contracts:  

$$
(-20)\times(9,700-9,748)\times25=\mathbb{5}24,000
$$  

You borrow $\$20$ million at. $3.00\%$ to incur interest cost on the loan of:  

$$
20,000,000\times0.03\times(90/360)=\mathbb{\mathbb{S}}150,000
$$  

Including your futures gain, your effective borrowing rate is:  

$$
{\langle0,000-24,000\rangle}/{20},0000,000\times{(360/90)}={(126,000)}/{1,000},000\times{(360/90)}=2.52\mathcal{U}
$$  

If instead of $3.00\%$ , on June 19, LIBOR is at. $2.00\%$ and the futures price is at 98.00, then. you have a negative total cash flow from your futures contracts:  

$$
(-20)\times(9,800-9,748)\times25=\mathbb{5}26,000
$$  

You borrow $\$20$ million at $2.00\%$ to incur interest cost on the loan of:  

$$
20,000,000\times0.02\times(90/360)=\mathbb{\mathbb{S}}100,000
$$  

Including your futures gain, your effective borrowing rate is:  

$$
)0,000+26,000)/20,000,000\times(360/90)=(126,000)/1,000,000\times(360/90)=2.52\mathcal{U}
$$  

You have now locked in a rate of $2.52\%$ in October no matter where LIBOR ends up on June 19.  

Let us provide another application of Eurodollar contracts, that of an extension of lending or borrowing at a guaranteed rate through a rollover or bundling strategy.  

# Bundling and Rollover Rate Lock  

Suppose on October 25, 2012, you have excess funds of $\$600$ million that you want to deposit through December 19, 2013. A London bank quotes a rate of $2.31\%A c t/360$ through December 19, 2012. What rate of interest can you lock in on your balances over the entire 14-month period from October 2012 to December 2013 and how?  

Since each successive Eurodollar contract guarantees a reinvestment rate over the 90-day period following the futures' expiry, the strategy to lock in the overall rate involves depositing the $\$600$ million balance for the next 2 months (until the first futures) and go long an increasing number of successive contracts to reflect the growing balance of principal and interest that needs to be rolled over. The calculation and strategy are shown in Table 3.11.  

Table 3.11  Locking in rollover rates with Eurodollar bundles   


<html><body><table><tr><td>Period</td><td>Days</td><td>Rate</td><td>Futurevaluecalculation</td><td>Strategy</td></tr><tr><td>Oct2012-Dec2012</td><td>55</td><td>2.31%</td><td>600,000,000 ×(1+0.0231×55/360)=602,117,500</td><td>Deposit$600m</td></tr><tr><td>Dec2012-Mar2013</td><td>90</td><td>2.15%</td><td>602,117,500×(1+0.0215×90/360)=605,353,882</td><td>Long 602 Dec</td></tr><tr><td>Mar2013-Jun2013</td><td>90</td><td>2.15%</td><td>605,353,882×(1+0.0215×90/360)=608,607,659</td><td>Long 605 Mar</td></tr><tr><td>Jun2013-Sep2013</td><td>90</td><td>2.52%</td><td>608,607,659 ×(1+0.0252×90/360)=612,441,887</td><td>Long 609 Jun</td></tr><tr><td>Sep2013-Dec2013</td><td>90</td><td>2.91%</td><td>612,441,887 × (1+0.0215× 90/360)=616,897,402</td><td>Long612Sep</td></tr></table></body></html>  

The only inaccuracy in this strategy is the rounding of the principal to the nearest million to arrive at the number of whole contracts to be bought. As successive contracts mature, we roll over the growing deposit for another 90 days using the collected/paid variation margin to offset interest cash flows. We have effectively locked in a simple rate of (16,897,402/ $600,000,000)(360/415)=2.443\%$ on an $\mathrm{Ac}\mathrm{{t}}/360$ basis for the entire period from October 25, 2012 through December 19, 2013. To lock in a borrowing rate we would have computed the same amounts but we would have shorted futures. Also, had we chosen to receive accrued interest in cash instead of reinvesting it, the number of futures contracts traded would have been a constant 600.  

# 3.2.3 Stock Index Futures  

There are two views of stock index futures. First, stock indexes are commodities. The quality is uniform, shares are perfectly substitutable, and are easily traded in bulk. Second, indexes. are not real assets but simply mathematical averages; there is nothing to deliver on a futures contract. Speculating on an index level at a future date is identical to betting on the numerical outcome of a soccer match: a numerical outcome of a random event at a future date. The two views can be reconciled. Indexes are constructed so that their changes mimic one-for-one changes in the value of precisely defined diversified portfolios of stocks. Betting on the value. of the index at some date in the future by buying and selling index futures can serve a useful purpose of hedging the purchase/sale price of a basket of stocks. Indexes may consist of tens or hundreds of different stocks, so to avoid actual physical delivery, index futures are settled in cash via the use of a simple multiplier.  

All major stock indexes around the world have futures traded on them. The CME lists futures on all US stock averages, the Dow, S&P 500, Nasdaq, and several others, in large and mini versions (with smaller multipliers). The CME also trades Asian, emerging markets indexes, and futures on index-tracking ETFs. In Europe, NYSE Euronext's LIFFE trades futures on FTSE 100, CAC-40, and a few other continental indexes, while the Deutsche Borse's EUREX trades futures on the DAX, Swiss SMI, DJ Stoxx 50, and a few others.  

All index futures specify the final settlement value of the contract equal to the index at the close of trading on the expiry date, and the multiplier that converts the point changes of the index into a cash settlement amount in a currency of denomination. The CAC-40 futures on LIFFE are defined as $\sf{\in}10$ times the index, the FTSE 100 contracts are 10 times the. index, and the Mini Nasdaq 100 on the CME is. $\$20$ times the index. Some contracts are. "quantoed"' into an unnatural currency, such as the Nikkei 225 on the CME defined as $\$5$ times the index (there is also a natural yen-denominated contract). While this is not really peculiar (US investors may want a pure play on the Nikkei), the multipliers of the most heavily traded contracts are always defined in the home currency of the index, reflecting the realities of stock trading and index-replicating portfolio construction (index component stocks are bought and sold in home currencies, free of artificial currency risk). The ability to replicate the index with baskets of stocks in the exact proportions of the index has important implications for the spot-futures price relationship through the cost-of-carry equation and cash-and-carry arbitrage.  

The single most popular index future is the S&P 500 contract traded on the CME. The. SPX's tick size is 0.10 index points and the multiplier is. $\$250$ per point or $\$25$ per tick. It is traded open outcry on the floor of the exchange and electronically on the GLOBEX platform on the March-June-September-December cycle. Suppose on Thursday, June 24, 2010, the.  

Table 3.12 S&P 500 futures on Thursday, June 24, 2010   


<html><body><table><tr><td></td><td>Open</td><td>High</td><td>Low</td><td>Settle</td><td>Openinterest</td></tr><tr><td colspan="6">S&P500(CME);$250×index</td></tr><tr><td>Sep2010</td><td></td><td></td><td></td><td>978.00</td><td></td></tr><tr><td>Dec2010</td><td></td><td></td><td></td><td>976.10</td><td></td></tr><tr><td>Mar2011</td><td></td><td></td><td></td><td>974.20</td><td></td></tr><tr><td colspan="6">S&P500indexclosedat978.80;3-monthLIBORat1.107%Act/360=1.13%cont.</td></tr></table></body></html>  

S&P 500 index closes at 978.80 (spot index) and the S&P500 futures settle at the levels shown in Table 3.12.  

While the S&P 500 index is not a price of anything, but rather a capitalization-weighted average of the values of $5000\mathrm{{US}}$ companies, it is easier to think of the index level of 978.80 as being the price of $\$978.80$ for a basket of 500 stocks, where for each company we have some fraction of an actual share. Suppose on Thursday, June 24, 2010, we want to lock in the amount. we would have to pay for 2,500 such baskets for delivery in March 2011. We buy 10 March futures contracts at 974.20. Table 3.13 shows the variation margin calculations assuming that. the futures price drops to 965.50.  

On March 18, 2011 we buy 2,500 baskets at $\$965.50$ each paying $\$2,413,750$ for all the. stocks. Including the mark-to-market loss of $\$21,750$ on the futures, the total is $\$2,435,500$ or $\$974.20$ per basket.  

In addition to broad market indexes, Chicago exchanges trade futures on narrow indexes and ETFs. The electronic OneChicago exchange also offers futures contracts on 1,200 individual US stocks, each representing 100 shares of a stock.  

# 3.2.4 Currency Futures and Forwards  

Currency futures trade on several derivative exchanges in the USA, Europe, and Asia. The unique feature of currency trading is, however, that the market is dominated by OTC forwards, rather than standardized futures, and that a significant share of the volume of transactions (about $30\%$ in contrast to less than $5\%$ in other markets) is linked directly to the end-user demand from non-financial corporations managing their day-to-day FX exposure. Outright forwards represent only $7\%$ of the total volume; forwards are packaged with spots or forwards for other dates to form short-term currency swaps, the main instruments traded.  

Table 3.13 MTM calculation for 10 contracts bought at 974.20   


<html><body><table><tr><td>Date</td><td>Settleprice</td><td>Daily calculation</td><td>MTM (VM)</td><td>Net var. margin</td></tr><tr><td>Fri,Jun252010</td><td>978.60</td><td>10 × (978.60-974.40)× $250</td><td>+$10,500</td><td>+$10,500</td></tr><tr><td>Mon,Jun282010</td><td>953.70</td><td>10× (953.70-978.60)× $250</td><td>$62,250</td><td>$51,750</td></tr><tr><td>Fri,Mar182011</td><td>965.50</td><td>10x(965.50-...)× $250</td><td></td><td>$21,750</td></tr></table></body></html>  

Table 3.14 FX Forwards EUR/USD on August 7, 2003   


<html><body><table><tr><td>Type</td><td>Expiry</td><td>Points</td><td>Bid</td><td>Ask</td><td>Time</td></tr><tr><td>Spot</td><td></td><td></td><td>1.1374</td><td>1.1381</td><td>19:31:00</td></tr><tr><td>ON</td><td>Aug082003</td><td>-0.36/-0.33</td><td>1.1374</td><td>1.1381</td><td>15:49:00</td></tr><tr><td>TN</td><td>Aug11 2003</td><td>-1.06 / -1</td><td>1.1373</td><td>1.1380</td><td>18:42:00</td></tr><tr><td>SN</td><td>Aug122003</td><td>-0.34 / -0.31</td><td>1.1374</td><td>1.1381</td><td>04:43:00</td></tr><tr><td>SW</td><td>Aug18 2003</td><td>-2.3/-2.21</td><td>1.1372</td><td>1.1379</td><td>19:31:00</td></tr><tr><td>2W</td><td>Aug252003</td><td>4.63 /-4.48</td><td>1.1369</td><td>1.1377</td><td>19:03:00</td></tr><tr><td>1M</td><td>Sep11 2003</td><td>-12.5 /-7.5</td><td>1.1361</td><td>1.1374</td><td>13:41:00</td></tr><tr><td>2M</td><td>Oct14 2003</td><td>-23.2/-18.2</td><td>1.1351</td><td>1.1363</td><td>15:08:00</td></tr><tr><td>3M</td><td>Nov12 2003</td><td>-32.3/-27.3</td><td>1.1342</td><td>1.1354</td><td>18:19:00</td></tr><tr><td>4M</td><td>Dec11 2003</td><td>41.4 / -36.4</td><td>1.1333</td><td>1.1345</td><td>19:31:00</td></tr><tr><td>5M</td><td>Jan122004</td><td>-50.5 /-45.5</td><td>1.1323</td><td>1.1336</td><td>19:12:00</td></tr><tr><td>6M</td><td>Feb11 2004</td><td>-58.9/-53.9</td><td>1.1315</td><td>1.1327</td><td>19:29:00</td></tr><tr><td>9M</td><td>May11 2004</td><td>-82.27/-77.27</td><td>1.1292</td><td>1.1304</td><td>19:32:00</td></tr><tr><td>1Y</td><td>Aug11 2004</td><td>-103.22/-98.22</td><td>1.1271</td><td>1.1283</td><td>19:32:00</td></tr><tr><td>2Y</td><td>Aug11 2005</td><td>-151 /-136</td><td>1.1223</td><td>1.1245</td><td>19:30:00</td></tr><tr><td>3Y</td><td>Aug11 2006</td><td>-130/-96</td><td>1.1244</td><td>1.1285</td><td>19:27:00</td></tr><tr><td>4Y</td><td>Aug11 2007</td><td>-53 / -7</td><td>1.1321</td><td>1.1374</td><td>19:00:00</td></tr><tr><td>5Y</td><td>Aug11 2008</td><td>53/111</td><td>1.1427</td><td>1.1492</td><td>19:12:00</td></tr></table></body></html>  

# FX Forwards  

Spot and forward FX rates are quoted continuously in the interbank market and are reported on Bloomberg or Reuters. Normally, only forwards for standard maturities of 1, 3, 6, and 12 months are displayed, but forwards for customized expiry dates, as long as 10 years, can be. easily arranged on most major currencies. Transaction sizes are large with $\$10$ million being a minimum lot. Table 3.14 shows quotes for the USD/EUR market found on a website of a major European bank on August 7, 2003. By convention, and despite the heading, the rate is. quoted in dollars per euro.  

Valid quotes go out 2 years (3-, 4-, and 5-year quotes were not updated that day) and all forwards are related to the spot quotes of USD/EUR 1.1374/81 (bid/ask) through forward points. These are decimals to be added to the significant digits of the spot rate. For USD/EUR, there are four significant digits after the decimal. For example, to arrive at the 9-month forward bid, we have to take the forward points of $-82.27$ (which are shorthand for $-0.008227.$ ) and add that to the spot bid of 1.1374 to get 1.1292. Dealers shout only the forward points to each other over the phone. Just like spot, the USD/EUR forwards are quoted in American terms,. with USD being the pricing currency of the commodity EUR. In this example, the EUR can be said to be trading at a forward discount as forward prices of EUR in dollars are lower than spot prices (all points are negative). Alternatively, the UsD is trading at a forward premium. The forward premium/discount is defined as the difference between forward and spot in percentage of spot. For example, the 6-month forward discount for the euro using ask prices is equal to:  

$$
(1.1327-1.1381)/1.1381=-0.4745\%
$$  

Note that the 6-month forward premium for the dollar (in euros) is not the same:  

$$
(1/1.1327-1/1.1381)/(1/1.1381)=+0.4767\%
$$  

Table 3.15 FX futures quotes for July 21, 2003   


<html><body><table><tr><td></td><td>Open</td><td>High</td><td>Low</td><td>Settle</td><td>Change</td><td>Lifetime high</td><td>Lifetime low</td><td>Open interest</td></tr><tr><td colspan="9">Japanese yen (CME) - ￥12,500,000; $ per ￥100</td></tr><tr><td>Sep</td><td>0.8437</td><td>0.8471</td><td>0.8432</td><td>0.8448</td><td>-0.0010</td><td>0.8815</td><td>0.8220</td><td>81,966</td></tr><tr><td>Dec</td><td>0.8478</td><td>0.8486</td><td>0.8465</td><td>0.8471</td><td>-0.0010</td><td>0.8915</td><td>0.8350</td><td>20,435</td></tr><tr><td colspan="9">Est vol8,659;vol Fri 19,005;open int 102,436,-4,422</td></tr><tr><td colspan="9">Euro/US dollar (CME) - 125,000; $ per </td></tr><tr><td>Sep</td><td>1.1239</td><td>1.1338</td><td>1.1226</td><td>1.1326</td><td>0.0057</td><td>1.1896</td><td>0.8780</td><td>92,581</td></tr><tr><td>Dec</td><td>1.1265</td><td>1.1310</td><td>1.1213</td><td>1.1299</td><td>0.0057</td><td>1.1860</td><td>0.9551</td><td>1,550</td></tr><tr><td>Mar2004</td><td>1.1218</td><td>1.1270</td><td>1.1218</td><td>1.1275</td><td>0.0057</td><td>1.1795</td><td>1.0425</td><td>253</td></tr><tr><td colspan="9">Est vol 33,046; vol Fri 41,304; 0pen int 94,456,-2,557</td></tr></table></body></html>  

What is special for currencies is that assets underlying the forward contracts are also currencies. Quotes (but not points and the premiums/discounts) can be inverted easily to suit the viewpoint of the customer. This dual nature of FX rates also has implications for the cost-of-carry link between spot and forward FX.  

# FX Futures  

Standardized currency futures trade on major exchanges. The CME lists G10 currencies against the dollar, several natural G10 crosses such as AUD/NZD or EUR/GBP, and several emerging market currencies against the dollar or natural crosses such as HUF/EUR. The LIFFE trades USD/EUR futures in limited volume. Except for the crosses, the CME contracts are defined. in foreign currencies per dollar, irrespective of the spot quoting convention. Contract sizes are. large by retail standards (e.g. 125,000), including the few half-size "mini" versions (62,500), but are relatively small by wholesale market standards. Table 3.15 shows the settlement values of CME futures for the previous business day reported in a financial newspaper on July 22,. 2003.  

The mechanics of daily settlement for currency futures are identical to those for commodities with the priced currency in the denominator treated as the underlying commodity. Suppose on. July 21 we entered into five long December USD/JPY contracts right at the close at 0.8471. Note that for JPY, the 0.8471 price is in dollars per 100 yen, or it is shorthand for 0.008471 in USD/JPY, which is equivalent to JPY/USD 118.05 (1/0.008471). Suppose by the next day the JPY/USD settlement rate changes to 119.25, or equivalently to USD/JPY 0.008386 or UsD/100JPY 0.8386. We have a negative cash flow in the form of a variation margin. settlement of:  

$$
5\times12{,}500,0000{(}0.8386-0.8471{)}/100=\S-5{,}328.48
$$  

The multiplier for the price as stated in the contract is thus 125,000 per yen. Note that for the USD/EUR contract, the multiplier is simply equal to the size of the contract, which is 125,000 as the price is stated in dollars per 1 euro. Since the USD/EUR rate is quoted to 4 decimal places, the multiplier can also be stated as $\$12.5$ per pip, with 1 pip equal to $\mathsf{\varepsilon}{\0.0001}$ . It can be shown in a manner analogous to the commodity arguments that going long five December JPY contracts allows us to lock in an exchange rate of 118.05 on JPY 62,500,000 for the delivery on December 19, 2003. The net variation margin accumulated by that expiry date will offset any difference between the spot FX rate on that date and the original rate of 118.05 on the purchase of JPY 62,500,000.  
