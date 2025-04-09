# 5.5 REPO MARKET STRATEGIES  

The previous sections dealt with repo mechanics and terminology. In this section, we start using repo instruments to devise financial engineering strategies..  

# 5.5.1 FUNDING A BOND POSITION  

The most classic use of repo is in funding fixed-income portfolios. A dealer thinks that it is the right. time to buy a bond. But, as is the case for market professionals, the dealer does not have cash in hand, but he can use the repo market. A bond is bought and repoed out at the same time to secure the. funds needed to pay for it. The dealer earns the bond return; his cost will be the repo rate..  

The same procedure may be used to fund a fixed-income portfolio and to benefit from any opportunities in the market, as the following reading shows..  

# EXAMPLE  

Foreign fund managers have recently been putting on bond versus swap spread plays in the Singapore. dollar-denominated market to take advantage of an expected widening in the spread between the term repo rate and swap spreads. "It's one of the oldest trades in the book," said [a trader] noting that it has only. recently become feasible in the local market....  

In a typical trade, an investor buys 10-year fixed-rate Singapore government bonds yielding. $3.58\%$ and then raises cash on these bonds via the repo market and pays an annualized funding rate of. $2.05\%$ .. At the same time the investor enters a 10-year interest-rate swap in which it pays. $3.7I5\%$ fixed and receives the floating swap offer rate, currently. $2.3I\%$ While the investor is paying out 13.5 basis points on the difference between the bond yield it receives and the fixed rate it pays in the swap, the position makes 26 bp on the. spread between the floating rate the investor receives in the swap and the term repo funding rate. The. absolute levels of the repo and swap offer rate may change, but the spread between them is most likely to widen, increasing the profitability of the transaction..  

One of the most significant factors that has driven liquidity in the repo is that in the last few months the Monetary Authority of Singapore has started using the repo market for monetary authority intervention, rather than the foreign exchange market which it had traditionally used..  

(Based on an article in Derivatives Week).  

We will analyze this episode in detail using the financial engineering tools developed in earlier chapters. For simplicity, we assume that the underlying are par bonds and that the swap has a 3-year maturity with the numerical values given in the example above.' The bond position of the trader is shown in Figure 5.6a. A price of 100 is paid at. $t_{0}$ to receive the coupons, denoted by $C_{t_{0}}$ and the principal. Figure 5.6b shows the swap position. The swap "hedges" the fixed coupon payments and "converts' the fixed coupon receipts from the bond into floating interest receipts. The equivalent of LIBOR in Singapore is SIBOR. After the swap, the trader receives SIBOR-13.5 bp. This is shown in Figure 5.6c which adds the first two cash flows vertically. At this point, we see another characteristic of the position. The trader receives the floating payments, but still has to make the initial payment of 100. This means the trader has to get these funds from somewhere.  

One possibility is to borrow them from the market. A better way to obtain them is the repo. By lending the bond as collateral, the player can get the needed funds, 100-assuming zero haircut. This situation is shown in Figure 5.7. We consider, artificially, a 1-year repo contract and assume that the repo can be rolled over at unknown repo rates $R_{t_{1}}$ and $R_{t_{2}}$ in future periods. According to the reading, the current repo rate is known:  

$$
R_{t_{0}}=2.05\%
$$  

![](images/5d1da774dfd380216c5c2551c244165fcba0c323851c6c2b05e482bed6c3bc37.jpg)  

# FIGURE 5.6  

Bond and swap cash flows.  

Adding the first two positions in Figure 5.7 vertically, we obtain the final exposure of the market participant.  

The market participant has a 12.5 bp net gain for 1 year. But, more important, the final position has the following characteristic: the market participant is long a forward floating rate bond, which pays the floating SIBOR rates $S_{t_{1}}$ and $S_{t_{2}}$ , minus the spread, with the following expectation:  

$$
\begin{array}{r}{S_{t_{1}}>R_{t_{1}}+13.5\mathrm{{bp}}}\ {S_{t_{2}}>R_{t_{2}}+13.5\mathrm{{bp}}}\end{array}
$$  

That is to say, if the spread between future repo rates and SIBOR tightens below $13.5\mathrm{bp}$ , the position will be losing money. This is one of the risks implied by the overall position. The lower part  

![](images/b04ee9a1caad4e2192e1682090e7e095e5b69cbf2833af6e86a4ffe9bfe31be1.jpg)  

# FIGURE 5.7  

Bond, swap, and repo cash flows.  

of Figure 5.7 shows how this exposure can be hedged. To hedge the position, we would need to go short the same bond forward.  

# 5.5.1.1 A subtle risk  

There is another, more subtle risk in this "classical"' position. The investor is short the bond and is paying a fixed swap rate. It is true that if the rates move in a similar way, the par bond and the par. swap gains or losses would cancel each other..  

Yet, the swap spread, $S_{t_{0}}-C_{t_{0}}$ can also change. For example, suppose $S_{t}$ remains the same but $C_{t}$ increases significantly, implying a lower swap spread. Then, the value of the swap would remain the same, but the value of the bond would decline. Overall, the bond plus swap position would lose money.  

More important, the repo dealer would ask for more collateral since the original collateral is now less than the funds lent..  

# 5.5.1.2 The asset swap  

There is another way we can describe this position. The investor is buying the bond using repo and asset swapping it. This terminology is more current..  

# 5.5.1.3 Risks and pricing aspects  

The position studied in the previous section is quite common in financial markets. Practitioners call. these arbitrage plays or just arb. But it is clear from the cash flow diagrams that this is not the arbitrage that an academic would refer to. In the preceding example, there was no initial invest-. ment. The immediate net gain was positive, but the practitioner had an open position which was. risky. The position was paying net 12.5 bp today, however, the trader was taking the risk that the future spreads between repo rates and SIBOR could tighten below 13.5 basis points. It is true that a 6-month SIBOR has a longer tenor than, say, a 1-month repo rate and, assuming a positively sloped. yield curve, the spread will be positive; but this cannot be guaranteed..  

Second, the player is assuming different credit risks. He or she is paying a low $2.05\%$ on the repo financing because it is backed by Singapore government bonds. On the other hand, the $2.31\%$ received from the SIBOR side is on a loan made to a high-quality private sector credit. Thus, the question remains: Is the net return of 12.5 bp worth the risks taken?  

# 5.5.1.4 An arbitrage approach  

There is a way to evaluate the appropriateness of the 12.5 bp return mentioned in the example. In fact, the market practitioner's final position is equivalent to owning a basis swap between the repo rate and the floating swap reference rate (assuming swap spreads do not change). After all, the position taker is receiving the floating rate in the swap and paying the repo rate.  

Suppose the repo and swap have identical settlement dates $t_{i}$ . The final position is one where, at. each settlement date, the position taker will receive.  

$$
(L_{t_{i-1}}+12.5\mathrm{bp}-R_{t_{i-1}})\delta N
$$  

Clearly, this is similar to the settlement of a basis swap with a 12.5 bp spread and notional amount $N$ . If such basis swaps traded actively in the Singapore market, one could evaluate the strategy by comparing the net return of 12.5 bp with the basis swap spread observed in the market. If they are equal, then the same position can be taken directly in the basis swap market. Otherwise, if the basis swap rate is different than 12.5 bp, then a true arbitrage position may be put in place by buying the cheaper one and simultaneously selling the more expensive position.  

# 5.5.2 FUTURES ARBITRAGE  

Repo plays a special role in bond and T-bill futures markets. Consider a futures position with expiration $t_{0}+30$ days. In 30 days, we will take possession of a default-free zero coupon bond with maturity $T$ at the predetermined futures price $P_{t_{0}}$ . Hence, at settlement, $P_{t_{0}}$ dollars will be paid and the 1-year bond will be received. Of course, at $t_{0}+30$ the market value of the bond will be given by $B(t_{0}+30,~T)$ and will, in general, be different than the contracted $P_{t_{0}}$ . The repo market can be used to hedge this position. This leads us to the important notion of implied repo rate.  

How can we use repo to hedge a short bond futures position? We dealt with this idea earlier in the discussion of cash-and-carry trades: secure funding, and buy a. $T+30$ day maturity bond at $t_{0}$ When time $t_{0}+30$ arrives, the maturity left on this bond will be. $T.$ and thus the cash and carry will. result in the same position as the futures. The practitioner borrows USD at. $t_{0}$ buys the $B(t_{0},$ $T+30)$ bond, and keeps this bond until time. $t_{0}+30$  

The novelty here is that we can collapse the two steps into one by buying the bond, and then immediately repoing it to secure financing. The result should be a futures position with an equivalent price.  

This means that the following equation must be satisfied:  

$$
P_{t_{0}}=B(t_{0},T+30)\bigg(1+R_{t_{0}}\frac{30}{360}\bigg)
$$  

In other words, once the carry cost of buying the $T+30$ -day maturity bond is included, the total amount paid should equal $P_{t_{0}}$ , the futures price of the bond.  

Given the market quotes on the $P_{t_{0}},B(t_{0},T+30)$ , market practitioners solve for the unknown $R_{t_{0}}$ and call this the implied repo rate:  

$$
R_{t_{0}}=\left[\frac{P_{t_{0}}}{B(t_{0},T+30)}-1\right]\frac{360}{30}
$$  

The implied repo rate is a pure arbitrage concept and shows the carry cost for fixed-income dealers.  

# 5.5.3 HEDGING A SWAP  

Repo can also be used to hedge swap positions. Suppose a dealer transacts a 100 million 2-year swap with a client. The dealer will pay the fixed 2-year treasury plus $30\mathrm{bp}$ , which brings the bid swap rate to, say, $5.95\%$ . As usual, LIBOR will be received. The dealer hedges the position by buying a 2-year treasury.  

In doing this, the dealer expects to transact another 2-year swap "soon' with another client, and receives the fixed rate. Given that the asking rate is higher than the bid swap rate, the dealer will cap-. ture the bid-ask spread. Suppose the ask side swap spread is 33 bp. Where does the repo market. come in? The dealer has hedged the swap with a 2-year treasury, but how is this treasury funded? The answer is the repo market. The dealer buys the treasury and then immediately repos it out over-. night. The repo rate is $5.61\%$ . The dealer expects to find a matching order in a few days. During this. time, the trader has exposure to (i) changes in the swap spread and (ii) changes in the repo rate.  

# 5.5.4 TAX STRATEGIES  

Consider the following situation:  

Domestic bond holders pay a withholding tax, while foreign owners don't. Foreign investors receive the gross coupons.  

The following operation can be used. The domestic bond holder repos out the bond just before. the coupon payment date to a foreign dealer (i.e., a tax-exempt counterparty). Then, the lender receives a manufactured dividend, which is a gross coupon.10  

This is legal in some economies. In others, the bond holder would be taxed on the theoretical coupon he or she would have received if the bond had not been repoed out. Repoing out the bond to avoid taxation is called coupon washing.  

# EXAMPLE  

Demand for Thai bonds for both secondary trading and investment has partly been spurred by the   
emergence of more domestic mutual funds, which have been launching fixed-income funds. However, foreign   
participation in the Thai bond market is limited because of withholding taxes.. "Nobody's figured out an effective way to wash the coupon to avoid paying withholding taxes," said one.   
investment banker in Hong Kong. Coupon washing typically involves an offshore investor selling a bond just   
before the coupon payment date to a domestic counterparty. Offshore entities resident in a country having a   
tax treaty with the country of the bond's origin can also serve to wash coupons.. In return, the entity washing the coupon pays the offshore investor the accrued interest earned for the.   
period before it was sold-less a small margin. Coupon washing for Thai issues is apparently widespread   
but is becoming more difficult. according to some sources..  

(Thomson Reuters IFR, Issue 1129).  

Another example of this important repo application is from Indonesia.  

# EXAMPLE  

A new directive from Indonesia's Ministry of Finance has put a temporary stop to coupon washing activities.   
undertaken by domestic institutions on behalf of offshore players. The new directive, among other things,.   
requires that tax be withheld on the accrued interest investors earn from their bond holdings..  

Before the directive was issued a fortnight ago, taxes were withheld only from institutions that held the bond on coupon payment date. Offshore holders of Indonesian bonds got around paying the withholding tax by having the coupons washed.  

Typically, coupon washing involves an offshore institution selling and buying its bonds-just before and after the coupon payment dates-to tax-exempt institutions in Indonesia. As such, few bond holdersdomestic or offshore-paid withholding taxes on bond holdings. Because the new directive requires that accrued interest on bonds be withheld, many domestic institutions have stopped coupon washing for. international firms.  

(Thomson Reuters IFR, Issue 1168).  

The relevance of repo to taxation issues is much higher than what these readings indicate. The following example shows another use of repo.  

# EXAMPLE  

In Japan there is a transaction tax on buying/selling bonds--the transfer tax. To (cut costs), repo dealers.   
lend and borrow Japanese Government Bonds (JGBs) and mark them to market every day.. The traders don't trade the bond but trade the name registration forms (NRF). NRF are "memos" sent to   
Central Bank asking for ownership change. They are delivered to local custodians. The bond remains in the   
hands of the original owner, which will be the issuer of the NRF.. JGB trading also has a no-fail rule, that is to say failure to deliver carries a very high cost and is.   
considered taboo.  

(Thomson Reuters IFR, Issue 942).  

Many of the standard transactions in finance have their roots in taxation strategies as these examples illustrate.  
