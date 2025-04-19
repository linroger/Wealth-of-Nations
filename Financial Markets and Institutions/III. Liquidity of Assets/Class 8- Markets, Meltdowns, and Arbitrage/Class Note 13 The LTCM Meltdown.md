---
tags:
  - arbitrage
  - financial_markets
  - liquidity_risk
  - ltcm_meltdown
  - risk_management
aliases:
  - Diamond-Dybvig model
  - LTCM
  - Long Term Capital Management
key_concepts:
  - Russian default
  - Shleifer-Vishny paper
  - arbitrage opportunities
  - illiquid assets
  - liquidity risk
  - margin calls
---

# Class Note 13 The LTCM Meltdown

## I.Introduction

To understand Long Term Capital Management's ([[Class Note 13 The LTCM Meltdown|LTCM]]) meltdown,  note that they were taking liquidity risk in two ways. First,  they were long less liquid assets and short more liquid assets that provided almost the same cash flows. For example,  they were long the 29.5 year off the run treasury and short the 30 year on the run treasury bond. Second,  they took large margined positions. They were subject to the liquidity risk of a margin call where they would be forced to close out the position. If they faced liquidation losses from unwinding positions,  and if their capital was sufficiently impaired to make losses to lenders possible,  they could have a "run" as lenders foreclose in anticipation of other lenders foreclosing

Whenever there is a limit to liquidity creation,  illiquid assets will need to offer higher expected returns than more liquid assets. Institutions like banks can be set up to partially arbitrage away this price of illiquidity. The arbitrage between the more and less liquid assets is a significant part of the [[Class Note 13 The LTCM Meltdown|LTCM]] strategy. They specialize in near arbitrage between assets for which it was hard to see that their only difference is liquidity (although this is not their stated goal,  it is my interpretation). [[Class Note 13 The LTCM Meltdown|LTCM]] has a comparative advantage in making these bets. They have the quantitative and creative skills to value the assets (probably the best such skills in the world). And because they lock in investors for a long term,  it seemed unlikely that they would need to liquidate early

Their losses got so large that they faced problems with margin calls rather than investor withdrawals. Thus,  they lost their long horizon. Second,  during the period of panic after the Russian default,  the significance of liquidity on asset prices increased. The Russian default revealed information that the International Monetary Fund (the closest thing to an international lender of last resort) would not bail out a country that did not live up to its promises,  even if this might damage the stability of world financial markets. Investors gravitated toward more liquid assets,  depressing the price of illiquid assets. Relative to liquid. This caused the correlation between their positions to increase beyond.

What had existed in the previous data they had used to estimate the value at risk in their positions.

All of this we can easily understand in the Diamond-Dybvig bank run model. It shows that it pays to try to earn the liquidity premium,  but that you are exposed to the risk that you might melt down. That model does not stress that some liquidity bets are hard to see and require special asset pricing skills to identify. In addition,  there is more that we can learn by focusing in general on the risk of taking long-term arbitrage-like positions.

The goal of this class note is to understand the risks in taking positions that are very similar to riskless arbitrage opportunities. I want to both simplify and extend the ideas in the Shleifer-Vishny paper in the packet,  "The Limits to Arbitrage." Read the words in that paper. You can use the math in this note if you do not want to invest in the math in their model

Begin with a traditional arbitrage opportunity. Suppose that shares of ExxonMobil on the NYSE sold for $\$90$ per share,    and thoseon the Chicagostock exchange sold for $\$80$ per share. If you can simultaneously buy 1 millon in Chicago shares and sell short 1 million on the NYSE,     you make a sure profit by immediately covering the short with the shares you buy in Chicago. If the cost were less than $\$10$ per share,  anyone who saw this would make the trade. It takes little skill to see that all ExxonMobil shares are the same security,  so we expect that the price will not be much different on the two exchanges.

Suppose that instead,  there were two "effectively similar" trades. For example,  suppose that a share of a holding company would distribute one share of ExxonMobil plus one of ChevronTexaco in exactly two years,  and that the holding company was selling forless than the price of one share of ExxonMobil plus one of ChevronTexaco You can't just short one share of ExxonMobil and one of ChevronTexaco and buy one share of the holding company to immediately cover the short. There are two problems: the items are not legally identical,  and it may be that some others do not see that the holding company will eventually be exactly identical to the two shares of oil stock. Because they are not legally identical,  you must carry the position for two years to cover the short. Further,  if not everyone sees that positions are identical; the prices will not

Necessarily always be in line. The fact that not everyone sees them to be identical is the reason that they mightbe out of line today,  presenting the apparent profit opportunity to you.

Because not everyone sees the opportunity today,  it is quite possible that not everyone will see it in one year. If you need to close out the position in one year,  the gap may have widened. This is not a problem if you never need to close it out in one year and you have no limit to the amount of capital that you can bring to such positions.

Because outside investors and lenders do not know the ability or see the models of hedge fund managers,  they will limit the amount of capital that they provide to managers. Investors and lenders do see their ex-post performance and use it to estimate the ability of managers. This is the reason for arbitrageurs' limited access to capital and for things that worklike margin calls after a loss. Shelifer andVishny callit performance based arbitrage ("PBA"). If an arbitraguer ("arb") loses money,  then outsiders reduce their estimate of the quality of the arb's analysis,  and pull out funds or force him or her to liquidate positions (or,  if the outsider is a lender,  force margin calls). This note examines how limits on the amount of capital that an arb can raise,  and these possible future losses of capital under management,  can influence the bets that an arb will place. We examine a very simple version of this: investors will pull all funds under management out whenever there is a loss. More generally,  the amount of capital available would be a function of the extent of the loss,  but we can see the main point with the more extreme assumption that if the arb loses any money at all,  he loses all assets under management. This simplifies the analysis because the arb will just choose whether to invest at date 1 or date 2,  instead of choosing the fraction of funds to invest at each date.

### II. An Example

Consider two assets that will be identical on date 3,  but it is not clear yet that they are identical. On date 3,  asset A will be worth 100 units of asset B.If A is not selling for 100 times the price of B,  there is a long-term arbitrage opportunity

Today is date 1 and the price of asset A is $p_1$ $\mathbf{p}_{1}$ is the date 1 relative price of asset A to asset B,  and the relative price will become 100 on date 3). On date 2,  the assets will revert toward the proper price of 100 (possibly all the way) with probability 1-q.We will refer to this revision toward the proper price as a“news trade.” With probability q,  however,  the mis-pricing will get worse,  and the price will be $\mathbf{p}_{2}<\mathbf{p}_{1}<100$ Following Shleifer-Vishny,  we will say that this further mis-pricing is due to misinformed “noise traders.”It could be for any reason,  however. If the assets differ in liquidity,  and the significance of liquidity increases,  this is an alternative motivation for the prices diverging.

Extreme performance based arbitrage works as follows. If the arb loses money at date t,  he is out of the arb business forever (could generalize this to"if he loses enough money,  "but this makes the math a little harder)

The arb gets compensated as a percentage of assets under management (a very similar analysis applies if instead the arb gets a percent of profits)

Suppose that the price at date 1 is $\mathbf{p}_{1}=80$ ,  and that on date 2 with probability q it will fall to $\mathbf{p}_{2}=70$ (due to a noise trade) and with probability 1-q it will rise to by 20 to $p_2$ =100 (due to a news trade). On date 3 the bet will mature and as a result,  $\mathbf{p}_{3}=100$ for sure.

To see the effect of PBA,  let us compare it with a benchmark of the case of someone investinghis or her own money,  whichis equivalent toa hedge fund not subject to PBA.

## II. A. Decisions by an investor not subject to Performance Based Arbitrage

If the nonPBAinvestor invests at date 1,  the value at date 3 is 100 for sure,  sc if theinvestor invests $D_{1}$ at date 1,  the date 3 value is

$$\begin{array}{c}(100/80)\mathrm D_1\:\mathrm or\$\mathrm V/\mathrm p_1)\mathrm D_1\:.\end{array}$$

In general

If instead the nonPBA investor waits until date 2 to invest (and just holds treasury bills yielding $0\%$ for the period),  then the price will be 70 or 100 (with prob q and 1-q respectively). When the price drops to 70,  the non PBA investor will buy $D_{1}$ units,  and when the price is 100,  the investor will continue to hold treasury bills. The expected date 3 value of waiting until date 2 to take a position is.

$$[\mathrm{q}(100/70)+(1\mathrm{-q})1]\mathrm{D}_{1}\quad\mathrm{or},    \mathrm{q}(\mathrm{V}\mathrm{p}_{2})+(1\mathrm{-q})]\mathrm{D}_{1}$$

The non PBA investor will go ahead and invest at date 1 when it gives a larger expected value of assets,  or:

$$100/80\:\geq q(100/70)+(1-q),    \:\mathrm{or}$$

$$\mathrm{q}<7/12=0.58\\\mathrm{or~in~general:}\:q\leq\frac{p_{2}(V-p_{1})}{p_{1}(V-p_{2})}\:.$$

A regularinvestorwouldwait only if the increased expected return from waiting to invest times the probability that the return increases,  exceeds the return from investing today.

## Decisions by a hedge fund that is subject to PBA

If the PBA arb invests $D_{1}$ at date 1,  his fund is closed with probability q,  when the price moves away from fundamental value.

Investing $D_{1}$ at date 1 produces expected date 2 assets under management of:

$$\mathrm{(1-q)(100/80)D_1+q(0).}$$

The last term,  $q(0)$ is zero because,  if he loses money,  he is out of business.

If the PBA arb waits until date 2 to invest,  he won't lose assets under management,  but with probability 1-q,  the profit opportunity goes away. The expected value of date 3 assets under management if hewaits toinvest at date 2 it then:

$$\mathrm{q(100/70)D_1+(1-q)D_1.}$$

The PBA arb invests at date 1 when:

$$\text{(1-q)(100/80)}\geq\text{q(100/70)}+\text{(1-q)}\quad\text{or}$$

$$q<7/47=0.15$$

$$\text{or in general if}\:q<\frac{p_2(V-p_1)}{p_1(V-p_2)+p_2V}\:.$$

Thus,  arbs subject to PBA are averse to profitable long-term bets that might go against them

If it takes special skill to see these opportunities,  and all with those skills are subject to PBA,  long-term risky investments won't be undertaken by arb's.

Table 1: Current and future prices:

<table>
	<tbody>
		<tr>
			<th>Date</th>
			<th>Price If Noise trade occurs at date 22 (probability=q)</th>
			<th>Price If Revert To True Value (“News trade" at date 2) (probability=1-q)</th>
		</tr>
		<tr>
			<td>1</td>
			<td>80</td>
			<td> </td>
		</tr>
		<tr>
			<td>2</td>
			<td>70</td>
			<td>100</td>
		</tr>
		<tr>
			<td>3</td>
			<td>100</td>
			<td>100</td>
		</tr>
	</tbody>
</table>

On date 2,  any arbs that see the opportunity will invest in it,  so long as $p_2<100$ But that need not prevent the market from being out of line at date 2. The arbs who see the date 2 opportunity have limited access to capital,  and as a result they will not push the price all the way to 100,  despite being a pure arbitrage. Remember that it is not obvious to all that this is an arbitrage opportunity.

The prices in table 1 already reflect the activities of arbs. We will assume that $q=$ 0.25 for some examples,  and for other examples we assume $q=0.5$ .For both values,  no arb subject to PBA will trade at date 1 $(q>0.15)$ ,  but non PBA arbs will trade at date 1 $(q<0.58)$

II. C.

## [[Class Note 13 The LTCM Meltdown|LTCM]] as a long term arb

Suppose that your fund had a very good reputation,  and you could get funds locked in and avoid PBA. You would have a relatively easy life (assuming that you really did have the skill to see opportunities),  because long term opportunities would be passed over by short term PBA funds.

Suppose that at date 1 there are PBA funds and your long-term fund. The PBA funds wait until date 2 to get in,  hold treasuries from dates 1 to 2,  and hold treasuries from 2 to 3 if the arbitrage opportunity is gone by then.

### The two-period expected return of a PBA fund is

$$\begin{aligned}
\mathrm{q(100/70)+(1-q)~(1)~=q(1+3/7)+(1-q)1}& =\mathbf{q}(3/7)\:+\:1 \\
&=\:0.25(3/7)+1=1.0525\:\mathrm{(for~q=0.25)}
\end{aligned}$$

The two-period return of the long-term fund (assuming that it raises no new capital at date 2,     so it can't scale up its bet if the price goes down at date 2).

The ability to lock in the funds for the long term allows the fund to take different bets in markets with less competition. This is part of the story behind the establishment of [[Class Note 13 The LTCM Meltdown|LTCM]]. Their reputation was so strong that they could get moneylocked in.

The problem arose when they lost so much money that they faced margin calls. For a large enough loss,    even [[Class Note 13 The LTCM Meltdown|LTCM]] had the equivalent of PBA,    leading to forced sales at the bottom. [[Class Note 13 The LTCM Meltdown|LTCM]] had locked in investor's old money. But once they had lost enough to face margin calls,     their ability to raise new capital to meet the calls without liquidating their positions was limited. Not only was there standard PBA uncertainty about [[Class Note 13 The LTCM Meltdown|LTCM]] 's ability to continue to make excess returns at low risk,     but there was a bank run style collective action problem. Unless [[Class Note 13 The LTCM Meltdown|LTCM]] could attract enough capital to meet all near term margin calls,    it would be forced to get out at the bottom. Anticipating this,    they would be unable to raise smaller amounts of capital. Since the market thought it was likely that they would soon liquidate and push down the price,     the current price of their positions moved against them due to front running.

Let us modify the notion that [[Class Note 13 The LTCM Meltdown|LTCM]] will not lose funds under management,     to assume instead that theywill lose them only if their loss isvery large (defined below). If [[Class Note 13 The LTCM Meltdown|LTCM]] assumed that their losses would not be“very large",    this would not affect the position that they take. And if they (and others like them) did get such a loss,     it would push down the price as they were forced to liquidate.

A large unanticipated price drop would result in a meltdown (forced liquidation) A meltdown causes an even larger price drop when the arbs ([[Class Note 13 The LTCM Meltdown|LTCM]] in particular) liquidate. Normally,     the trades of arbs are a stabilizing force,     offsetting the trades of noise traders who would push the price further below 100. When there is a meltdown,     this reverses. Instead of being a stabilizing force,    the arbs further destabilize the price by joining the selling

To evaluate this further,    we need to think about price formation. This gets a bit complicated,     and we will just follow Shelifer-Vishny.

The prices we used in table 1 are those that prevail AFTER the arbs have put on their trades. If there were no trades coming in during a period,    theprice would remain unchanged. If there were only noise trading,    the price goes down when noise traders sell and up when they buy. If there is also some trade by arbs,     the price changes by the net amount of trade. Thatis:

$$P_t=\left\{\begin{matrix}P_{t-1}+\text{Noise trade }+\text{arb trades}\quad\text{(happens with prob q)}\\P_{t-1}+\text{News trades}\quad\text{(happens with prob 1-q)}\end{matrix}\right\}$$

We could allow for arb trades in addition to news trades,     but in normal circumstances,    news trades from many investors who see the mis-pricing will be sufficient to remove arbitrage opportunities.

Let us assume that [[Class Note 13 The LTCM Meltdown|LTCM]] already had established a position in the trade before date 1 (because of past mis-pricing),     and was long 20 units. Thus if [[Class Note 13 The LTCM Meltdown|LTCM]] was not long 20 units,     the price would be lower by 20. Arbs who are subject to PBA would not trade before date 2. (In practice,     other arbs sometimes copied [[Class Note 13 The LTCM Meltdown|LTCM]],     so there might be some others who each took smaller positions in the same bets as [[Class Note 13 The LTCM Meltdown|LTCM]]. We will ignore this.) The prices in back in table 1 include the efforts of various arbs. If they were not present. The date 1 and 2 prices would be lower,     in part because of liquidity differences,    in part because of "noise trader" selling.

Table 2 shows the impact of the arbs. Before date 1,    [[Class Note 13 The LTCM Meltdown|LTCM]] had a position of 20. On date 1,     the price is 80. The price would have dropped on that date,     but [[Class Note 13 The LTCM Meltdown|LTCM]] bought 5 more,    offsetting selling of 5 by noise traders on date 1. There is further noise trade on date 2 with probabiliy q.If the noise trade occurs at date 2 it is noise trader selling of 25. This is partly offset by added buying of 5 more units by [[Class Note 13 The LTCM Meltdown|LTCM]],     and buying of 10 units
By PBA arbs who see the opportunity (and are willing to bet now that it is short-term arbitrage).
Table 2: Trades by arbs and noise traders that produce prices in table 1.

<table>
	<tbody>
		<tr>
			<th rowspan="2">Date</th>
			<th rowspan="2">Price</th>
			<th colspan="6">Tf Noise $\mathrm{lccurs}$ $\operatorname{At}$Date 2</th>
			<th> </th>
			<th colspan="2">If News trade at date 2</th>
		</tr>
		<tr>
			<th>|Noise trade |occurs at l,     |and with |prob. Q At 2</th>
			<th>Ltcm Trade</th>
			<th>Ltcm Position</th>
			<th>Other Arb Trade</th>
			<th>Other Arb Position</th>
			<th>Total Order Imbalance</th>
			<th> </th>
			<th>News Trade (Prob 1-q) 1</th>
			<th>$\mathrm{Reverted}$ |Price If News Trade</th>
		</tr>
		<tr>
			<td>0</td>
			<td>80</td>
			<td> </td>
			<td> </td>
			<td>20</td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>1</td>
			<td>80</td>
			<td>-5</td>
			<td>+5</td>
			<td>25</td>
			<td>0</td>
			<td>0</td>
			<td>0</td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>2</td>
			<td>70</td>
			<td>-25</td>
			<td>+5</td>
			<td>30</td>
			<td>+10</td>
			<td>10</td>
			<td>-10</td>
			<td>Or</td>
			<td>+20</td>
			<td>100</td>
		</tr>
		<tr>
			<td>3</td>
			<td>100</td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
	</tbody>
</table>

Supposeinstead that thingsplay out differently on and after date 1. TheRussian default causes panic selling at date 1 by noise traders,    when [[Class Note 13 The LTCM Meltdown|LTCM]] already has a position of 20. The noise trade at 1 is now -30 .If this loss is large enough to force [[Class Note 13 The LTCM Meltdown|LTCM]] out immediately at date 1,    forcing them to sell 20 at date 1,    look at the meltdown in table 3:

Table 3: A meltdown after the Russian default,     if [[Class Note 13 The LTCM Meltdown|LTCM]] must liquidate immediately

<table>
	<tbody>
		<tr>
			<th rowspan="2">Date</th>
			<th rowspan="2">Price</th>
			<th colspan="6">If Noise Trade Occurs At Date 2</th>
			<th> </th>
			<th colspan="2">If News trade at date 2</th>
		</tr>
		<tr>
			<th>Noise trade |occurs at l,     with and prob at date $\div 2$ 4 1</th>
			<th>|LTCM trade</th>
			<th>$\mathrm{LTCM}$ |position</th>
			<th>Other arb trade</th>
			<th>Other arb |position</th>
			<th>Total Order imbalance</th>
			<th>e</th>
			<th>News |trade (prob. $1-q)$</th>
			<th>Reverted price if news trade</th>
		</tr>
		<tr>
			<td>0</td>
			<td>80</td>
			<td> </td>
			<td> </td>
			<td>20</td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>1</td>
			<td>30</td>
			<td>-30</td>
			<td>-20</td>
			<td>0</td>
			<td>0</td>
			<td>0</td>
			<td>-50</td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>2</td>
			<td>15</td>
			<td>-25</td>
			<td>0</td>
			<td>0</td>
			<td>+10</td>
			<td>10</td>
			<td>-15</td>
			<td>Or</td>
			<td>+20</td>
			<td>50</td>
		</tr>
		<tr>
			<td>3</td>
			<td>100</td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
	</tbody>
</table>

The panic from the Russian crisis would make the price fall by 30 (from 80 to 50 on date 1) by itself. By forcing the [[Class Note 13 The LTCM Meltdown|LTCM]] to liquidate,    it makes the price fall by 50 (80 to 30). The losses force aliquidation,    in awayvery similar to a bankrun.

In practice,    [[Class Note 13 The LTCM Meltdown|LTCM]] was careful to get some advanced assurance from margin lenders not to force immediate margin calls. As a result,    they had some time to meet the calls. We can interpret this as meaning that they are not forced out at date 1,    but can wait until date 2 to sell. If the news trade were to arrive on date 2 (which happens with
probability 1-q),     they could avoid liquidating their position. However,     with probabilty q,     the noise trade of -25 comes in at date 2,     and [[Class Note 13 The LTCM Meltdown|LTCM]] would be forced to sell on date 2.

Suppose that [[Class Note 13 The LTCM Meltdown|LTCM]] could delayliquidation until date 2,    and it could still buy 5 at date 1 to seek a profit. Then the prices after the Russian default would be those shown in table 4.

Table 4: A delayed meltdown if [[Class Note 13 The LTCM Meltdown|LTCM]] canwait toliquidate:

<table>
	<tbody>
		<tr>
			<th rowspan="2">Date</th>
			<th rowspan="2">Price</th>
			<th colspan="6">ff Nois 111 rad $() ccun$ $\operatorname{At}\operatorname{At}$Date 2 </th>
			<th> </th>
			<th colspan="2">If News trade at t=2</th>
		</tr>
		<tr>
			<th>Noise Trade Occurs At 1,     And With $\operatorname{Prob}\operatorname{q}\operatorname{At}2$</th>
			<th>LTCM Trade</th>
			<th>LTCM Position</th>
			<th>Other Arb Trade</th>
			<th>Other Arb Position</th>
			<th>Total Order Imbal m</th>
			<th>ance</th>
			<th>News Trade (0 ccurs With Prob 2) lq at date ·</th>
			<th>Reverted Price If News Trade</th>
		</tr>
		<tr>
			<td>0</td>
			<td>80</td>
			<td> </td>
			<td> </td>
			<td>20</td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>1</td>
			<td>55</td>
			<td>-30</td>
			<td>+5</td>
			<td>25</td>
			<td>0</td>
			<td>0</td>
			<td>-2!</td>
			<td>5</td>
			<td> </td>
			<td> </td>
		</tr>
		<tr>
			<td>2</td>
			<td>15</td>
			<td>-25</td>
			<td>-25</td>
			<td>0</td>
			<td>+10</td>
			<td>10</td>
			<td>-41</td>
			<td> Or</td>
			<td>+20</td>
			<td>75</td>
		</tr>
		<tr>
			<td>3</td>
			<td>100</td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
			<td> </td>
		</tr>
	</tbody>
</table>

Let us compute the expected price change from date 1 to 2. With probability q,    there is a noise trade that forces it down to 15,     because [[Class Note 13 The LTCM Meltdown|LTCM]] is forced out. With probability 1-q,     there is a news trade,     that pushes the price up to 75 (and then [[Class Note 13 The LTCM Meltdown|LTCM]] is not forced out). The expected price change is then:

$$\begin{matrix}\mathrm{q (15-55)+(1-q)(75-55)=}&20-\mathrm{q (60)}\end{matrix}$$

For $q=$ ，this is +5 ,    but for $q=0.5$ ,     it is -10 .Let's assume $q=0.5$ ,     and we will learn something about thefront runningproblem faced by [[Class Note 13 The LTCM Meltdown|LTCM]].

When the expected price change from date 1 to 2 is negative,    any traderwho knows that he or she must sell on date 2 will instead sell on date 1. Further,     if not subject to PBA,    it will be profitable to short on date 1 so long as the expected price change is negative. If some of this trade occurs,    it will further reduce the date 1 price. We will examine this in homework 5.