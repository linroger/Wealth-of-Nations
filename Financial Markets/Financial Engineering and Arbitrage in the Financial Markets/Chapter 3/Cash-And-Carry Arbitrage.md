---
tags:
  - arbitrage
  - cash_and_carry
  - cost_of_carry
  - futures_pricing
  - spot_price
aliases:
  - Carry Arbitrage
  - Cash and Carry
key_concepts:
  - Cost-of-carry equation
  - Profit-seeking arbitrageurs
  - Replicating derivative contracts
  - Riskless profit opportunity
  - Spot vs. futures prices
---

# 3.3 CASH-AND-CARRY ARBITRAGE  

The cost-of-carry equation and the cash-and-carry arbitrage that justifies it and are the most. important links that bind the spot price of a commodity to all its forwards and futures prices.. The essence of the cost-of-carry equation lies in the fact that futures and forwards are redundant derivative contracts that can be completely replicated with a spot transaction combined with financing and carrying actions. The purchase of 20,o00 bushels of corn for delivery in 3 months can be replicated with borrowing money for 3 months, buying corn now, and paying for the storage of corn for 3 months. The purchase of 500 component stocks in the S&P 500 index. for delivery in 6 months can be replicated with borrowing money for 6 months, buying the stocks in the right proportions now, and receiving the expected dividends on the stocks over. the next 3 months, which defrays the cost of buying them now. The purchase of euros with dollars for delivery in 1 month can be replicated with borrowing dollars for 1 month, buying euros with the borrowed dollars now, and earning interest on the purchased euros over the next month. In a month, dollars are repaid with interest and euros are received with interest, but the exact amounts, and therefore the exchange ratio, are known or are locked in now, in advance. All the replicating strategies involve borrowing or lending money (financing), buying or selling a commodity now (spot), and paying for storage and/or receiving cash flows (dividends, coupon interest) from the commodity (carry). Therefore, the relationship between. spot $S$ and futures/forwards $F$ can be written approximately as:  

$$
F=S+F i n a n c i n g\pm C a r r y
$$  

Or, if we define financing (paid carry) and received carry as percentages of spot, then we can write it as:  

$$
F=S\times(1+P a i d c a r r y)/(1+R e c e i\nu e d c a r r y)
$$  

This equation naturally has to be corrected for the right fraction of the year or the number of years over which the commodity is carried. The (. $^{1+}$ rate) terms need to be modified to. terms like ( $1+\operatorname{rate}\times$ day-count) or ( $1+$ rate) raised to the power of the number of years. We. will see this equation in various guises as we discuss each commodity.  

It is important to realize that the cost-of-carry equation is not as absolute as a physics equation. Distance is always equal to velocity multiplied by time; force is always equal to mass multiplied by acceleration - at least in our universe. The cost-of-carry equation holds only if there are market participants operating in unrestricted markets that force it to hold. Another way to state this is to ask: What if the cost-of-carry equation did not hold? What if the. forward price of corn for delivery in 3 months was much greater than posited by the equation?. We will argue that free agents motivated by profit seeking could borrow money to buy and store 20,000 bushels of corn and at the same time could sell four futures contracts (each for 5,000 bushels) to guarantee the future sale price on the stored corn, thus locking in a riskless profit equal to the present value of the difference between the actual (too high) futures price and the (lower) theoretical fair value futures price from the cost-of-carry equation. The actions of. profit-seeking arbitrageurs would push the forward price down (excess supply) and spot price up (excess demand), and/or even push borrowing and lending rates, eliminating the riskless profit opportunity they were chasing. The theoretical fair value price is the break-even price at which no riskless profit can be generated from synthetic replication of the forward contract through cash-and-carry and simultaneous opposite transaction in the actual forward/futures. Since executing transactions takes time - although in today's electronic world, not much time -- at any given moment futures and forwards may deviate from their fair values. But the existence of many speculators in the markets ensures that these deviations are speedily eliminated.  

Not all commodities can be subject to cash-and-carry. Financial commodities are the easiest to arbitrage. It is easy to effect spot currency transactions and borrow and lend money in the Eurocurrency markets. Bonds (and stocks) can be easily bought or borrowed in repo markets and short-sold. But even our corn example has a flaw. It is easy to borrow money to buy corn, but what if the forward price of corn in the market fell below the fair value? The reverse cash-and-carry arbitrage would call for buying corn forward at the low forward price and short-selling corn now by borrowing corn and selling it spot. While borrowing stocks held in street name and shorting them is easy, short-selling corn is impossible as the market for borrowing corn is non-existent. In that case, the cost-of-carry equation has to be replaced by an inequality  

$$
F\leq S+F i n a n c i n g\pm C a r r y
$$  

Any deviation of the forward price on the up side will be arbitraged out, but deviations on the down side may not be. In this situation, we cannot argue that greed will instantly push prices to equality. We can only argue that, over time, agents, realizing that corn for future delivery is relatively cheaper while corn for immediate delivery is relatively dearer, will demand less spot and more forward corn. But this adjustment mechanism will be much slower, and may involve the actual producers/users of corn. Users of corn who have already held corn, may be inclined to reduce their holdings while increasing their long positions in forward corn. Or the adjustment mechanism may extend into riskier speculation in spot corn, something altogether different from riskless arbitrage, where users and speculators reduce their spot holdings of corn with an intent to re-acquire it later.  

Commodities in general run a gamut from those subject to strict cash-and-carry (e.g.. financials and gold) through approximate cash carry (e.g. corn and substitutable agriculturals) all the way to strategic non-substitutables, such as oil..  

# 3.3.1 Commodities  

Let us first consider an example of gold cash-and-carry with actual gold bullion. Suppose on December 18, 2009 we face the gold prices, financing, and carry costs in Table 3.16.  

We can buy gold spot in 100-ounce bars for $\$810.00$ per ounce. Storing it for 3 months. costs $\$15$ per bar, or $\$0.15$ per troy ounce. If we were to borrow gold to short it we would pay a borrow fee of $1.0\%$ per annum. We can borrow or lend dollars at. $1.5\%$ per annum.  

Table 3.16 Gold data on December 18, 2009   


<html><body><table><tr><td></td><td></td></tr><tr><td>Spotgoldpertroyoz 3-monthLIBOR</td><td>$810.00</td></tr><tr><td></td><td>1.5%p.a.</td></tr><tr><td>Storage cost per 100 troy oz per quarter</td><td>$15.00</td></tr><tr><td>Borrowfee</td><td>1.0% p.a.</td></tr></table></body></html>  

Table 3.17 March 2010 gold (NYMEX) at 821.50   


<html><body><table><tr><td>Fair value per 0z = (S + storage) × (1 + LIBOR/4)F*=(810.00 + 0.15) × (1 + 0.015/4) = 813.19 Marchfutures</td><td>F=821.50</td></tr><tr><td>Strategy:</td><td>Cashflow:</td></tr><tr><td>BorrowPVof100×821.50=82,150/(1+0.015/4)</td><td>+ $81,843.09</td></tr><tr><td>Buy100ozgold spot</td><td>$81,000.00</td></tr><tr><td>Paystorage</td><td>- $15.00</td></tr><tr><td>SelloneMarchcontract</td><td></td></tr><tr><td>Netcashatspot</td><td>$828.09</td></tr></table></body></html>  

The fair value equation needs to reflect the cash-and-carry arbitrage we will engage. This will be somewhat different, dependent on whether the forward price of gold is higher or lower than the fair value. Table 3.17 shows the situation when the gold futures trade above the cost-of-carry value, computed assuming we are borrowing money to buy gold spot (cash-and-carry).  

We borrow $\$81,843.09$ today for 3 months. Of that, we spend. $\$81,015$ to buy and store. 100 troy oz of gold for 3 months. We also short one gold contract at 821.50 (no cost to enter). Today, we have a net cash inflow of $\$828.09$ , which is our riskless profit. The short futures. position ensures that irrespective of the price of gold by March, with the variation margin settlement (gain or loss) we will have on hand. $\$82,150$ from the sale of gold. The. $\$82,150$ will pay off the principal and interest on our 3-month borrowing of dollars, leaving us with no. exposure on March 19, 2010.  

Table 3.18 shows the situation when the gold futures trade below the cost-of-carry value. computed, assuming shorting gold spot and lending money to buy gold forward (reverse cash-and-carry). Shorting gold is subject to a gold borrow fee of. $1\%$ p.a. paid in arrears.  

We borrow $100~\mathrm{oz}$ of gold and sell it. We collect $\$81,000$ for it. Of that sum, we lend $\$80,371.11$ for 3 months at. $1.5\%$ . The difference $(\$628.89)$ is our riskless arbitrage profit. We also go long one March gold contract. When the $\$80,371.11$ deposit matures on March 19, 2010, we collect the principal and interest of $\$80,472,50$ Of that sum, we use. $\$202.50$ $(=\$81,000$ to pay the fee for borrowing gold, and the remaining $\$80,470$ , together with any variation margin settlement, to buy back 100 oz of gold to return it to the original lender. The net cash flow is zero on March 19, 2010.  

Table 3.18 March 2010 gold (NYMEX) at 804.70   


<html><body><table><tr><td>Fair value per oz=S× (1+LIBOR/4)/(1 + borrow/4) Marchfutures</td><td>）F*=810×(1+0.015/4)/(1+0.01/4)=811.01 F=804.70</td></tr><tr><td>Strategy:</td><td>Cash flow at spot:</td></tr><tr><td>Borrowandshort100ozgoldspot</td><td>+ $81,000.00</td></tr><tr><td>LendPV(80,470+fee202.50)</td><td>$80,371.11</td></tr><tr><td>= (80,470 + 81,000 × 0.01/4)/(1 + 0.015/4) BuyoneMarchcontract</td><td></td></tr><tr><td>Netcash atspot</td><td>$628.89</td></tr><tr><td>On March19,2010:</td><td>Cashflowatfuturesexpiry:</td></tr><tr><td>Collect principal+interest on lending</td><td>+ $80,672.50</td></tr><tr><td>Paygoldborrowfee</td><td>-$202.50</td></tr><tr><td>Take delivery of gold (incl.var.margin)</td><td>-$80,470.00</td></tr><tr><td>Return gold tolender</td><td></td></tr><tr><td>Net cash atfutures expiry</td><td>$0.00</td></tr></table></body></html>  

# 3.3.2 Stock Indexes  

There are several factors to consider in the fair value equation for stocks and stock indexes. Stock purchases need to be financed either explicitly by borrowing money in a margin account, or implicitly by forgoing interest that could have been earned. Holding stocks may earn a positive carry if they pay dividends. Shorting stocks may be subject to negative carry by forcing dividend reimbursement and by requiring a fee for borrowing the stocks. To keep things clear let us first consider an unrealistic case where we assume that none of the stocks in an index pays any dividends over the contract period. We then include dividends in the cost-of-carry. Lastly we consider the full case of the associated cash-and-carry arbitrage for stock index futures, often referred to as index arbitrage, using the data in Table 3.12.  

# Fair Value with No Dividends  

If stocks do not pay dividends, then the only thing to consider in the cost-of-carry equation. is the cost of financing the stock purchase, at least theoretically. Finance textbooks therefore show the following fair value equation:.  

$$
F=S e^{r t}
$$  

where $t$ is the time to maturity in years, e.g. $t={^{1}}/{_2}$ for 6 months, and. $r$ is the continuously compounded interest rate. The expression $e^{r t}$ is the future value factor equivalent to $(1+r)^{n}$ or ( $1+r\times$ day-count) in discrete time. In practice, the financing rate is likely to be LIBOR, and the fair value definition translates into the following intra-year equation:.  

$$
F=S(1+L\times\mathrm{Act}/_{360})
$$  

The right-hand side has two components:. $S$ the spot price, and. $S\times L\times^{\mathrm{Act}}/_{360}$ , the interest cost on borrowing the dollar amount $S$ until expiry. The theoretical equations need to be augmented by one practical feature of stock trading. While $L$ is the only financing cost when. borrowing money to buy stocks, it is not so when shorting stocks. In order to short stocks, they need to be borrowed first, and the borrower will pay the lender a fee. Rather than in dollar terms, that fee can be conveniently expressed as an annualized cost in basis points, similar to an interest rate (but negative). If $b$ is the stock borrow fee on an Act/360 basis, then the corrected fair value equation is:.  

$$
F=S\times(1+L\times\mathrm{^{Act}}/_{360})/(1+b\times\mathrm{^{Act}}/_{360})
$$  

The textbook continuous version of the cost-of-carry is simply  

$$
F=S e^{(r-b)t}
$$  

Note that two other practical factors can be safely omitted from the equation. First, the stock borrow fee is a real cost even if the arbitrageur uses his own to stock to sell; he gives up the revenue that could be earned by lending the stock. Second, even though stocks are shorted in  

margin accounts subject to initial and maintenance requirements, and the cash balances cannot be used immediately, they do earn interest and so no lending interest is lost..  

# Fair Value with Dividends  

The fair value equation for stock index futures must be further amended to reflect the fact that some of the stocks in the index may pay dividends during the contract period. In the synthetic replication of long futures with borrowing and spot purchase, the financing cost of the spot purchase is defrayed by the amount of dividends received between the spot purchase and the futures expiry. In the synthetic replication of short futures with spot stock shorting and lending the balances, the interest earned is reduced by the amount of dividends that need to be reimbursed between the spot and the futures expiry.  

There are two ways of including dividends into the fair value equation depending on how we make future dividend estimates. For shorter expiries, we can typically predict very accurately the dollar amounts and the dates of the dividends. We can present-value them up to today,. subtract them from the spot price, and future-value the net amount in the cost-of-carry equation. Denoting as $D$ the present value of the intervening dividends, we can write the continuous fair. value equation as:  

$$
F=(S-D)e^{(r-b)t}
$$  

and the discrete one as:  

$$
F=(S-D)\times(1+L\times^{\mathrm{Act}}/_{360})/(1+b\times^{\mathrm{Act}}/_{360})
$$  

For longer expiries, we may feel more confident assuming that the dividend rate will be a constant, or at least a predictable, percentage of the stock price. So we can include dividends through a continuously compounded annualized dividend yield. $d$ and subtract it from the. interest charge:  

$$
F=S e^{(r-d-b)t}
$$  

or we can express it in a similar way to the interest rate and the stock borrow fee as a discrete annualized dividend yield $d$ and correct the discrete fair value equation with one more term in the denominator:  

$$
F=S\times(1+L\times^{\mathrm{Act}}/_{360})/(1+b\times^{\mathrm{Act}}/_{360})(1+d\times^{\mathrm{Act}}/_{360})
$$  

There is no inconsistency between this very general expression and its previous version with the subtraction of the PV of dividends. It is simply a matter of preference of how we want to correct the amount of financing for the dividends earned or paid.  

# Stock Index Arbitrage  

The cash-and-carry arbitrage that underlies the fair value equations is carried out through index. program trading (simultaneous and instantaneous trading of all stocks in the index). Consider the data for the S&P 500 futures and LIBOR in Table 3.12 for June 24, 2010. Recall that the spot index stood at 978.80 on that day. Assume a continuous stock borrow fee of 25 bp and a. dividend yield of $1.0\%$ p.a.  

Table 3.19 shows the fair value calculation (using the continuous equation) and the arbitrage for the 3-month contract period from spot on June 24 to futures expiry on September 24, 2010.  

Table 3.19 Index arbitrage with September 2010 at 978.00   


<html><body><table><tr><td>Fair value per contract = F = S e (r-d-b)t September2010futures</td><td>F* = 978.80 e(0.0113-0.0025-0.01)/4 = 978.51 F=978.00</td></tr><tr><td>Strategy:</td><td>Cash flow at spot:</td></tr><tr><td>Borrowandshort250S&P500basketsspot</td><td>+ $244,700.00</td></tr><tr><td>Lend PV of 250 × 978.00 = 250 × 978.00 × e-0.0113/4</td><td>$243,810.26</td></tr><tr><td>Pay dividends+fee 250 × 978.80 × (1-e-(0.01+0.0025)/4)</td><td>-$763.49</td></tr><tr><td>Long one September 10 contract Net cash at spot</td><td>$126.25</td></tr><tr><td>On September 24,2010:</td><td>Cashflow atfuturesexpiry:</td></tr><tr><td>Collect principal + interest on lending = 250× 978.00</td><td>+ $244,500</td></tr><tr><td>Pay for stocks (incl.var.margin)=250× 978.00</td><td>-$244,500</td></tr><tr><td>Returnstockstolender</td><td></td></tr><tr><td>Net cash atfutures expiry</td><td>$0.00</td></tr></table></body></html>  

We assume exactly $^1/_{4}$ year for interest rate, borrow fee and dividend yield in the continuous. equation. All resulting amounts would be identical if we were to use the discrete equation with inputs converted to $1.1070\%$ $0.2446\%$ , and $0.9795\%$ , respectively, on an $\mathrm{Act}/360$ basis with 92 days. The conversion from continuous $c$ to discrete $d$ is $e^{c/4}=1+d\times92/360$ . Also note that the dividend yield of $1.0\%$ continuous or $0.9795\%$ discrete is equivalent to the present value of dividends, equal to $\$2.44$ for a stock basket costing $\$978.80$ . The conversion from continuous yield to discrete dividend PV is $978.80\times(1-e^{-0.01/4})$  

If the September 2010 futures were trading above fair value, e.g. at 980, the strategy would. have been the exact opposite. We would have borrowed dollars (equal to the present value of the futures) to buy stocks spot and we would have shorted futures. The difference between the borrowed dollars plus the present value of the expected dividends (and the borrow fee to be earned), net of the amount needed to purchase stocks, would have been our riskless profit..  

# Fair Value Equation as Arbitrage Cash Flow Equation  

By rearranging the terms in the cost-of-carry equation, the equation becomes the mirror image in exact dollar amounts of the arbitrage strategy described in Table 3.19. All we need to do is to present-value the actual futures price rather than future-value the spot. The continuous version becomes  

$$
F e^{-r t}\neq S e^{-(d+b)t}
$$  

and the discrete version becomes  

$$
F/(1+L\times\mathrm{^{Act}}/_{360})\neq S/(1+b\times\mathrm{^{Act}}/_{360})(1+d\times\mathrm{^{Act}}/_{360})
$$  

The difference between the two sides is the profit. In the reverse cash-and-carry strategy. of Table 3.19, we shorted stocks equal in value to the right-hand side, net of dividends and. borrow fee (we would have to pay), and we lent out the amount equal to the (smaller) left-hand side to be able to buy the stocks back at a prearranged price. As the right-hand side was greater (receipts from shorting) in value than the left-hand side (lending), we still had some money.. In a situation when the left-hand side is greater, we borrow that amount to pay for right-hand (smaller) spot purchases of stocks, net of dividends and fee to be earned..  

# 3.3.3Currencies  

The cash-and-carry argument for currencies is similar to that for stock indexes with the dividend yield replaced by a LIBOR interest rate. Just like index futures, currency forwards are redundant contracts; they can be perfectly synthesized using a spot currency purchase/sale and two interest rate transactions, borrowing in one currency and lending in the other. With. index futures, we borrow dollars (pay interest) to buy stocks, and stocks may earn a dividend. while we wait. With FX forwards, we borrow dollars (pay interest) to buy euros, and we invest euros to earn interest while we wait. We match the maturity dates for borrowing and lending exactly (e.g. 3 months). On the day of maturity, we have an outflow of dollars (to pay off the borrowing) and an inflow of euros (from the investment). Today, we know what those flows are going to be. A strategy that results in a net zero cash flow today, and a known outflow in one currency and a known inflow in another currency on a future day (in 3 months), is a synthetic physical-settle (3-month) currency forward. Extending the argument, since physical. and cash settle forwards are economically equivalent, and forwards and futures are almost economically equivalent (enhanced by credit mitigation and marking-to-market), the synthetic strategy essentially replicates futures and forwards and has the same value at the outset and throughout the life of the contract. This equivalence has been termed in economics as the Covered Interest Rate Parity (CIRP) and is simply another guise of the cost-of-carry equation..  

Economists often talk about another parity, called (Uncovered) Interest Rate Parity, where the forward is replaced by the expected future spot FX rate. While the CIRP is a strict noarbitrage relationship ensured by cash-and-carry arbitrageurs, the "uncovered"' parity is only a macroeconomic theory.  

# Covered Interest Rate Parity  

The CIRP principle states that a currency forward for any expiry must be at a level at which no. riskless profit can be earned through cash-and-carry or reverse cash-and-carry arbitrage. For dollars (USD) and euros (EUR), that translates into the following continuous rate equation:.  

$$
F^{\frac{U S D}{E U R}}=S^{\frac{U S D}{E U R}}e^{(r^{U S D}-r^{E U R})t}
$$  

The FX rates, forward $F$ and spot $S$ , are in dollars per euro, and the exponent contains. the continuous equivalents of LIBOR interest rates, with the euro LIBOR subtracted from the. dollar LIBOR. Comparing this to the stock index fair value equation, we simply replace the. dividend yield with an interest rate and delete the stock borrow fee, reflecting the fact that just as owned stocks earn dividends, idle cash balances of a purchased currency can be deposited to earn interest. In the discrete version of the CIRP, the interest rate terms reflect discrete present-valuing:  

$$
F^{\frac{U S D}{E U R}}=S^{\frac{U S D}{E U R}}\frac{\left(1+r^{U S D}\right)^{t}}{\left(1+r^{E U R}\right)^{t}}
$$  

Both the numerator and denominator have to be further amended to reflect the exact way in which interest is compounded and days are counted.  

Table 3.20 shows an arbitrage strategy to force the CIRP to hold. We observe the spot FX rate for JPY/EUR of 100; 1-year deposit rates are $2\%$ in yen and $4\%$ in euros. A dealer quotes a 1-year forward rate of JPY/EUR 98 good for up to EUR 10,000,000. According to the CIRP, a 1-year forward rate of 98.077 would be arbitrage free. Since the actual forward is lower at  

Table 3.20 CIRP arbitrage: a 1-year forward example   


<html><body><table><tr><td colspan="2">Data: JPY/EUR Spot = 100, 1-Year Forward = 98; Rates JPY 2%,EUR 4%.</td></tr><tr><td>FairValue = S × (1 + r/PY)/(1 + rEUR) F*=100× (1+0.02)/(1+0.04)=98.077 1-year forward</td><td>F=98.00</td></tr><tr><td>On spot date:</td><td>Cash flows:</td></tr><tr><td>BorrowPVof10m=10m/(1+0.04)at4%</td><td>+9,615,384.62</td></tr><tr><td>Spot FX at 100: Sell euros</td><td>- 9,607,843.14</td></tr><tr><td>Buy yen</td><td>+￥ 960,784,313.73</td></tr><tr><td>LendPVof￥980m=￥980m/(1+0.02)at2%</td><td>￥960,784.313.73</td></tr><tr><td>Buy10m at￥/981-yearforward Net cash at spot</td><td>7,541.48 ￥0.00</td></tr><tr><td>On forward date:</td><td>Cash flows:</td></tr><tr><td>Collectmaturing￥ deposit</td><td>+¥980,000,000.00</td></tr><tr><td>Complete forward FX: Sell yen</td><td>￥980,000.000.00</td></tr><tr><td>Buy euros</td><td>+ 10,000,000.00</td></tr><tr><td>Pay off borrowing</td><td>-10,000,000.00</td></tr><tr><td>Netcash atforwarddate</td><td>0.00¥0.00</td></tr></table></body></html>  

98.00, the profit strategy will involve buying euros/selling yen forward. The forward-bought euros will repay a borrowing of euros, and yen deposited today will be used to acquire euros 1 year from today. We match future cash flows in yen and euros, leaving an extra spot inflow in euros as our riskless profit.  

The computations of the amounts start with the forward flows that are then present-valued to establish the amount of borrowing in euros and lending in yen. The spot amount to be exchanged is computed last, based on the amount of yen we need to deposit (assuming we want our riskless profit in euros). Irrespective of the location of the arbitrageur or the desired currency of profit, the direction of the transactions would be the same. The spot and forward FX rates, and perhaps the borrowing and lending rates, would come under pressure to adjust (spot down and forward up) to such levels that the CIRP would hold, and riskless profiting would not be possible.  

Note that in our example, we borrowed in a high interest rate currency and lent in a low interest rate currency. It is the relative levels of all four variables in the fair value equation that matter, not simply the interest rate differential. Another way of stating that is by rearranging the CIRP equation in terms of the forward premium/discount relative to the present value of the interest rate differential:  

$$
\frac{F^{\frac{J P Y}{E U R}}-S^{\frac{J P Y}{E U R}}}{S^{\frac{J P Y}{E U R}}}=\frac{r^{J P Y}-r^{E U R}}{1+r^{E U R}}
$$  

According to this form of the CIRP equation, one cannot profit by borrowing in one currency. and lending in another, because the loss (gain) on the forward cover will be exactly offset by the present value of the interest gain (loss).  

# Covered Interest Rate Parity with LIBOR Rates  

The cash-and-carry arbitrage with currencies is conducted using the deposit markets of Eurocurrencies. For intra-year periods, the CIRP needs to be amended to reflect the day  

count for LIBOR rates. Since both dollars and euros use the Act/360 day-count, the equation looks like this:  

$$
F^{\frac{U S D}{E U R}}=S^{\frac{U S D}{E U R}}{\frac{1+L^{U S D}\times{\frac{\mathrm{Act}}{360}}}{1+L^{E U R}{\frac{\mathrm{Act}}{360}}}}
$$  

Let us apply this equation to the FX rates for August 7, 2003 in Table 3.14. The spot ask. FX rate is USD/EUR 1.1374 bid and USD/EUR 1.1381 ask. The 3-month LIBOR rates on that day were $1.14\%$ for USD and $2.1613\%$ for EUR. Using 97 as the actual number of days. between August 7 and November 12 - the stated expiry of the 3-month FX forward - we obtain the fair forward bid rate:.  

$$
F^{\frac{U S D}{E U R}}=1.1374{\frac{1+0.011400\times{\frac{97}{360}}}{1+0.021613\times{\frac{97}{360}}}}=1.1343
$$  

and the fair ask rate:  

$$
F^{\frac{U S D}{E U R}}=1.1381\frac{1+0.011400\times\frac{97}{360}}{1+0.021613\times\frac{97}{360}}=1.1350
$$  

The actual forward bid/ask quotes of USD/EUR 1.1342/1.1354 contain a wider spread, reflecting a potential mark-up charged by the quoting dealer for unsolicited orders. Such. quotes also ensure that, on August 7, 2003, one could not have picked the quoting dealer off to earn riskless profit.  
