---
tags:
  - cash_and_carry
  - dollar_rolls
  - repo_rate
  - tba_liquidity
  - tba_prices
aliases:
  - Dollar Rolls
  - TBA rolls
key_concepts:
  - Cash-and-carry arbitrage
  - Forward contracts
  - Implied financing rate
  - Repo position
  - TBA contracts
---

# 15.10 DOLLAR ROLLS  

Because TBA liquidity is concentrated in contracts that mature in one of the next several months, market participants often need to roll their positions in maturing contracts to contracts that mature at later dates. For example, orig-. inators and investors that are short January 2022 TBAs to hedge exposures. but wish to keep those short positions past the January settlement date, can. buy the roll, that is, buy (back) the front month contract (January) and sell contracts expiring in later months, perhaps in February. Similarly, servicers and investors who are long January 2022 TBAs, but wish to maintain those longs past January, can sell the roll, that is, sell (out of) the front month contract (January) and buy contracts expiring in later months. These TBA rolls are also called dollar rolls..  

A natural question that arises in the context of dollar rolls is whether TBA prices are fair relative to one another. Because TBAs are forward contracts, several of the insights of Chapters 10 and 11 apply here. First, a. long TBA position is similar to a long position in the underlying pool and. a short repo position (i.e., borrowing money on the collateral of the pool). Second, TBA prices will exhibit forward drops so long as the carry on the pool exceeds the repo rate. This is illustrated, in fact, in Table 15.6. The repo.  

rate at the time is 10 basis points; all the TBA coupons shown significantly exceed that repo rate; and TBA prices are lower for later expiration months..   
Third, just as each TBA has implicit financing from the trade date to settle-.   
ment, a TBA roll embeds implicit financing from the expiration of the front.   
contract to the expiration of the deferred contract..  

Market practitioners calculate the value of a roll and the implied financing rate or breakeven financing rate of a roll along the lines of the. cash-and-carry arbitrage for forward contracts on coupon bonds discussed in Chapter 11. In that context, however, the forward contract is on a. particular bond and that bond's coupon is known with certainty. In the TBA context, because of the delivery option, the forward contract is on an unknown pool. Furthermore, because of prepayments, the cash flows of pools are not known with certainty. An industry standard roll analysis puts. these issues aside, essentially assuming that rolls are perfectly equivalent. to mortgage repo. After presenting this analysis, the text returns to the differences between TBA and repo financing.  

Consider an investor who holds. $\$1,000,000$ of a 30-year $2.5\%$ pool in early January 2022. Assume that TBA prices are as in Table 15.6 and that the mortgage repo rate of 10 basis points is the relevant risk-free rate. Also, consistent with the discussion in the previous paragraph, assume for the purposes of this analysis that the February cash flow from the pool (payable to investors on February 25) is known and equal to $\$10,850.00$ , which includes $\$8,800.00$ of principal (both scheduled payments and prepayments).  

The investor holding the pool is considering two strategies, both of. which leave the investor with the same outstanding balance of the pool on 2/14: i) hold the pool to February 14, the settlement date of the February. TBA, at which point the principal outstanding balance is $\$1,000,000$ minus $\$8,800.00$ , or $\$991,200$ ; ii) sell the pool through the January TBA for. 101-28 (101.875) and buy back $\$991,200$ of the pool through the February. TBA at 101-20 (101.625). The assumption that the investor will get back. the same pool that had been sold in January is again consistent with the simplifications of this analysis. Figure 15.7 summarizes these two strategies: holding the pool, below the line, and ii) rolling, above the line..  

The cash flows from holding the pool are very simple. The February payment of $\$10,850.00$ is received on 2/25, but, for comparison purposes,. is discounted 11 days, back to 2/14, for a present value of. $\$10,850.00/(1+$ $11\times0.10\%/360)=\S10,849.67$  

The cash flows from rolling are as follows. The pool is sold through the January TBA for flat proceeds of $\$1,000,0000\times101.875=\$1,018,750.00$ plus 12 days of accrued interest, that is, $\$1,000,000$ 833.33, for total proceeds of $\$1,019,583,33$ . These proceeds are invested at the repo rate from 1/13 to 2/14, that is, for 32 days, to earn interest of $\$1,019$ $583.33\times{0.10\%}\times32/360=590.63$ . The next part of this strategy. is to buy $\$991,200.00$ face amount of the pool through the February TBA at a flat cost of. $\$9991,200.00$ 00, plus accrued interest of 13 days of $\$9991,200.000\times2.50\%\times13/360=\S894.83$ , for a total cost of $\$1,008,201.83$ . Finally, subtracting this cost from the invested proceeds of the January sale leaves a net of $\$11,472.13$  

![](91ebea2122375d029660f0e767c9e81120b4494330f09eee2caecbc3c903d7a1.jpg)  
FIGURE 15.7  Dollar Roll Example, UMBS 30-Year $2.5\%$ Jan-Feb TBAs, as of January 2022.  

Putting the pieces together, both the hold and roll strategies leave the. investor with $\$991,200$ of the pools as of 2/14. But the roll strategy also. leaves the investor with net proceeds of. $\$11,472.13$ on 2/14, while the hold strategy leaves the investor with $\$10,849,67$ . The value of the roll, defined as the difference between these two amounts, is. $\$623.46$ . Hence, according to this analysis, the January TBA is rich relative to the February TBA, or, in other words, investors are willing to pay up to have the. $2.5\%$ pools now.  

The advantage of the roll is often expressed as an implied or breakeven financing rate, which, replacing the repo rate, sets the value of the roll to zero. In this example, the implied financing rate is. $-58.4$ basis points. The difference between the actual repo rate of 10 basis points and this implied rate, or about 68 basis points, is known as the specialness of the pools. From a rates perspective, owners of the. $2.5\%$ pools can earn 68 basis points over repo by giving up their pools for a month..  

While the numbers in this example are rounded for easy reading, the implied financing rate of. $-58$ basis points is consistent with the analysis. circulated by market professionals at the time. The discussion circles back then, to the simplifying assumptions behind the standard dollar roll analysis. First, the assumption that the same pool will be returned to the owner in February overstates the desirability of the roll to the owner of the pool: the TBA delivery option opens the roll seller to the risk of receiving a pool of lower value. Second, the prepayment assumption is critical in the calculation of the breakeven rate. Slower prepayments make holding the pool more valuable, or equivalently, reduce the value of the roll and increase the implied financing rate. Third, the assumption of known prepayments overstates the desirability of holding the pool, or equivalently, understates the value of the roll, because prepayments are, in fact, uncertain, and prepayment risk is borne by the holder of the pool..  

In summary, financing in the mortgage market is available directly,. through repo, and indirectly, through TBAs. The liquidity of the TBA market is a factor in its favor. Repo financing keeps the prepayment risk. of intermediate payments with the owner of the collateral, while TBA. positions avoid that risk. Repo financing keeps control of the collateral; long TBA positions give up control of collateral; and short TBA positions are long a delivery option..  
