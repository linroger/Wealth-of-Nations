---
title: Hedging Strategies with Forwards
tags:
  - continuous_dividends
  - dividend_yield
  - forward_contracts
  - prepaid_forward
  - stock_price
aliases:
  - continuous dividend
  - forward price
  - prepaid forward
  - stock index
key_concepts:
  - continuous dividend yield
  - dividend reinvestment
  - forward contract
  - future spot price
  - prepaid forward price
  - time to maturity
---

- [[Ch1 Introduction to Derivative Markets]]
- [[Chapter 6 (Hull) Hedging Strategies with Forwards]]
- [[Deriving Forward Exchange Rate Numerical Example]]
- [[Primary vs. Secondary Commodities]]
- [[Foreign Exchange Quoting Conventions]]
- [[Forward Contracts on Exchange Rates]]
- [[Forwards and Futures Notes]]
- [[Hedging Strategies with Forwards]]
- [[Financial Instruments/Lecture Notes/Teaching Note 1- Forward Rates Agreement/Interest Rates,  Carry Trades,  and Exchange Rate Movements]]
- [[Teaching Note 1Forward Rates Agreement]]

| TABLE 2          | Examples of underlying assets on which futures contracts are traded.                                                                                    |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Category         | Description                                                                                                                                             |
| Stock index      | S&P 500 index,  Euro Stoxx 50 index,  Nikkei 225,  Dow-Jones Industrials,  Dax,  NASDAQ,  Russell 2000,  S&P Sectors (healthcare,  utilities,  technology,  etc.) |
| Interest rate    | 30-year U.S. Treasury bond,  10-year U.S. Treasury notes,  [[A Guide to the Front End and Basis Swap Markets#Federal Funds Market|Fed Funds Rate]] ,  Euro-Bund,  Euro-Bobl,  LIBOR,  Euribor                                           |
| Foreign exchange | Euro,  Japanese yen,  British pound,  Swiss franc,  Australian dollar,  Canadian dollar,  Korean won                                                          |
| Commodity        | Oil,  natural gas,  gold,  copper,  aluminum,  corn,  wheat,  lumber,  hogs,  cattle,  milk                                                                       |
| Other            | Heating and cooling degree-days,  credit,  real estate                                                                                                    |

# Hedging Strategies with Forwards

- In this section we discuss some issues when using commodity futures and forwards to hedge commodity price exposure. First,  since commodities are heterogeneous and often costly to transport and store,  it is common to hedge a risk with a commodity contract that is imperfectly correlated with the risk being hedged. This gives rise to basis risk: The price of the commodity underlying the futures contract may move differently than the price of the commodity you are hedging. For example,  because of transportation cost and time,  the price of natural gas in California may differ from that in Louisiana,  which is the location underlying the principal natural gas futures contract
- Second,  in some cases one commodity may be used to hedge another. As an example of this we discuss the use of crude oil to hedge jet fuel. Finally,  weather derivatives provide another example of an instrument that can be used to cross-hedge.

### BASIS RISK

- Exchange-traded commodity futures contracts call for delivery of the underlying commodity at specific locations and specific dates. The actual commodity to be bought or sold may reside at a different location and the desired delivery date may not match that of the futures contract. Additionally,  the grade of the deliverable under the futures contract may not match the grade that is being delivered.
- This general problem of the futures or forward contract not representing exactly what is being hedged is called basis risk. Basis risk is a generic problem with commodities because of storage and transportation costs and quality differences.
- Basis risk can also arise with financial futures,  as for example when a company hedges its own borrowing cost with the Eurodollar contract.
- Another example of basis risk occurs when hedgers decide to hedge distant obligations with near-term futures. For example,  an oil producer might have an obligation to deliver 100, 000 barrels per month at a fixed price for a year. The natural way to hedge this obligation would be to buy 100, 000 barrels per month,  locking in the price and supply on a month-bymonth basis. This is called a strip hedge
- We engage in a strip hedge when we hedge a stream of obligations by offsetting each individual obligation with a futures contract matching the maturity and quantity of the obligation.
- For the oil producer obligated to deliver every month at a fixed price,  the hedge would entail buying the appropriate quantity each month,  in effect taking a long position in the strip.
- An alternative to a strip hedge is a stack hedge. With a stack hedge,  we enter into futures contracts with a single maturity,  with the number of contracts selected so that changes in the present value of the future obligations are offset by changes in the value of this "stack" of futures contracts.
- In the context of the oil producer with a monthly delivery obligation,  a stack hedge would entail going long 1.2 million barrels using the near-term contract.
- When the near-term contract matures,  we reestablish the stack hedge by going long contracts in the new near month. This process of stacking futures contracts in the near-term contract and rolling over into the new near-term contract is called a stack and roll.
- If the new near-term futures price is below the expiring near-term price (i.e.,  there is backwardation),  rolling is profitable.

There are at least two reasons for using a stack hedge.

- First,  there is often more trading volume and liquidity in near-term contracts. With many commodities,  [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spreads]] widen with maturity. Thus,  a stack hedge may have lower transaction costs than a strip hedge.
- Second,  the manager may wish to speculate on the shape of the forward curve. You might decide that the forward curve looks unusually steep in the early months. If you undertake a stack hedge and the forward curve then flattens,  you will have locked in all your oil at the relatively cheap near-term price,  and implicitly made gains from not having locked in the relatively high strip prices.However,  if the curve becomes steeper,  it is possible to lose.

### HEDGING JET FUEL WITH CRUDE OIL
#### SYNTHETIC FORWARDS IN MARKET-MAKING AND ARBITRAGE
- Jet fuel futures do not exist in the United States,  but firms sometimes hedge jet fuel with crude oil futures along with futures for related petroleum products.
- In order to perform this hedge,  it is necessary to understand the relationship between crude oil and jet fuel prices.
- If we own a quantity of jet fuel and hedge by holding H crude oil futures contracts,  our markto-market profit depends on the change in the jet fuel price and the change in the futures price:$$\left(P_{t}-P_{t-1}\right)+H\left(F_{t-1}\right)\tag{12}$$
	- where$P_t$is the price of jet fuel and$F_t$the crude oil futures price.
- We can estimate H by regressing the change in the jet fuel price (denominated in dollars per gallon) on the change in the crude oil futures price (denominated in dollars per gallon,  which is the barrel price divided by 42). We use the nearest to maturity oil futures contract.

# FINANCIAL FORWARDS AND FUTURES

## 1. ALTERNATIVE WAYS TO BUY A STOCK
- The purchase of a share of XYZ stock has three components: (1) fixing the price,  (2) the buyer making payment to the seller,  and (3) the seller transferring share ownership to the buyer. If we allow for the possibility that payment and physical receipt can occur at different times—say,  time 0 and time T —then once the price is fixed there are four logically possible purchasing arrangements: Payment can occur at time 0 or T,  and physical receipt can occur at time 0 or T
- Outright purchase. The typical way to think about buying stock. You simultaneously pay the stock price in cash and receive ownership of the stock.
- Fully leveraged purchase. A purchase in which you borrow the entire purchase price of the security. Suppose you borrow the share price,  S_{0}{0}{0},  and agree to repay the borrowed amount at time T. If the continuously compounded interest rate is r,  at time T you would owe erT per dollar borrowed,  or S0erT.
- Prepaid forward contract. An arrangement in which you pay for the stock today and receive the stock at an agreed-upon future date0.\1 The difference between a prepaid forward contract and an outright purchase is that with the former,  you receive the stock at time T. We will see that the price you pay is not necessarily the stock price.
- Forward contract. An arrangement in which you both pay for the stock and receive it at time T,  with the time T price specified at time 0.

| Description                | Pay at Time | Receive Security at Time | Payment                    |
|----------------------------|-------------|--------------------------|----------------------------|
| Outright purchase          | 0           | 0                        |$S_0$at time 0        |
| Fully leveraged purchase   |$T$| 0                        |$S_0e^{rT}$at time$T$|
| Prepaid forward contract   | 0           |$T$|?                          |
| Forward contract           |$T$|$T$|?$\times e^{rT}$|

- Four different ways to buy a share of stock that has price$S_0$at time 0. At time 0 you agree to a price,  which is paid either today or at time$T$. The shares are received either at 0 or$T$. The interest rate is$r$.
### CONTINUOUS DIVIDENDS

- For stock indexes containing many stocks,  it is common to model the dividend as being paid continuously at a$S_{0}e^r$that is proportional to the level of the index; i.e.,  the dividend yield (the annualized dividend payment divided by the stock price) is constant.
- This is an approximation,  but in a large stock index there can be dividend payments on a large proportion of days.
- The dividend yield is not likely to be fixed in the short run: When stock prices rise,  the dividend yield falls,  at least temporarily. Nevertheless,  we will assume a constant proportional dividend yield for purposes of this discussion.
- To model a continuous dividend,  suppose that the index price is$S_0$and the annualized daily compounded dividend yield is δ. Then the dollar dividend over 1 day is
	- Daily dividend =$\frac{\delta}{365} \times S_{0}$
- Now suppose that we reinvest dividends in the index. Because of reinvestment,  after T years we will have more shares than we started with. Using continuous compounding to approximate daily compounding,  we get
	- Number of shares =$\left(1+\frac{\delta}{365}\right)^{365 \times T} \approx e^{\delta T}$
- At the end of T years we have approximately$e^{δT}$times the shares we had initially
- Now suppose we wish to invest today in order to have one share at time T.
- We can buy$e^{−δT}$shares today.
- Because of dividend reinvestment,  at time T,  we will have$e^{δT}$more shares than we started with,  so we end up with exactly one share.
- Adjusting the initial quantity in this way in order to offset the effect of income from the asset is called tailing the position. Tailing enables us to offset the effect of continuous dividends.
- Since an investment of$S_{0}e^{−δT}$gives us one share at time T,  this is the time 0 prepaid forward price for delivery at time T:$$F_{0, T}^{p}=S_{0} e^{-\delta T}\tag{4}$$
- where δ is the dividend yield and T the time to maturity of the prepaid forward contract.

#### FORWARD CONTRACTS ON STOCK

- If we know the prepaid forward price,  we can compute the forward price. The difference between a prepaid forward contract and a forward contract is the timing of the payment for the stock,  which is immediate with a prepaid forward but deferred with a forward. Because there is deferral of payment,  the forward contract is initially costless for both the buyer and seller; the premium is zero. Also,  because payment is deferred,  the forward price is just the future value of the prepaid forward price:$$F_{0,  T}=FV\left(F_{0,  T}^{r}\right)\tag{5}$$
- This formula holds for any kind of dividend payment.
- An important special case is that of a continuous dividend. In tS_{0}t case,  equation (5) becomes$$F_{0, 1}=\int_{0} e^{(r-\delta)_{T}}\tag{6}$$
- The r in equation (6) is the yield to maturity for a default-free zero coupon bond with the same time to maturity as the forward contract.
- For each maturity,  there is an interest rate,  r,  such that$e^{−r (T −t)} = P (t,  T)$,  where$P (t,  T)$is the time t price of a zero-coupon bond maturing at time T.
- We can therefore also write equation (6) as the price of the prepaid forward contract divided by the price of a zero-coupon bond:

### DOES THE FORWARD PRICE PREDICT THE FUTURE SPOT PRICE?

- It is common to think that the forward price predicts the future spot price. Equation (9) tells us that the forward price equals the expected future spot price,  but with a discount for the risk premium of the asset. Thus,  the forward price systematically errs in predicting the future stock price. If the asset has a positive risk premium,  the future spot price will on average be greater than the forward price.
- The reason is straightforward. When you buy a stock,  you invest money that has an opportunity cost (it could otherwise have been invested in an interest-earning asset),  and you are acquiring the risk of the stock. On average you expect to earn interest as compensation for the time value of money
- You also expect an additional return as compensation for the risk of the stock—this is the risk premium. Algebraically,  the expected return on a stock is
- When you enter into a forward contract,  there is no investment; hence,  you are not compensated for the time value of money. However,  the forward contract retains the risk of the stock,  so you must be compensated for risk. This means that the forward contract must earn the risk premium. If the risk premium is positive,  then on average you must expect a positive return from the forward contract. The only way this can happen is if the forward price predicts too low a stock price. In other words the forward contract is a biased predictor of the future stock price.
- The forward price is the expected future spot price,  discounted at the risk premium
- This bias does not imply that a forward contract is a good investment. Rather,  it tells us that the risk premium on an asset can be created at zero cost and hence has a zero value. Though this seems surprising,  it is a result from elementary finance that if we buy any asset and borrow the full amount of its cost—a transaction that requires no investment—then we earn the risk premium on the asset. Since a forward contract has the risk of a fully leveraged investment in the asset,  it earns the risk premium. This proposition is true in general,  not just for the example of a forward on a non-dividend-paying stock.

### CREATING A SYNTHETIC FORWARD CONTRACT

- A market-maker or arbitrageur must be able to offset the risk of a forward contract. It is possible to do this by creating a synthetic forward contract to offset a position in the actual forward contract.
- In this discussion we will assume that dividends are continuous and paid at the rate δ,  and hence that equation (6) is the appropriate forward price
- We can then create a synthetic long forward contract by buying the stock and borrowing to fund the position. To see how the synthetic position works,  recall that the payoff at expiration for a long forward position on the index is$$\text{Payoff at expiration}=S_T −F_{0, T}$$
- In order to obtain this same payoff,  we buy a tailed position in the stock,  investing S0e−δT. This gives us one share at time T. We borrow this amount so that we are not required to pay anything additional at time 0. At time T we must repay S0e(r−δ)T and we sell the stock for ST. Table 3 demonstrates that borrowing to buy the stock replicates the expiration payoff to a forward contract.
- Just as we can use the stock and borrowing to synthetically create a forward,  we can also use the forward to create synthetic stocks and bonds.
- Table 4 demonstrates that we can go long a forward contract and lend the present value of the forward price to synthetically create the stock. The expiration payoff in this table assumes that equation (6) holds. Table 5 demonstrates that if we buy the stock and short the forward,  we create cash flows like those of a risk-free bond. The rate of return on this synthetic bond—the construction of which is summarized in Table 5—is called the implied repo rate.
- To summarize,  we have shown that
- Forward = Stock − zero-coupon bond
- We can rearrange this equation to derive other synthetic equivalents
- Stock = Forward + zero-coupon bond Zero-coupon bond = Stock − forward
- All of these synthetic positions can be reversed to create synthetic short positions

# CURRENCY CONTRACTS

Currency futures and forwards are widely used to hedge against changes in exchange rates.

# CURRENCY PREPAID FORWARD

Suppose that 1 year from today you want to have ¥1. A prepaid forward allows you to pay dollars today to acquire ¥1 in 1 year. What is the prepaid forward price? Suppose the yen-denominated interest rate is$r_y$and the exchange rate today (\$/¥) is$x_0$. We can work backward. If we want ¥1 in 1 year,  we must have$e^{-r_y}$in yen today. To obtain that many yen today,  we must exchange$x_0 e^{-r_y}$dollars into yen.

Thus,  the prepaid forward price for a yen is$$FP = x_0 e^{-r_y T}\tag{17}$$

where T is time to maturity of the forward

The economic principle governing the pricing of a prepaid forward on currency is the same as that for a prepaid forward on stock. By deferring delivery of the underlying asset,  you lose income. In the case of currency,  if you received the currency immediately,  you could buy a bond denominated in that currency and earn interest. The prepaid forward price reflects the loss of interest from deferring delivery,  just as the prepaid forward price for stock reflects the loss of dividend income

# CURRENCY FORWARD

The prepaid forward price is the dollar cost of obtaining 1 yen in the future. Thus,  to obtain the forward price,  compute the future value using the dollar-denominated interest rate,  r:$$F_{0, T} = x_0 e^{(r-r_y)T}\tag{18}$$

The forward currency rate will exceed the current exchange rate when the domestic risk-free rate is higher than the foreign risk-free rate

The interest rate difference$r - r_y$is the cost of carry for a foreign currency (we borrow at the domestic rate r and invest the proceeds in a foreign money-market instrument,  earning the foreign rate$r_y$as an offset to our cost). If we wish to borrow foreign currency, $r_y$is the lease rate.

# COVERED INTEREST ARBITRAGE

We can synthetically create a forward contract by borrowing in one currency and lending in the other. If we want to have 1 yen in the future,  with the dollar price fixed today,  we can pay today for the yen,  and borrow in dollars to do so. To have 1 yen in 1 year,  we need to invest$x_0 e^{-r_y T}$in dollars,  and we obtain this amount by borrowing. 

The required dollar repayment is$x_0 e^{(r-r_y)T}$which is the forward exchange rate.

The example shows that borrowing in one currency and lending in another creates the same cash flow as a forward contract. If we offset this borrowing and lending position with an actual forward contract,  the resulting transaction is called covered interest arbitrage.

- Synthetically creating a yen forward contract by borrowing in dollars and lending in yen. The payoff at time 1 is ¥1 −$0.009367.

A carry trade entails borrowing in the currency with low interest rates and lending in the currency with high interest rates,  without hedging.

To summarize,  a forward exchange rate reflects the difference in interest rates denominated in different currencies. Imagine that you want to invest$1 for 1 year. You can do so by buying a dollar-denominated bond,  or you can exchange the dollar into another currency and buy a bond denominated in that other currency. You can then use currency forwards to guarantee the exchange rate at which you will convert the foreign currency back into dollars. The principle behind the pricing of currency forwards is that a position in foreign risk-free bonds,  with the currency risk hedged,  pays the same return as domestic risk-free bonds.

# EURODOLLAR FUTURES

The Eurodollar contract,  described in Figure 4,  is based on a$1 million 3-month deposit earning [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] (the London Interbank Offer Rate),  which is the average borrowing rate faced by large international London banks. The 1-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] contract is similar. Suppose that current [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is 1.5% over 3 months. By convention,  this is annualized by multiplying by 4,  so the quoted [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rate is 6%. Assuming a bank borrows$1 million for  3 months,  a change in annualized [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] of 0.01% (1 basis point) would raise its borrowing cost by 0.0001/4 ×$1 million =$25

The Eurodollar futures price at expiration of the contract is 100 − Annualized 3-month LIBOR

Thus,  if [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is 6% at maturity of the Eurodollar futures contract,  the final futures price will be 100 − 6 = 94. It is important to understand that the Eurodollar contract settles based on current LIBOR,  which is the interest rate quoted for the next 3 months. Thus,  for example,  the price of the contract that expires in June reflects the 3-month interest rate between June and September. With the futures contract,  as with a$1 million [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] deposit,  a change of 0.01% in the rate is worth$25.

> Specifications for the Eurodollar futures contract

Like most money-market interest rates,  [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is quoted assuming a 360-day year. Thus,  the annualized 91-day rate, $r_{91}$,  can be extracted from the futures price,  F,  by computing the 90-day rate and multiplying by 91/90. The quarterly effective rate is then computed by dividing the result by 4:$$r_{91} = (100-F) \times \frac{1}{100} \times \frac{1}{4} \times \frac{91}{90}\tag{19}$$

Three-month Eurodollar contracts have maturities out to 10 years,  which means that it is possible to use the contract to lock in a 3-month rate as far as 10 years in the future.

If the Eurodollar futures contract maturing 60 months from today has a price of 95.25,  this means that the contract can be used to lock in an annualized rate of 4.75% for a period beginning 60 months from today and terminating 63 months from today.

The Eurodollar futures strip (the set of futures prices with different maturities at one point in time) provides basic interest rate information that is commonly used to price other futures contracts and to price swaps.

Figure 5 depicts the Eurodollar strip for four dates. Each point on the graph is the annualized 3-month interest rate implied by the Eurodollar futures price maturing that many months in the future.

Let's see how the Eurodollar contract can be used to hedge interest rate risk. For a borrower,  for example,  a short position in the contract is a hedge because it pays when the interest rate rises and requires payment when the interest rate falls. 

To see this,  suppose that 7 months from today we plan to borrow$1 million for 90 days,  and that our borrowing rate is the same as LIBOR. The Eurodollar futures price for 7 months from today is 94; this implies a 90-day rate of (100 − 94) × 90/360 × 1/100 = 1.5%. Now suppose that 7 months hence,  3-month [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is 8%,  which implies a Eurodollar futures price of 92. The implied 90-day rate is 2%. Our extra borrowing expense over 90 days on$1 million will therefore be (0.02 − 0.015) ×$1m =$5000.

This extra borrowing expense is offset by gains on the short Eurodollar contract. The Eurodollar futures price has gone down,  giving us a gain of$25 per basis point,  or$25 × 100 × (94 − 92) =$5000.

The short position in the futures contract compensates us for the increase in our borrowing cost0.\1 In the same way,  a long position can be used to lock in a lending rate.

The Eurodollar futures price is a construct,  not the price of an asset. In this sense Eurodollar futures are different from the futures contracts we have already discussed. Although Eurodollar [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is closely related to a number of other interest rates,  there is no one specific identifiable asset that underlies the Eurodollar futures contract

[[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is quoted in currencies other than dollars,  and comparable rates are quoted in different locations. In addition to LIBOR,  there are PIBOR (Paris),  TIBOR (Tokyo),  and Euribor (the European Banking Federation).

Finally,  you might be wondering why we are discussing [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] rather than rates on Treasury bills. Business and bank borrowing rates move more in tandem with [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] than with the government's borrowing rate. Thus,  these borrowers use the Eurodollar futures contract to hedge. [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is also a better measure of the cost of funds for a market-maker,  so [[A Guide to the Front End and Basis Swap Markets#London Interbank Offered Rate (LIBOR)|LIBOR]] is typically used to price forward contracts.

It might occur to you that the Eurodollar contract pays us at the time we borrow,  but we do not pay interest until the loan matures,  91 days hence. Since we have time to earn interest on the change in the value of the contract,  the hedge ratio should be less than 1 contract per \$1 million borrowing.

### CHAPTER SUMMARY

- The purchase of a stock or other asset entails agreeing to a price,  making payment,  and taking delivery of the asset. 
- A forward contract fixes the price today,  but payment and delivery are deferred. 

-The pricing of forward contracts reflects the costs and benefits of this deferred payment and delivery. 

-The seller receives payment later,  so the price is higher to reflect interest owed the seller,  and the buyer receives possession later,  so the price is lower to reflect dividends not received by the buyer. 

-A prepaid forward contract requires payment today; hence,  it separates these two effects. 

-The price of a prepaid forward is$$\text{Prepaid forward price} =S_{0} e^{-\delta T}$$

- The prepaid forward price is below the asset spot price, $S_0$,  due to dividends forgone by deferring delivery. 
- The forward price also reflects deferral of payment,  so it is the future value of the prepaid forward price:$$\text{Forward price} =S_{0} e^{(r-\delta) T}$$
- In the case of a currency forward,  the dividend yield forgone by holding the forward contract instead of the underlying asset,  δ,  is the interest rate you could earn by investing in foreigncurrency denominated assets. 
- Thus,  for currencies, $δ = r_f$,  where$r_f$is the foreign interest rate.
- A forward contract is equivalent to a leveraged position in an asset—borrowing to buy the asset. By combining the forward contract with other assets it is possible to create synthetic stocks and bonds.
- Since a forward contract is risky but requires no investment,  it earns the risk premium. The forward price is therefore a biased predictor of the future spot price of the asset,  with the bias equal to the risk premium.
- The fact that it is possible to create a synthetic forward has two important implications. 
- First,  if the forward contract is mispriced,  arbitrageurs can take offsetting positions in the forward contract and the synthetic forward contract—in effect buying low and selling high— and make a risk-free profit
- Second,  dealers who make markets in the forward or in the underlying asset can hedge the risk of their position with a synthetic offsetting position. With transaction costs there is a no-arbitrage region rather than a single no-arbitrage price.
- Futures contracts are similar to forward contracts,  except that with futures there are [[Lecture 6-Leverage, Tail Risk, Volatility Products#6.1.3 Margin requirements|margin requirements]] and daily settlement of the gain or loss on the position.