---
cssclasses:
  - academia
linter-yaml-title-alias: Class Slides The LTCM Meltdown Liquidity and “Performance
  Based Arbitraged
title: Class Slides The LTCM Meltdown Liquidity and “Performance Based Arbitrage.”
tags:
  - hedge_fund
  - ltcm_meltdown
  - news_trade
  - pba_arb
  - performance_based_arbitrage
aliases:
  - LTCM
  - Long-Term Arbitrage
  - PBA
key_concepts:
  - Hedge Fund Behavior
  - LTCM Meltdown
  - News Trade
  - PBA Investor Decisions
  - Performance Based Arbitrage
---

[[Class Note 13 The LTCM Meltdown]]

# Class Slides The LTCM Meltdown Liquidity and “Performance Based Arbitrage.”

## II. An Example from Class Note 13
1. **Consider two assets** that will be identical on date 3,  but it is not clear yet that they are identical.
   - On date 3,  asset A will be worth 100 units of asset B.
   - If A is not selling for 100 times the price of B,  there is a long-term arbitrage opportunity.
   - Today is date 1 and the price of asset A is $p_1$ (the date 1 relative price of asset A to asset B,  which will become 100 on date 3).
   - On date 2,  the assets will revert toward the proper price of 100 (possibly all the way) with probability $1 - q$.
   - This revision toward the proper price is referred to as a **“news trade.”**
   - With probability $q$,  the mis-pricing will get worse,  and the price will be $p_2 < p_1 < 100$.

## III. Extreme Performance Based Arbitrage (PBA)
1. Any loss and your investors exit.
1. Suppose that the price at date 1 is $p_1 = 80$,  and that on date 2:
   - With probability $q$,  it will fall to $p_2 = 70$ (due to a noise trade).
   - With probability $1 - q$,  it will rise by 20 to $p_2 = 100$ (due to a news trade).
1. On date 3,  the bet will mature and as a result,  $p_3 = 100$ for sure.
1. To see the effect of PBA,  compare it with a benchmark of the case of someone investing their own money,  which is equivalent to a hedge fund not subject to PBA.

   $$ \begin{array}{c|c}
   \text{Prob} & \text{Price} \\
   \hline
   1 - q & 100 \\
   q & 70 \\
   \end{array} $$

## IV. Decisions by an Investor Not Subject to PBA
1. If the non-PBA investor invests at date 1,  the value at date 3 is:
   $$ \frac{100}{80}D_1 \text{ or in general } \frac{V}{p_1}D_1. $$
1. If instead,  the non-PBA investor waits until date 2 to invest (holding T-bills yielding 0% initially):
   - The price will be 70 or 100 (with probability $q$ and $1 - q$,  respectively).
   - When the price drops to 70,  the non-PBA investor will buy $D_1$ units,  and when the price is 100,  the investor will continue to hold T-bills.
1. The expected date 3 value of waiting until date 2 to take a position is:
   $$ [q \cdot \frac{100}{70} + (1 - q) \cdot 1]D_1 \text{ or in general } [q \cdot \frac{V}{p_2} + (1 - q)]D_1. $$

## V. Investment Decisions Comparison
1. The non-PBA investor will invest at date 1 when it gives a larger expected value of assets:
   $$ \frac{100}{80} \geq q \cdot \frac{100}{70} + (1 - q) $$
   - This leads to:
   $$ q < \frac{7}{12} = 0.58 $$

1. In general:
   $$ \frac{p_1 - V}{p_1 - p_2} \leq \frac{p_2 - V}{p_1 - p_2} $$

## VI. Decisions by a Hedge Fund Subject to PBA
1. If the PBA arb invests $D_1$ at date 1,  their fund is closed with probability $q$ when the price moves away from fundamental value.
   - Investing $D_1$ at date 1 produces expected date 2 assets under management of:
   $$ (1 - q) \cdot \frac{100}{80}D_1 + q \cdot 0. $$
   - The last term,  $q \cdot 0$,  is zero because,  if they lose money,  they are out of business.

1. If the PBA arb waits until date 2 to invest:
   - They won't lose assets under management,  but with probability $1 - q$,  the profit opportunity goes away.
   - The expected value of date 3 assets under management if they wait to invest at date 2 is:
   $$ q \cdot \frac{100}{70}D_1 + (1 - q)D_1. $$

## VII. PBA Arb Investment Condition
1. The PBA arb invests at date 1 when:
   $$ (1 - q) \cdot \frac{100}{80} \geq q \cdot \frac{100}{70} + (1 - q) $$
   - This leads to:
   $$ q < \frac{7}{47} = 0.15 $$

1. In general:
   $$ \frac{p_1 - V}{p_1 - p_2} < \frac{p_2 - V + p_1}{p_1 - p_2} $$

1. Thus,  arbs subject to PBA are averse to profitable long-term bets that might go against them.

## VIII. Table 1: Current and Future Prices (Example)
$$
\begin{array}{|c|c|c|}
\hline
\text{Date} & \text{Price} & \text{If Noise Trade Occurs at Date 2 (Probability = q)} \\
\hline
1 & 80 &  \\
2 & 70 & 100 \\
3 & 100 & 100 \\
\hline
\end{array}
$$

## IX. Market Behavior on Date 2
1. On date 2,  any arbs that see the opportunity will invest in it,  so long as $p_2 < 100$.
   - The arbs who see the date 2 opportunity have limited access to capital.
   - This prevents them from pushing the price all the way to 100,  despite being a pure arbitrage.

1. **Price Example**:
   - We will assume that $q = 0.25$ for some examples,  and for other examples we assume $q = 0.5$.
   - For both values,  no arb subject to PBA will trade at date 1 ($q > 0.15$),  but non-PBA arbs will trade at date 1 ($q < 0.58$).

## X. [[Class Note 13 The LTCM Meltdown|LTCM]] as a Long-Term Arb
1. Suppose that your fund had a very good reputation,  allowing you to avoid PBA.
   - You would have a relatively easy life (assuming you have the skill to see opportunities).
   - Long-term opportunities would be passed over by short-term PBA funds.

1. At date 1,  there are PBA funds and your long-term fund.
   - The PBA funds wait until date 2 to get in,  holding treasuries from dates 1 to 2.

## XI. Expected Returns of PBA Fund
1. The two-period expected return of a PBA fund is:
   $$ q \cdot \frac{100}{70} + (1 - q) \cdot 1 = q \cdot \left(1 + \frac{3}{7}\right) + (1 - q) \cdot 1 = q \cdot \frac{3}{7} + 1. $$

1. For $q = 0.25$:
   $$ = 0.25 \cdot \frac{3}{7} + 1 = 1.0525. $$

1. The two-period return of the long-term fund (assuming that it raises no new capital at date 2) is:
   $$ \frac{100}{80} = 1.25. $$

1. The ability to lock in funds for the long term allows the fund to take different bets in markets with less competition.

## XII. The Problem of Margin Calls
1. The problem arose when [[Class Note 13 The LTCM Meltdown|LTCM]] lost so much money that they faced margin calls.
   - For a large enough loss,  even [[Class Note 13 The LTCM Meltdown|LTCM]] had the equivalent of PBA,  leading to forced sales at the bottom.
   - [[Class Note 13 The LTCM Meltdown|LTCM]] faced a bank-run-style collective action problem.

1. If [[Class Note 13 The LTCM Meltdown|LTCM]] cannot attract enough capital to meet margin calls,  they would be forced to liquidate at the bottom.
   - Anticipating this,  they would be unable to raise smaller amounts of capital.

## XIII. Large Price Drop and Forced Liquidation
1. A large unanticipated price drop would result in a meltdown (forced liquidation).
1. A meltdown causes an even larger price drop when arbs ([[Class Note 13 The LTCM Meltdown|LTCM]] in particular) liquidate.
1. Normally,  the trades of arbs stabilize the market,  offsetting the trades of noise traders.

## XIV. Price Formation and Trade Impact
1. Prices in table 1 are those that prevail AFTER the arbs have put on their trades.
   - If no trades occur,  the price remains unchanged.
   - If only noise trading occurs,  prices fluctuate based on trader behavior.

1. If there is also trade by arbs,  the price changes by the net amount of trade:
   $$ P_t = P_{t-1} + \text{(Noise trade + arb trades)} $$

## XV. [[Class Note 13 The LTCM Meltdown|LTCM]]'s Established Position
1. Assume [[Class Note 13 The LTCM Meltdown|LTCM]] already established a position in the trade before date 1 and is long 20 units.
   - If [[Class Note 13 The LTCM Meltdown|LTCM]] were not long 20 units,  the price would be lower by 20.
   - Arbs subject to PBA would not trade before date 2.

1. **Table 2: Trades by Arbs and Noise Traders**:

   $$ 
   \begin{array}{|c|c|c|c|c|c|c|c|}
   \hline
   \text{Date} & \text{Price} & \text{Noise trade occurs at 1,     } & \text{LTCM Trade} & \text{LTCM Position} & \text{Other Arb Trade} & \text{Other Arb Position} & \text{Total Order Imbalance} \\
   \hline
   0 & 80 &  & 20 &  &  &  &  \\
   1 & 80 & -5 & +5 & 25 & 0 & 0 & 0 \\
   2 & 70 & -25 & +5 & 30 & +10 & 10 & -10 \\
   &  &  &  &  &  &  & +20 \\
   3 & 100 &  &  &  &  &  &  \\
   \hline
   \end{array} 
   $$

## XVI. Panic Selling After the Russian Default
1. Suppose the Russian default causes panic selling at date 1 by noise traders,  when [[Class Note 13 The LTCM Meltdown|LTCM]] already has a position of 20.
   - The noise trade at 1 is now -30.
   - If [[Class Note 13 The LTCM Meltdown|LTCM]] must liquidate immediately at date 1,  look at the meltdown in table 3:

   $$ 
   \begin{array}{|c|c|c|c|c|c|c|c|c|}
   \hline
   \text{Date} & \text{Price} & \text{Noise trade occurs at 1,     } & \text{LTCM Trade} & \text{LTCM Position} & \text{Other Arb Trade} & \text{Other Arb Position} & \text{Total Order Imbalance} & \text{News trade (Prob 1-q)} \\
   \hline
   0 & 80 &  & 20 &  &  &  &  &  \\
   1 & 30 & -30 & -20 & 0 & 0 & 0 & -50 &  \\
   2 & 15 & -25 & 0 & 0 & +10 & 10 & -15 & O \\
   &  &  &  &  &  &  & +20 & 50 \\
   3 & 100 &  &  &  &  &  &  &  \\
   \hline
   \end{array} 
   $$

1. The panic from the Russian crisis would make the price fall by 30 (from 80 to 50 on date 1) by itself.
   - By forcing [[Class Note 13 The LTCM Meltdown|LTCM]] to liquidate,  it makes the price fall by 50 (80 to 30).
   - The losses force a liquidation,  similar to a bank run.

## XVII. Delayed Liquidation and [[Class Note 13 The LTCM Meltdown|LTCM]]
1. In practice,  [[Class Note 13 The LTCM Meltdown|LTCM]] was careful to get advanced assurance from margin lenders not to force immediate margin calls.
   - This allowed them some time to meet the calls.
   - If [[Class Note 13 The LTCM Meltdown|LTCM]] could delay liquidation until date 2,  they could still buy 5 at date 1.

1. **Table 4: A Delayed Meltdown if [[Class Note 13 The LTCM Meltdown|LTCM]] Can Wait to Liquidate**:

   $$ 
   \begin{array}{|c|c|c|c|c|c|c|c|c|}
   \hline
   \text{Date} & \text{Price} & \text{Noise Trade Occurs At Date 1,     } & \text{LTCM Trade} & \text{LTCM Position} & \text{Other Arb Trade} & \text{Other Arb Position} & \text{Total Order Imbalance} & \text{Reverted Price If News Trade} \\
   \hline
   0 & 80 &  & 20 &  &  &  &  &  \\
   1 & 55 & -30 & +5 & 25 & 0 & 0 & -25 &  \\
   2 & 15 & -25 & -25 & 0 & +10 & 10 & -40 & Or +20 & 75 \\
   3 & 100 &  &  &  &  &  &  &  \\
   \hline
   \end{array} 
   $$

## XVIII. Expected Price Change from Date 1 to Date 2
1. With probability $q$,  a noise trade forces the price down to 15 because [[Class Note 13 The LTCM Meltdown|LTCM]] is forced out.
1. With probability $1 - q$,  there is a news trade that pushes the price up to 75 (and then [[Class Note 13 The LTCM Meltdown|LTCM]] is not forced out).
1. The expected price change is:
   $$ q(15 - 55) + (1 - q)(75 - 55) = 20 - q(60). $$

1. For $q = 0.25$,  this is +5,  but for $q = 0.5$,  it is -10.
1. Assume $q = 0.5$ to learn about the front running problem faced by [[Class Note 13 The LTCM Meltdown|LTCM]].
   - When the expected price change from date 1 to date 2 is negative,  any trader who knows they must sell on date 2 will instead sell on date 1.
   - Further,  if not subject to PBA,  it will be profitable to short on date 1 as long as the expected price change is negative.

1. The presence of fear of fire sales affects market dynamics.