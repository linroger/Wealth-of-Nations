---
tags:
  - '#arbitrage_free_pricing'
  - '#fra_pricing'
  - '#heath_jarrow_morton_model'
  - '#hjm_model'
  - '#interest_rate_derivatives'
  - '#interest_rate_risk_factors'
  - '#notional_value'
  - '#swap_valuation'
  - '#term_structure_modeling'
---
# 26.4 RECAP AND PREVIEW

In this chapter, we looked at interest rate derivatives, which are different from the derivatives on assets that we have previously covered. An interest rate is not an asset and, therefore, cannot be owned. Nonetheless, the payoff functions of interest rate derivatives can be replicated. Hence, these derivatives can be priced by arbitrage. We showed that pricing FRAs and swaps is relatively simple, at least in comparison to pricing options in that they can be replicated in a static, rather than dynamic, manner.

In Chapter 27, we show how an arbitrage-free model of the term structure can be built. It will then form the basis for pricing derivatives on these interest rates that will prohibit arbitrage.

# QUESTIONS AND PROBLEMS

1  Suppose you are quoted loan rates of. $3\%$ for both 270-day and 360-day maturities. Compute the 90-day FRA fixed rate based on this information.
2 Using the same information as in the previous problem, assume now that 90 days have passed but interest rates have not changed. Specifically, you are quoted loan rates of $3\%$ for both the 180-day and 270-day maturities. Compute the receive-floating FRA value assuming a 1,000,000 notional.
3 Suppose you are quoted $4\%$ for the 270-day rate and $3\%$ for the 360-day rate. Compute the 90-day FRA fixed rate based on this information. Assuming a trader entered this receive-floating FRA with 1,000,o00 notional. Now assume 90 days have passed and the 180-day rate is $3\%$ and the 270-day rate is $4\%$ . Compute the value of this FRA assuming all rates are quoted on an add-on interest basis on a 360-day year..

4 Suppose you are provided the following information regarding loan spot rates.. Compute the equilibrium swap rate based on discount factors as well as forward rates.

<html><body><table><tr><td>Days</td><td>Spot Rate (%)</td></tr><tr><td>90</td><td>2.0</td></tr><tr><td>180</td><td>5.0</td></tr><tr><td>270</td><td>3.0</td></tr><tr><td>360</td><td>4.0</td></tr></table></body></html>

5 The following table provides three sets of forward rates each with an average forward rate of $3.5\%$ . Compute the equilibrium swap rates by both methods (discount factors. and weighted average of forward rates). Explain your results..

<html><body><table><tr><td rowspan="2"></td><td colspan="2">Forward Rate (%)</td></tr><tr><td>Flat</td><td>Upward Downward</td></tr><tr><td>1</td><td>3.5</td><td>2.0 5.0</td></tr><tr><td>2</td><td>3.5</td><td>3.0 4.0</td></tr><tr><td>3</td><td>3.5</td><td>4.0 3.0</td></tr><tr><td>4</td><td>3.5</td><td>5.0 2.0</td></tr></table></body></html>

# NOTES

1. Alternatively, you can think of an asset the way accountants think of assets: as "things" that belong on the left-hand side of the balance sheet wherein the cost of acquiring these "things" is funded by either equity or debt, which comprise the right-hand side of the balance sheet..

2. All contracts are designated as having a certain underlying amount, called the notional. For example, if the notional were 10 million, the above amount would be multiplied by 10 million.. The FRA would be a contract to pay the agreed-on fixed rate of interest and receive the underlying LIBOR interest on 10 million notional. There is no exchange of the 10 million. Only the interest payments are exchanged. In our examples, we are effectively assuming a 1.0 notional.
3. That is, we multiplied by the factor $1+L_{m}(q)(q/360)$ to reflect rolling over the payoff at the rate $L_{m}(q)$
4. This point is no different from the fact that if we had a liquid asset, such as stock, and wanted to know what it was worth, we would simply look up its current price in the market. We do not. have to actually sell the asset. We just need to know the price at which we could sell it.
5. There are also swaps based on currencies, commodity prices, stock prices, and stock indexes, but we do not cover these other swaps in this book..
6. As with FRAs, the example here assumes 1.0 notional. In a real swap, where the notional is more. than 1.0, the payments would be multiplied by whatever is the notional. Further, in practice, the. accrual period and related day-count methods influence the pricing and valuation of FRAs. For our purposes here, we simply assume 30 days in a month and 360 days in a year..

7. Recall that we added a 1.0 hypothetical notional when valuing FRAs.

8. The word notional means in name only, but here we prepend the word hypothetical, which would seem to be unnecessary because these notionals are obviously not exchanged. In currency swaps however, the parties can exchange nonequivalent notionals, meaning, the notionals are not hypothetical.
9. Technically, this is not a requirement. The exercise rates could be set such that the floor generates more than enough value to result in a net cash inflow from selling the floor at a greater price than buying the cap. Or the exercise rates could be set such that the cap costs more than the floor, resulting in a net cash outflow. These cases are not common, however, and the cap and floor strikes are usually set so that the cap and floor prices are equal. Sometimes this transaction is called a zero-cost collar, but most collars are of the zero-cost type.

# Fitting an Arbitrage-Free Term Structure Model

0m of the mos significant discoverie in modern finance recarch is the Heath-Jarrowst rate derivatives as well as interest rate products in general. The Heath-Jarrow-Morton. (1992) model, or HJM as it is commonly known, stands at the head of a family tree of. models that take the initial term structure as given, affix the conditions required to preclude arbitrage, and produce trading strategies that lead to the valuation of all interest-dependent claims. Hence, it is in the spirit of the Black-Scholes-Merton model, which takes the price of the underlying and volatility as given and derives the arbitrage-free condition that produces the price of the option.

The HJM model is somewhat similar to a predecessor model by Ho and Lee (HL) (1986). Both models are partial equilibrium models. There are some general equilibrium models of the term structure, such as Vasicek (1977) and Cox-Ingersoll-Ross (1985). Those models derive market equilibrium conditions leading to the prices of fixed-income securities, but they do not fit the current term structure. Hence, they can admit arbitrage if used in extant markets. By accommodating the existing term structure, HJM, as well as HL, can be used in real markets to actually trade. There are a handful of other models, such as in Black, Derman, and Toy (1990), Black and Karasinski (1991), and Brace, Gatarek, and Musiela (1997), that you can, and should, study if you want to become proficient in this. subject, but we shall focus on HJM, because it is probably the most well-known, and it is relatively easy to implement assuming a single risk factor for the entire term structure.

What sets HJM apart from HL is the fact that the former admits a wide range of. structures for the sources driving interest rates. We should think of an interest rate as being. driven by one or more "factors," which are sources of noise or uncertainty. Although HL is a one-factor model, HJM can accommodate any finite number of factors, though with each factor there is a considerable increase in complexity and practicality. In addition, HJM admits an extremely flexible structure for the volatilities of the various interest rates. On the downside, many common versions of HJM are non-Markovian, meaning that they are path. dependent, which increases the computational complexity. Also, because the distribution. of interest rates is assumed to be normal, HJM models can theoretically allow negative interest rates, although that occurrence would not be common.1.
