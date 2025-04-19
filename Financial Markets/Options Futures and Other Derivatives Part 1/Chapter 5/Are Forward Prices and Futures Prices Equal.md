---
tags:
  - arbitrage_argument
  - forward_prices
  - futures_contract
  - futures_prices
  - interest_rates
aliases:
  - Forward Price vs Futures Price
  - Forward vs Futures
key_concepts:
  - Arbitrage and interest rates
  - Forward and futures prices
  - Futures contract advantages
  - Interest rate futures exception
---

# 5.8 ARE FORWARD PRICES AND FUTURES PRICES EQUAL?  

Technical Note 24 at www-2.rotman.utoronto.ca/\~hull/TechnicalNotes provides an arbitrage argument to show that, when the short-term risk-free interest rate is constant, the forward price for a contract with a certain delivery date is in theory the same as the futures price for a contract with that delivery date. The argument can be extended to cover situations where the interest rate is a known function of time.  

When interest rates vary unpredictably (as they do in the real world), forward and futures prices are in theory no longer the same. We can get a sense of the nature of the relationship by considering the situation where the price of the underlying asset, $S$ , is strongly positively correlated with interest rates. When $S$ increases, an investor who holds a long futures position makes an immediate gain because of the daily settlement procedure. The positive correlation indicates that it is likely that interest rates have also increased, thereby increasing the rate at which the gain can be invested. Similarly, when $S$ decreases, the investor will incur an immediate loss and it is likely that interest rates. have just decreased, thereby reducing the rate at which the loss has to be financed. The. positive correlation therefore works in the investor's favor. An investor holding a forward contract rather than a futures contract is not affected in this way by interest rate movements. It follows that a long futures contract will be slightly more attractive than a similar long forward contract. Hence, when $S$ is strongly positively correlated with interest rates, futures prices will tend to be slightly higher than forward prices. When $S$ is strongly negatively correlated with interest rates, a similar argument shows that forward prices will tend to be slightly higher than futures prices.  

The theoretical differences between forward and futures prices for contracts that last only a few months are in most circumstances sufficiently small to be ignored. In practice, there are a number of factors not reflected in theoretical models that may. cause forward and futures prices to be different. These include taxes, transactions costs, and margin requirements. The risk that the counterparty will default may be less in the. case of a futures contract because of the role of the exchange clearing house. Also, in some instances, futures contracts are more liquid and easier to trade than forward contracts. Despite all these points, for most purposes it is reasonable to assume that forward and futures prices are the same. This is the assumption we will usually make in this book. We will use the symbol. $F_{0}$ to represent both the futures price and the forward. price of an asset today.  

One exception to the rule that futures and forward contracts can be assumed to be the same concerns interest rate futures. This will be discussed in Section 6.3.  
