# 5.14  FUTURES PRICES AND EXPECTED FUTURE SPOT PRICES  

We refer to the market's average opinion about what the spot price of an asset will be at a certain future time as the expected spot price of the asset at that time. Suppose that it is now June and the September futures price of corn is 450 cents. It is interesting to ask what the expected spot price of corn in September is. Is it less than 450 cents, greater than 450 cents, or exactly equal to 450 cents? As illustrated in Figure 2.1, the futures price converges to the spot price at maturity. If the expected spot price is less than 450 cents, the market must be expecting the September futures price to decline, so that traders with short positions gain and traders with long positions lose. If the expected spot price is greater than 450 cents, the reverse must be true. The market must be expecting the September futures price to increase, so that traders with long positions gain while those with short positions lose..  

# Keynes and Hicks  

Economists John Maynard Keynes and John Hicks argued that, if hedgers tend to hold short positions and speculators tend to hold long positions, the futures price of an asset will be below the expected spot price. This is because speculators require compensation for the risks they are bearing. They will trade only if they can expect to make money on average. Hedgers will lose money on average, but they are likely to be prepared to accept this because the futures contract reduces their risks. If hedgers tend to hold long positions while speculators hold short positions, Keynes and Hicks argued that the futures price will be above the expected spot price for a similar reason.  

# Risk and Return  

The modern approach to explaining the relationship between futures prices and.   
expected spot prices is based on the relationship between risk and expected return in the economy. In general, the higher the risk of an investment, the higher the expected.   
return demanded by an investor. The capital asset pricing model, which is explained in the appendix to Chapter 3, shows that there are two types of risk in the economy:.   
systematic and nonsystematic. Nonsystematic risk should not be important to an.   
investor. It can be almost completely eliminated by holding a well-diversified portfolio.   
An investor should not therefore require a higher expected return for bearing non-.   
systematic risk. Systematic risk, in contrast, cannot be diversified away. It arises from a.   
correlation between returns from the investment and returns from the whole stock.   
market. An investor generally requires a higher expected return than the risk-free.   
interest rate for bearing positive amounts of systematic risk. Also, an investor is.   
prepared to accept a lower expected return than the risk-free interest rate when the.   
systematic risk in an investment is negative..  

# The Risk in a Futures Position  

Let us consider a speculator who takes a long position in a futures contract that lasts for $T$ years in the hope that the spot price of the asset will be above the futures price at the end of the life of the futures contract. We ignore daily settlement and assume that the futures contract can be treated as a forward contract. We suppose that the speculator puts the present value of the futures price into a risk-free investment while simultaneously taking a long futures position. The proceeds of the risk-free investment are used to buy the asset on the delivery date. The asset is then immediately sold for its market price. The cash flows to the speculator are as follows:  

Today: $-F_{0}e^{-r T}$ End of futures contract: $+S_{T}$  

where $F_{0}$ is the futures price today, $S_{T}$ is the price of the asset at time $T$ at the end of the futures contract, and $r$ is the risk-free return on funds invested for time $T$  

How do we value this investment? The discount rate we should use for the expected. cash flow at time $T$ equals an investor's required return on the investment. Suppose that. $k$ is an investor's required return for this investment. The present value of this investment is  

$$
-F_{0}e^{-r T}+E(S_{T})e^{-k T}
$$  

where $E$ denotes expected value. We can assume that all investments in securities markets are priced so that they have zero net present value. This means that  

$$
-F_{0}e^{-r T}+E(S_{T})e^{-k T}=0
$$  

or  

$$
F_{0}=E(S_{T})e^{(r-k)T}
$$  

As we have just discussed, the returns investors require on an investment depend on its systematic risk. The investment we have been considering is in essence an investment in the asset underlying the futures contract. If the returns from this asset are uncorrelated with the stock market, the correct discount rate to use is the risk-free rate $r$ , so we should set $k=r$ Equation (5.20) then gives  

$$
{\cal F}_{0}={\cal E}(S_{T})
$$  

This shows that the futures price is an unbiased estimate of the expected future spot price when the return from the underlying asset is uncorrelated with the stock market.  

If the return from the asset is positively correlated with the stock market, $k>r$ and equation (5.20) leads to $F_{0}<E(S_{T})$ . This shows that, when the asset underlying the futures contract has positive systematic risk, we should expect the futures price to understate the expected future spot price. An example of an asset that has positive. systematic risk is a stock index. The expected return of investors on the stocks underlying an index is generally more than the risk-free rate, $r.$ The dividends provide a return of. $q$ The expected increase in the index must therefore be more than $r-q$ . Equation (5.8) is therefore consistent with the prediction that the futures price understates the expected future stock price for a stock index.  

If the return from the asset is negatively correlated with the stock market, $k<r$ and equation (5.20) gives $F_{0}>E(S_{T})$ . This shows that, when the asset underlying the futures contract has negative systematic risk, we should expect the futures price to overstate the expected future spot price.  

These results are summarized in Table 5.5.  

Table 5.5 Relationship between futures price and expected future spot price.   


<html><body><table><tr><td>Underlyingasset</td><td>Relationshipofexpected returnkfromasset torisk-freerater</td><td>Relationshipoffutures priceFtoexpected future spot price E(ST)</td></tr><tr><td>No systematic risk</td><td>k=r</td><td>Fo = E(Sr)</td></tr><tr><td>Positive systematic risk</td><td>k>r</td><td>Fo < E(ST)</td></tr><tr><td>Negative systematic risk</td><td>k<r</td><td>Fo > E(Sr)</td></tr></table></body></html>  

# Normal Backwardation and Contango  

When the futures price is below the expected future spot price, the situation is known as.   
normal backwardation; and when the futures price is above the expected future spot.   
price, the situation is known as contango. However, it should be noted that sometimes.   
these terms are used to refer to whether the futures price is below or above the current spot price, rather than the expected future spot price.  

# SUMMARY  

For most purposes, the futures price of a contract with a certain delivery date can be considered to be the same as the forward price for a contract with the same delivery date. It can be shown that in theory the two should be exactly the same when interest rates are perfectly predictable.  

For the purposes of understanding futures (or forward) prices, it is convenient to divide futures contracts into two categories: those in which the underlying asset is held for investment by at least some traders and those in which the underlying asset is held primarily for consumption purposes.  

In the case of investment assets, we have considered three different situations:  

1. The asset provides no income.   
2. The asset provides a known dollar income.   
3. The asset provides a known yield.  

The results are summarized in Table 5.6. They enable futures prices to be obtained for contracts on stock indices, currencies, gold, and silver. Storage costs can be treated as negative income.  

In the case of consumption assets, it is not possible to obtain the futures price as a function of the spot price and other observable variables. Here the parameter known as the asset's convenience yield becomes important. It measures the extent to which users of the commodity feel that ownership of the physical asset provides benefits that are not obtained by the holders of the futures contract. These benefits may include the ability to profit from temporary local shortages or the ability to keep a production process running. We can obtain an upper bound for the futures price of consumption assets using arbitrage arguments, but we cannot nail down an equality relationship between futures and spot prices.  

Table 5.6  Summary of results for a contract with time to maturity $T$ on an investmen1 asset with price $S_{0}$ when the risk-free interest rate for a $T$ -year period is $r$   


<html><body><table><tr><td>Asset</td><td>Forward/futures price</td><td>Valueoflongforwardcontract with delivery priceK</td></tr><tr><td>Provides no income:</td><td>SoerT</td><td>So - Ke-rT</td></tr><tr><td>Providesknownincome</td><td></td><td></td></tr><tr><td>with present value I:</td><td>(So - I)erT</td><td>So - I - Ke-rT</td></tr><tr><td>Provides known yield q:</td><td>Soe(r-q)T</td><td>Soe-qT - Ke-rT</td></tr></table></body></html>  

The concept of cost of carry is sometimes useful. The cost of carry is the storage cost of the underlying asset plus the cost of financing it minus the income received from it. In the case of investment assets, the futures price is greater than the spot price by an amount reflecting the cost of carry. In the case of consumption assets, the futures price is greater than the spot price by an amount reflecting the cost of carry net of the convenience yield.  

If we assume the capital asset pricing model is true, the relationship between the futures price and the expected future spot price depends on whether the return on the asset is positively or negatively correlated with the return on the stock market. Positive correlation will tend to lead to a futures price lower than the expected future spot price, whereas negative correlation will tend to lead to a futures price higher than the expected future spot price. Only when the correlation is zero will the theoretical futures price be equal to the expected future spot price.  

# FURTHER READING  

Cox, J. C., J. E. Ingersoll, and S. A. Ross. "The Relation between Forward Prices and Futures Prices,' Journal of Financial Economics, 9 (December 1981): 321-46.   
Jarrow, R. A., and G. S. Oldfield. "Forward Contracts and Futures Contracts,' Journal of Financial Economics, 9 (December 1981): 373-82.   
Richard, S., and S. Sundaresan. "A Continuous-Time Model of Forward and Futures Prices in a Multigood Economy,' Journal of Financial Economics, 9 (December 1981): 347-72.   
Routledge, B. R., D. J. Seppi, and C. S. Spatt. "Equilibrium Forward Curves for Commodities, Journal of Finance, 55, 3 (2000) 1297-1338.  

# Short Concept Questions  

5.1. What is the difference between an investment asset and a consumption asset?   
5.2. Explain what happens when an investor shorts a certain stock..   
5.3. What is the formula for the forward price of an investment asset that provides no income?   
5.4. What is the formula for the forward price of an investment asset that provides a known dollar income?   
5.5. What is the difference between a known yield and a known dollar income?   
5.6. What is meant by index arbitrage?.   
5.7. What is the formula for the value of a forward contract in terms of the forward price?   
5.8. What is the formula for a forward exchange rate in terms of the spot exchange rate?   
5.9. Explain the meaning of cost of carry and convenience yield. What is the relationship between futures price, spot price, convenience yield, and cost of carry?.   
5.10. Under what circumstances is the futures price greater than the expected future spot price according to (a) Keynes and Hicks and (b) systematic risk considerations?  

# Practice Questions  

5.11. What is the difference between the forward price and the value of a forward contract?  

5.12. Suppose that you enter into a 6-month forward contract on a non-dividend-paying stock when the stock price is $\$30$ and the risk-free interest rate (with continuous compounding). is $5\%$ per annum. What is the forward price?.  

5.13. A stock index currently stands at 350. The risk-free interest rate is $4\%$ per annum (with continuous compounding) and the dividend yield on the index is $3\%$ per annum. What should the futures price for a 4-month contract be?  

5.14. Explain carefully why the futures price of gold can be calculated from its spot price and other observable variables whereas the futures price of copper cannot.  

5.15. Explain why a foreign currency can be treated as an asset providing a known yield.   
5.16. Is the futures price of a stock index greater than or less than the expected future value of the index? Explain your answer.   
5.17. A 1-year long forward contract on a non-dividend-paying stock is entered into when the stock price is $\$40$ and the risk-free rate of interest is $5\%$ per annum with continuous compounding. (a) What are the forward price and the initial value of the forward contract? (b) Six months later, the price of the stock is $\$45$ and the risk-free interest rate is still $5\%$ What are the forward price and the value of the forward contract?   
5.18. The risk-free rate of interest is $7\%$ per annum with continuous compounding, and the. dividend yield on a stock index is $3.2\%$ per annum. The current value of the index is 150. What is the 6-month futures price?   
5.19. Assume that the risk-free interest rate is $4\%$ per annum with continuous compounding and that the dividend yield on a stock index varies throughout the year. In February, May, August, and November, dividends are paid at a rate of $5\%$ per annum. In other months, dividends are paid at a rate of $2\%$ per annum. Suppose that the value of the index on July 31 is 1,300. What is the futures price for a contract deliverable in December 31 of the same year?   
5.20. Suppose that the risk-free interest rate is $6\%$ per annum with continuous compounding and that the dividend yield on a stock index is. $4\%$ per annum. The index is standing at. 400, and the futures price for a contract deliverable in four months is 405. What arbitrage opportunities does this create?   
5.21. Estimate the difference between short-term interest rates in Japan and the United States on May 21, 2020, from the information in Table 5.4..   
5.22. The 2-month interest rates in Switzerland and the United States are, respectively, $1\%$ and $2\%$ per annum with continuous compounding. The spot price of the Swiss franc is. $\$1.0500$ . The futures price for a contract deliverable in 2 months is $\$1.0500$ .What arbitrage opportunities does this create?.   
5.23. The spot price of silver is $\$25$ per ounce. The storage costs are $\$0.24$ per ounce per year payable quarterly in advance. Assuming that interest rates are $5\%$ per annum for all maturities, calculate the futures price of silver for delivery in 9 months.   
5.24. Suppose that $F_{1}$ and $F_{2}$ are two futures contracts on the same commodity with times to maturity, $t_{1}$ and $t_{2}$ , where $t_{2}>t_{1}$ . Prove that $F_{2}\leq F_{1}e^{r(t_{2}-t_{1})}$ , where $r$ is the interest rate  

(assumed constant) and there are no storage costs. For the purposes of this problem, assume that a futures contract is the same as a forward contract.  

5.25. When a known future cash outflow in a foreign currency is hedged by a company using a. forward contract, there is no foreign exchange risk. When it is hedged using futures contracts, the daily settlement process does leave the company exposed to some risk.. Explain the nature of this risk. In particular, consider whether the company is better off. using a futures contract or a forward contract when:.  

(a) The value of the foreign currency falls rapidly during the life of the contract..   
(b) The value of the foreign currency rises rapidly during the life of the contract.. (c) The value of the foreign currency first rises and then falls back to its initial value. (d) The value of the foreign currency first falls and then rises back to its initial value. Assume that the forward price equals the futures price.   
5.26. It is sometimes argued that a forward exchange rate is an unbiased predictor of future exchange rates. Under what circumstances is this so?   
5.27. Show that the growth rate in an index futures price equals the excess return on the portfolio underlying the index over the risk-free rate. Assume that the risk-free interest rate and the dividend yield are constant.   
5.28. Explain carefully what is meant by the expected price of a commodity on a particular future date. Suppose that the futures price for crude oil declines with the maturity of the. contract at the rate of $2\%$ per year. Assume that speculators tend to be short crude oil futures and hedgers tend to be long. What does the Keynes and Hicks argument imply about the expected future price of oil?   
5.29. The Value Line Index is designed to reflect changes in the value of a portfolio of over 1,600 equally weighted stocks. Prior to March 9, 1988, the change in the index from one day to the next was calculated as the geometric average of the changes in the prices of the stocks underlying the index. In these circumstances, does equation (5.8) correctly relate the futures price of the index to its cash price? If not, does the equation overstate or understate the futures price?   
5.30. A U.S. company is interested in using the futures contracts traded by the CME Group to hedge its Australian dollar exposure. Define. $r$ as the interest rate (all maturities) on the U.S. dollar and $r_{f}$ as the interest rate (all maturities) on the Australian dollar. Assume that $r$ and $r_{f}$ are constant and that the company uses a contract expiring at time. $T$ to hedge an exposure at time $t\left(T>t\right)$ (a) Show that the optimal hedge ratio is $e^{(r_{f}-r)(T-t)}$ , ignoring daily settlement. (b) Show that, when. $t$ is 1 day, the optimal hedge ratio is almost exactly. $S_{0}/F_{0}$ , where $S_{0}$ is the current spot price of the currency and. $F_{0}$ is the current futures price of the currency for the contract maturing at time $T$ (c) Show that the company can take account of the daily settlement of futures contracts for a hedge that lasts longer than 1 day by adjusting the hedge ratio so that it always equals the spot price of the currency divided by the futures price of the currency..  

5.31. What is the cost of carry for:  

(a) a non-dividend-paying stock. (b) a stock index   
(c) a commodity with storage costs (d) a foreign currency..   
5.32. The spot exchange rate between the Swiss franc and U.S. dollar is 1.0404 ( $\S$ per franc). Interest rates in the United States and Switzerland are $0.25\%$ and $0\%$ per annum, respectively, with continuous compounding. The 3-month forward exchange rate was 1.0300 ( $\S$ per franc). What arbitrage strategy was possible? How does your answer change if the forward exchange rate is 1.0500 $\S$ per franc).   
5.33. An index is 1,200. The three-month risk-free rate is. $3\%$ per annum and the dividend yield. over the next three months is. $1.2\%$ per annum. The six-month risk-free rate is $3.5\%$ per annum and the dividend yield over the next six months is $1\%$ per annum. Estimate the. futures price of the index for three-month and six-month contracts. All interest rates and dividend yields are continuously compounded.   
5.34. Suppose the current USD/euro exchange rate is 1.2000 dollar per euro. The six-month forward exchange rate is 1.1950. The six-month USD interest rate is $1\%$ per annum continuously compounded. Estimate the six-month euro interest rate.   
5.35. The spot price of oil is $\$50$ per barrel and the cost of storing a barrel of oil for one year is $\$3$ payable at the end of the year. The risk-free interest rate is $5\%$ per annum continuously compounded. What is an upper bound for the one-year futures price of oil?   
5.36. A company that is uncertain about the exact date when it will pay or receive a foreign currency may try to negotiate with its bank a forward contract that specifies a period during which delivery can be made. The company wants to reserve the right to choose the exact delivery date to fit in with its own cash flows. Put yourself in the position of the bank. How would you price the product that the company wants?.   
5.37. A company enters into a forward contract with a bank to sell a foreign currency for $K_{1}$ at time $T_{1}$ . The exchange rate at time $T_{1}$ proves to be $S_{1}$ $(>K_{1})$ . The company asks the bank if it can roll the contract forward until time $T_{2}\left(>T_{1}\right)$ rather than settle at time $T_{1}$ . The bank agrees to a new delivery price,. $K_{2}$ . Explain how $K_{2}$ should be calculated.  

![](images/7722cd44af2c45dc5cd612c264bfc1ec309c0fbb2bf9b11e7a8597910490bb85.jpg)  

# Interest Rate Futures  

So far we have covered futures contracts on commodities, stock indices, and foreign currencies. We have seen how they work, how they are used for hedging, and how futures prices are determined. We now move on to consider interest rate futures.  

This chapter explains the contracts that trade in the United States. Many of the other interest rate futures contracts throughout the world have been modeled on these contracts. The chapter also shows how interest rate futures contracts, when used in conjunction with the duration measure introduced in Chapter 4, can be used to hedge a company's exposure to interest rate movements.  
