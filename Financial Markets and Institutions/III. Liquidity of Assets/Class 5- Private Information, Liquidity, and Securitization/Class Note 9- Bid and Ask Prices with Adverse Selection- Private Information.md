---
title: Class note 9 BID and ASK PRICES WITH ADVERSE SELECTION -PRIVATE INFORMATION
aliases: [Class note 9 BID and ASK PRICES WITH ADVERSE SELECTION -PRIVATE INFORMATION]
linter-yaml-title-alias: Class note 9 BID and ASK PRICES WITH ADVERSE SELECTION -PRIVATE INFORMATION
---

# Class Note 9- Bid and Ask Prices with Adverse Selection- Private Information
### Class note 9 BID and ASK PRICES WITH ADVERSE SELECTION/PRIVATE INFORMATION

Based on The Only Game in Town,  and Glosten-Milgrom
1.The Setup

1. Two types of trader: informed and liquidity (can lump the "misinformed" of The Only Game in Town together with the uninformed). All traders and market makers are risk neutral,  so there is no risk premium.
a.Simple private information:informed traders know exactly what the firm will be worth on some fixed date in the future..
	- i. V is the unknown value.Everyone knows $V$ will be either zero or one,  and the informed know which of the values will occur
	- ii. The uninformed liquidity traders start out believing that the probability that $V=1$ is 1/21/2 is also the probability that $V=0$).
b.Each instant,  at most one trade comes in,  and we assume all trades are the same size (abstracts from block trading). This means at each instant,  at most one trader either gets private information about $V$ (and then has a reason to speculate),  or finds out about his (or her) need for liquidity (implying a non-speculative reason to buy or sell).
c. Informed traders buy when stock is underpriced at the ask,  sell when overpriced at the bid (and do nothing if value is between the bid and the ask))
	- i. Liquidity traders buy when they have excess liquidity (money to invest) and sell when they need liquidity. The need for liquidity is not related to the value of the stock or the private information that they do not have. Half of all liquidity traders buy and the other half sell. Any given liquidity trader buys with probability one-half
	- ii. A trader buys one share if he buys and sells one if he sells. We abstract from block trading and note that introducing risk aversion would result in a limit to the size of trades made by even very well informed traders
d. The competitive market makers earn zero monopoly profits and break even on average across trades.
	- i.Market makers do not observe the privateinformation of the informed traders. As a result,  market makers lose money when trading with the informed
	- ii. The market maker sets prices first,  then traders can choose the type of trade they want at the fixed price. To break even,  market makers set a bid-ask spread. This implies that they make money from trades with liquidity traders.The competitive break even condition implies that the average loss to informed traders is equal to the average profit from liquidity
	- iii.The market maker cannot distinguish between liquidity trades and information trades and must quote a single bid and ask price pair.Break even on average implies that:
		- (1) The bid is the expected value of the stock given public information and the fact that a sell order arrives this instant
		- (2) The ask is the expected value of the stock given all public information and the fact that a buy order arrives this instant
For example,  if there are no informed traders the bid-ask spread is zero.If there are nothing but informed traders,  there is no bid-ask spread which allows the market maker to break even,  because he loses on all trades to informed.
 e.One Period Example
	- i. Absent a trade,  price of the stock would be 1/2 because there is a 50-50 chance of being worth 1 or O. If no informed traders existed,  this would be the price,  with no spread. This represents the"grand mean"average value of the stock
	- ii. 1/2 of all traders are informed (more than in reality),  1/2 uninformed. This means that when an order comes in,  the probability it is an informed trade is 1/2
		- i. Consider first the ask price.If a buy order comes in,  and it is from an informed,  it must be that the private information is that the stock is worth 1(otherwise the informed trader would sell) and the market makerwill make a"profit"of:
				- ask-1(= a loss of 1-ask)
		- If the buy is from a liquidity trader,  the stock is equally likely to be worth O as 1,  so the average profit from the trade is:ask -[(1/2 x1)+(1/2 x 0)]=ask -1/2
			- The average profit is the average of these two"profits,  "so break even is when
				-$$V_2x(ask-1)+V_2x(ask-V_2)=0$$
				- $$\mathrm{ask}=3/4.$$
					- (Equivalently,  3/4 is the expected value of the stock given a buy order).
	- iv. Bid price determination
	- If a sell order comes in,  and it is from an informed,  it must be that the private information is that the stock is worth O (otherwise the informed trader would buy) and the market maker will make 	- a "profit" of: 0-bid = a loss of bid - 0).
	- If the sell is from a liquidity trader,  the stock is equally likely to be worth O as 1,  so the average profit from the trade is: ${} $[(\frac{1}{2} \times 1)+(\frac{1}{2} \times 0)]-bid=\frac{1}{2} - bid.$
		- A similar calculation to that for the ask,  but for the bid price solves:
			- $$\mathrm{\frac{1}{2} \times(0-bid)~+\frac{1}{2} \times(\frac{1}{2} -bid)=0}$$
			-$$ \mathrm{bid} = \frac{1}{4}$$
			- (Equivalently,  1/4 is the expected value of the stock given a sell order)
- A positive bid-ask spread is due to the losses to informed trading.It also makes the price reveal and reflect some of the private information of information traders.
- If the first trade were a buy (at the ask of 3/4),  then 3/4 would be the transaction price,  and would be the "baseline" for the next transaction. The new ask would be above 3/4 and the new bid above 1/4 Trade by informed traders makes the price adjust toward the value that is not yet known to the public.

## 2. Results
- Private information reduces liquidity. The larger the fraction of informed traders,  the larger the bid-ask spread,  but the quicker the price reflects the private information
- Private information implies that buying or selling a security will move the price,  even if you have noinformation and the market is competitive.
- Market efficiency is consistent with the ability to make money by trading if you have private information (but it is often difficult to tell if you have information that isreally private!)