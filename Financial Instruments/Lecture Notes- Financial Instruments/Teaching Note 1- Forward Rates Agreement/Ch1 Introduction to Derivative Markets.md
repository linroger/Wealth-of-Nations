---
aliases:
  - 
  - 
title: Ch1 Introduction to Derivative Markets
tags:
  - '#derivative_markets'
  - '#financial_engineering'
  - '#long_position'
  - '#market_makers'
  - '#regulatory_arbitrage'
  - '#risk_management'
  - '#short_selling'
  - '#speculation'
  - '#transaction_costs'
---
# Ch1 Introduction to Derivative Markets

[[C[[Ch1 Introduction to Derivative Markets]]vative Markets]]
	- [[Chapter 6 (Hull) Hedging Strategies with Forwards]]
	- [[Deriving Forward Exchange Rate Numerical Example]]
	- [[Primary vs. Secondary Commodities]]
	- [[Foreign Exchange Quoting Conventions]]
	- [[Forward Contracts on Exchange Rates]]
	- [[Forwards and Futures Notes]]
	- [[Hedging Strategies with Forwards]]
	- [[Financial Instruments/Lecture Notes/Teaching Note 1- Forward Rates Agreement/Interest Rates,  Carry Trades,  and Exchange Rate Movements]]
	- [[Teaching Note 1 Forward Rates Agreement]]

Financial markets in theory serve two purposes. Markets permit diversifiable risk to be widely shared. This is efficient: By definition,  diversifiable risk vanishes when it is widely shared. At the same time,  financial markets permit nondiversifiable risk,  which does not vanish when shared,  to be held by those most willing to hold it. Thus,  the fundamental economic idea underlying the concepts and markets is that the existence of risk-sharing mechanisms benefits everyone.

### USES OF DERIVATIVES
- Risk management. [Derivatives](Derivatives.md) are a tool for companies and other users to reduce risks.
-\Speculation. [Derivatives](Derivatives.md) can serve as investment vehicles. [Derivatives](Derivatives.md) can provide a way to make bets that are highly leveraged (that is,  the potential gain or loss on the bet can be large relative to the initial cost of making the bet) and tailored to a specific view.
- Reduced transaction costs.
	- Sometimes derivatives provide a lower-cost way to undertake a particular financial transaction. For ex ample,  the manager of a mutual fund may wish to sell stocks and buy bonds. Doing this entails paying fees to brokers and paying other trading costs,  such as the bid-ask spread
	- It is possible to trade derivatives instead and achieve the same economic effect as if stocks had actually been sold and replaced by bonds. Using the derivative might result in lower transaction costs than actually selling stocks and buying bonds.
- Regulatory arbitrage.
	- It is sometimes possible to circumvent regulatory restrictions,  taxes,  and accounting rules by trading derivatives. [Derivatives](Derivatives.md) are often used,  for example,  to achieve the economic sale of stock (receive cash and eliminate the risk of holding the stock) while still maintaining physical possession of the stock.
	- This transaction may allow the owner to defer taxes on the sale of the stock,  or retain voting rights,  without the risk of holding the stock.

#### PERSPECTIVES ON DERIVATIVES
- How you think about derivatives depends on who you are. The following are three distinct perspectives on derivatives:
	- The end-user perspective.
		- End-users are the corporations,  investment managers,  and investors who enter into derivative contracts for the reasons listed in the previous section: to manage risk,  speculate,  reduce costs,  or avoid a rule or regulation. Endusers have a goal (for example,  risk reduction) and care about how a derivative helps to meet that goal.
	- The market-maker perspective.
		- Market-makers are intermediaries,  traders who will buy derivatives from customers who wish to sell,  and sell derivatives to customers who wish to buy. In order to make money,  market-makers charge a spread: They buy at a low price and sell at a high price. In this respect market-makers are like grocers,  who buy at the low wholesale price and sell at the higher retail price. Market-makers are also like grocers in that their inventory reflects customer demands rather than their own preferences:
		- After dealing with customers,  market-makers are left with whatever position results from accommodating customer demands. Market-makers typically hedge this risk and thus are deeply concerned about the mathematical details of pricing and hedging.
	- The economic observer.
		- Finally,  we can look at the use of derivatives,  the activities of the market-makers,  the organization of the markets,  and the logic of the pricing models and try to make sense of everything. This is the activity of the economic observer.

#### FINANCIAL ENGINEERING AND SECURITY DESIGN
- One of the major ideas in derivatives—perhaps the major idea—is that it is generally possible to create a given payoff in multiple ways. The construction of a given financial product from other products is sometimes called financial engineering.
- The fact that this is possible has several implications.
	- First,  since market-makers need to hedge their positions,  this idea is central in understanding how market-making works. The market-maker sells a contract to an end-user,  and then creates an offsetting position that pays him if it is necessary to pay the customer. This creates a hedged position.
	- Second,  the idea that a given contract can be replicated often suggests how it can be customized. The market-maker can,  in effect,  turn dials to change the risk,  initial premium,  and payment characteristics of a derivative. These changes permit the creation of a product that is more appropriate for a given situation.
	- Third,  it is often possible to improve intuition about a given derivative by realizing that it is equivalent to something we already understand.
	- Finally,  because there are multiple ways to create a payoff,  the regulatory arbitrage discussed above can be difficult to stop. Distinctions existing in the tax code,  or in regulations,  may not be enforceable,  since a particular security or derivative that is regulated or taxed may be easily replaced by one that is treated differently but has the same economic profile.
- The bid price is what the market-maker pays; hence it is the price at which you sell.
- The offer price is what the market-maker will sell for; hence it is what you have to pay.
- The terminology reflects the perspective of the market-maker.
- What happens to your shares after you buy them? Unless you make other arrangements,  shares are typically held in a central depository (in the U.S.,  at the DTCC) in the name of your broker. Such securities are said to be held in street name.

#### SHORT-SELLING
- The sale of a stock you do not already own is called a short-sale.
- When we buy something,  we are said to have a long position in that thing.
	- For example,  if we buy the stock of XYZ,  we pay cash and receive the stock. Some time later,  we sell the stock and receive cash.
	- This transaction is a form of lending,  in that we pay money today and receive money back in the future.
	- For many assets the rate of return we receive is not known in advance (the return depends upon whether the stock price goes up or down),  but it is a loan nonetheless.
- The opposite of a long position is a short position. A short-sale of XYZ entails borrowing shares of XYZ from an owner,  and then selling them,  receiving the cash.
	- Some time later,  we buy back the XYZ stock,  paying cash for it,  and return it to the lender.
- A shortsale can be viewed as a way of borrowing money. With ordinary borrowing,  you receive money today and repay it later,  paying a rate of interest set in advance.
- This also happens with a short-sale,  except that typically you don't know in advance the rate you will pay.
- There are at least three reasons to short-sell:
	- 1. Speculation: A short-sale,  considered by itself,  makes money if the price of the stock goes down. The idea is to first sell high and then buy low. (With a long position,  the idea is to first buy low and then sell high.)
	- 2. Financing: A short-sale is a way to borrow money, and it is frequently used as a form of financing. This is very common in the bond market,  for example.
	- 3. Hedging: You can undertake a short-sale to offset the risk of owning the stock or a derivative on the stock. This is frequently done by market-makers and traders.

Cash flows associated with short-selling a share of IBM for 90 days. $S_0$ and S90 are the share prices on days 0 and 90. Note that the short-seller must pay the dividend,  D,  to the share-lender.

|  | Day 0 | Dividend Ex-Day | Day 90 |
| :--- | :--- | :--- | ---- |
| Action | Borrow shares | - | Return shares |
| Security | Sell shares | - | Purchase shares |
| Cash | $+S_0$ | - D | $-S_0$ |

 ![500](IMG-20240913171226948.png)