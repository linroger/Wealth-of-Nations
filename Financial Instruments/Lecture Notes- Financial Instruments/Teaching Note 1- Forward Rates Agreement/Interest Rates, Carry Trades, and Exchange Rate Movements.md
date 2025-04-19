---
title: Interest Rates,  Carry Trades,  and Exchange Rate Movements
tags:
  - carry_trade
  - currency_markets
  - exchange_rates
  - interest_rate_differentials
  - interest_rates
aliases:
  - Carry Trade Strategy
  - Exchange Rate Swings
key_concepts:
  - Carry trade strategy
  - Covered interest parity
  - Forward exchange rate
  - Funding currency
  - Interest rate differentials
---

# Interest Rates, Carry Trades, and Exchange Rate Movements

Federal Reserve Bank of San Francisco
[[https://www.frbsf.org/economic-research/publications/economic-letter/2006/november/interest-rates-carry-trades-and-exchange-rate-movements/]]

- [What is the carry trade?](https://www.frbsf.org/economic-research/publications/economic-letter/2006/november/interest-rates-carry-trades-and-exchange-rate-movements/#sub1)
- [Not profitable in theory,  but profitable in practice](https://www.frbsf.org/economic-research/publications/economic-letter/2006/november/interest-rates-carry-trades-and-exchange-rate-movements/#sub2)
- [Carry trade profits and exchange rate swings](https://www.frbsf.org/economic-research/publications/economic-letter/2006/november/interest-rates-carry-trades-and-exchange-rate-movements/#sub3)
- [How big is the carry trade?](https://www.frbsf.org/economic-research/publications/economic-letter/2006/november/interest-rates-carry-trades-and-exchange-rate-movements/#sub4)
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

---

The U.S. dollar has seen some remarkable swings against major currencies recently. For example,  over most of 2005,  it gained nearly 18% against the yen and 13% against the euro,  while between March and May 2006,  it depreciated sharply against these currencies,  losing almost 10% of its value. Many observers have related these swings to what is known as the carry trade. This is a strategy widely used by investors in international financial markets that is based on exploiting the existence of interest rate differentials across countries.

The use of this strategy by investors is puzzling,  as the theory of interest parity conditions implies that it should not generate predictable profits. This _Economic Letter_ explores this puzzle by first describing the structure of a carry trade transaction. It then reviews research documenting the payoff properties of carry trades and discusses how these strategies can be linked to the swings in exchange rates observed over recent years. Finally,  it presents some evidence on the size of carry trade strategies.

**What is the carry trade?**

In the most common version of this strategy,  an investor borrows a given amount in a low-interest-rate currency (the “funding” currency),  converts the funds into a high-interest-rate currency (the “target” currency) and lends the resulting amount in the target currency at the higher interest rate.

Another version exploits the forward premium of one currency relative to another. The forward premium is basically the percent difference between the forward exchange rate and the spot exchange rate between two currencies. Specifically,  the forward exchange rate between two currencies indicates the amount of one currency to be delivered at a specific future date that can be bought with a single unit of the other currency,  while the spot exchange rate refers to immediate delivery. This version combines two transactions. The first involves selling currencies that are at a forward premium,  that is,  currencies for which the forward exchange rate is higher than the spot exchange rate. The second involves buying currencies that are at a forward discount,  that is,  currencies for which the forward exchange rate is lower than the spot exchange rate. Thus,  currencies that are at a forward premium are like funding currencies and those that are at a forward discount are like target currencies.

Why is this version equivalent to the one based on interest rate differentials? According to an equilibrium condition of international financial markets,  called “covered interest parity, ” the forward premium of one currency relative to another is equal to the interest rate differential between them. Traders in [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) markets,  in fact,  use this condition to set forward exchange rates and,  thereby,  forward premiums. This implies that currencies with a low interest rate are typically at a forward premium,  whereas currencies with a high interest rate are typically at a forward discount. Therefore,  borrowing in currencies with low interest rates and lending in currencies with high interest rates is equivalent to selling currencies that are at a forward premium and buying currencies that are at a forward discount.

**Not profitable in theory,  but profitable in practice**

According to economic theory,  an investment strategy based on exploiting differences in interest rates across countries should yield no predictable profits. Consider two countries,  one with a high interest rate,  and the other with a low interest rate. According to another equilibrium condition of international financial markets called the “uncovered interest parity, ” the difference in interest rates between the two countries simply reflects the rate at which investors expect the high-interest-rate currency to depreciate against the low-interest-rate currency. When this depreciation occurs,  investors who borrowed a given amount in the low-interest-rate currency and then lent it in the high-interest-rate currency will find that their return is worth less. The uncovered interest parity condition implies,  indeed,  that investors should expect to receive no profits,  as they should expect the return from lending in the high-interest-rate currency to be worth ultimately as much as the cost of borrowing in the low-interest-rate currency.

In practice,  however,  investors in international financial markets do seem able to make profits through such strategies. In fact,  market participants and commentators have often cited the carry trade as the source of several recent exchange rate swings.

Why can carry trades be profitable? If the exchange rate between the funding and the target currencies does not move,  then the profit from the carry trade is proportional to both the interest rate differential and the forward premium between the two currencies. But,  of course,  exchange rates do move,  and,  therefore,  a carry trade involves exchange rate risk,  in particular,  the possibility that the target currency will depreciate against the funding currency. In that case,  the value of the amount initially borrowed in the funding currency will increase in terms of the target currency,  effectively increasing the borrowing cost of the strategy. By the same token,  the higher interest rate obtained by lending in the target currency will be worth less in terms of the funding currency,  ultimately trimming its profitability.

If the carry trade is a risky strategy,  why are investors reported to use it extensively? The answer lies in the “forward premium puzzle.” This is a well-known empirical anomaly of [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) markets,  and it concerns the implications of the forward premium for the realized rate of change in the value of one currency relative to another. Empirical evidence shows that currencies that are at a forward premium and that,  correspondingly,  have a low interest rate,  actually tend,  on average,  to _depreciate_,  not appreciate,  as the theory of interest parity conditions predicts. Similarly,  currencies that are at a forward discount and that,  correspondingly,  have a high interest rate,  tend,  on average,  to _appreciate_,  not depreciate. This anomaly,  then,  implies that an investor who enters a carry trade is quite likely to make predictable profits from two sources: the interest rate differential between two currencies and the appreciation of the high-interest-rate currency that was originally bought at a forward discount.

**Carry trade profits and exchange rate swings**

How large are the profits from carry trade strategies? Work by Burnside et al. (2006) provides one answer to this question. These authors document the return properties of a version of the carry trade that they call an “optimally weighted” carry trade portfolio. Like the earlier example,  it involves selling currencies that are at a forward premium and buying currencies that are at a forward discount. It also entails choosing the weights of the portfolio in order to maximize its Sharpe ratio,  which evaluates the risk-adjusted performance of a portfolio by correcting a measure of its average return with the volatility of its returns. Burnside et al. find that,  for the period from 1977 to 2005,  the realized cumulative return to their strategy is very similar to that of investing in the S&P500 index. The relative attractiveness of their strategy,  however,  lies in the lower volatility of its returns: the Sharpe ratio of their strategy is about one and a half times larger than the Sharpe ratio of the S&P500 index,  implying that the volatility of the returns of their carry trade strategy is only two-thirds of the volatility of the returns of the S&P500 index.

Even though the Sharpe ratio of the optimally weighted carry trade portfolio is relatively high,  transaction costs,  such as [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spreads]],  lower its average payoff significantly,  as they are of the same order of magnitude as the portfolio returns. This implies that,  in order to generate substantial profits,  investors need to roll over the carry trade strategy for prolonged periods.

Changes in supply and demand for currencies prompted by the opportunity to exploit interest rate differentials can,  therefore,  result in sizeable and persistent exchange rate movements. Specifically,  carry trades based on interest rate differentials and forward premiums affect the balance of supply and demand for funding and target currencies in [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) markets. In particular,  as these strategies involve selling short funding currencies and,  at the same time,  buying target currencies,  they induce excess supply of the funding currencies and excess demand for target currencies. In turn,  this leads to the depreciation of low-interest-rate funding currencies and to the appreciation of highinterest-rate target currencies. In addition,  the appreciation of high-interest-rate target currencies can encourage an increasing number of investors to enter this strategy and,  ultimately,  amplify the appreciation of target currencies,  as well as the persistence of exchange rate movements of the currencies involved in these strategies.

The appreciation of the dollar against the yen and the euro that occurred over most of 2005,  for example,  has been related to increasing interest rate differentials. As interest rates rose in the U.S. while remaining at near-zero levels in Japan and at 2% in the euro area,  the dollar looked like an increasingly attractive target currency. In contrast,  in early 2006,  the decline in the dollar has been related to expectations of narrowing interest rate differentials: As investors started to expect rising interest rates in Japan and the euro area,  the attractiveness of using the dollar as a target currency decreased.

**How big is the carry trade?**

The effect of carry trades on exchange rates most likely depends on the magnitude of the international financial transactions and investment positions associated with them. Unfortunately,  evidence on these magnitudes is fairly limited,  in part because these strategies are generally conducted through transactions,  such as [[Financial Instruments/Review Session Notes/Currency Swaps.md|currency swaps]],  that are reported as off-balance-sheet items and,  therefore,  hard to monitor through official statistics.

Two studies from the Bank for International Settlements (BIS),  however,  provide some evidence of the size of carry trade activity and thereby their significance in exchange rate movements. One study concerns [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) market turnover,  which measures the gross value in U.S. dollar equivalents of all transactions involving the exchange of two currencies. Galati and Melvin (2004) argue that the remarkable increase in [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) market turnover between 2001 and 2004 was likely due to a rise in carry trade activities. They note that the increase in turnover was particularly strong for the Australian and the New Zealand dollars,  two currencies with relatively high interest rates that simultaneously had extended periods of appreciation against low-interest-rate currencies,  such as the U.S. dollar and the yen. The authors also illustrated graphically that,  between 2001 and 2004,  as the interest rate differential with the U.S. widened,  the Australian dollar appreciated against the U.S. dollar and [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) turnover increased substantially. Finally,  based on survey data from 1992 to 2004,  they found that,  for major trading currencies,  increases in [Foreign Exchange](Foreign%20Exchange%20Quoting%20Conventions.md) market turnover were strongly related to interest rate differentials with the U.S.

The second study concerns the stock of outstanding BIS reporting banks’ cross-border claims denominated in yen,  a currency that has been popular as a funding currency,  given the long period of very low interest rates in Japan. McGuire and Tarashev (2006) report that the stock of yen-denominated claims rose substantially in the fourth quarter of 2005,  continuing a trend evident since 2004. They argue that this provides some evidence of the increased relevance of yen carry trade positions,  as a large share of the increase in yen-denominated claims has been driven by the increase in yen borrowing by investors in financial centers.

**Conclusions**

Market participants and commentators have often linked the swings in exchange rates over recent years to the use of carry trades,  that is,  investors’ strategies that exploit interest rate differentials across countries. What is puzzling from a theoretical standpoint,  however,  is that investors should even engage in carry trades,  because the textbook theory of interest parity conditions implies that these strategies should yield no predictable profits. As this _Economic Letter_ has explained,  the key to the puzzle is yet another puzzle—the forward premium puzzle—wherein currencies with high or rising interest rates tend to appreciate,  and currencies with low or declining interest rates tend to depreciate,  as investors are lured into buying currencies with positive interest rate differentials and selling short currencies with negative interest rate differentials. The evidence on the quantitative importance of carry trades is fairly limited,  but to date it suggests that these strategies may well have been an important factor in recent exchange rate swings.
