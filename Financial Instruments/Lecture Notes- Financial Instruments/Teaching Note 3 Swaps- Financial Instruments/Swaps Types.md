---
tags:
  - commodity_swap
  - forward_contract
  - hedging
  - oil_swap
  - swap
aliases:
  - Commodity Swap Example
  - Swap Contract
key_concepts:
  - Borrowing and lending
  - Exchange of payments
  - Forward contract pricing
  - Hedging risky payments
  - Lock in fixed price
---

**[[Teaching Note 3 SwapsFinancial Instruments]]**
	- [[Forward Rates Agreement]]
	- [[Overnight Index Swaps (OIS)]]
	- [[Swaps Types]]
	- [[Teaching Note 3 SwapsFinancial Instruments]]
	- [[The Value of the Swap Contract after Initiation]]

+ A swap is a contract calling for an exchange of payments over time. One party makes a payment to the other depending upon whether a reference price turns out to be greater or less than a fixed price that is specified in the swap contract. A swap thus provides a means to hedge a stream of risky payments.
+ By entering into an oil swap, for example, an oil buyer confronting a stream of uncertain oil payments can lock in a fixed price for oil over a period of time. The swap payments would be based on the difference between a fixed price for oil and a market price that varies over time.
+ In fact, a forward contract is a single-payment swap. It is possible to price a multi-date swap—determine the fixed price for oil in the above example—by using information from the set of forward prices with different maturities (i.e., the strip). We will see that swaps are nothing more than forward contracts coupled with borrowing and lending money.

## 1. AN EXAMPLE OF A COMMODITY SWAP
+ An industrial producer, IP Inc., is going to buy 100,000 barrels of oil 1 year from today and 2 years from today. Suppose that the forward price for delivery in 1 year is$110/barrel and in 2 years is$111/barrel.
+ IP can use forward contracts to guarantee the cost of buying oil for the next 2 years. Specifically, IP could enter into long forward contracts for 100,000 barrels in each of the next 2 years, committing to pay$110/barrel in 1 year and$111/barrel in 2 years.
+ Alternatively, IP could pay an oil supplier$201.638, and the supplier would commit to delivering one barrel in each of the next 2 years. A single payment today for a single delivery of oil in the future is a prepaid forward. A single payment today to obtain multiple deliveries in the future is a prepaid swap.
+ Although it is possible to enter into a prepaid swap, buyers might worry about the resulting credit risk: They have fully paid for oil that will not be delivered for up to 2 years. For the same reason, the swap counterparty would worry about a postpaid swap, where the oil is delivered and full payment is made after 2 years.
+ A more attractive solution for both parties is to defer payment until the oil is delivered, while still fixing the total price. Typically, a swap will call for equal payments in each year.
+ In this example, 100,000 is the notional amount of the swap, meaning that 100,000 barrels is used to determine the magnitude of the payments when the swap is settled financially.

 ![500](IMG-20240913171226965.png)

Positions and cash flows for a dealer who has an obligation to receive the fixed price in an oil swap and who hedges the exposure by going long year 1 and year 2 oil forwards.

## PHYSICAL VERSUS FINANCIAL SETTLEMENT
+ With financial settlement, the oil buyer pays the swap counterparty the difference between the fixed swap price and the spot price. The oil buyer then buys the oil at the spot price.
+ The results for the buyer are the same whether the swap is settled physically or financially. In both cases, the net cost to the oil buyer is the swap price.

## THE SWAP COUNTERPARTY
+ The swap counterparty is a dealer who hedges the oil price risk resulting from the swap. The dealer can hedge by entering into offsetting long forward or futures contracts.
+ When the dealer serves as counterparty and hedges using forward markets, the dealer also has interest rate exposure from the implicit lending in the swap. So the dealer would also hedge interest rate risk using instruments like Eurodollar futures.
>
> the swap, we are lending the counterparty money for 1 year beginning in 1 year. If the deal is priced fairly, the interest rate on this loan should be the implied forward interest rate.

### THE SWAP COUNTERPARTY
+ The swap counterparty is a dealer who hedges the oil price risk resulting from the swap. The dealer can hedge in several ways. First, imagine that an oil seller would like to lock in a fixed selling price of oil. In this case, the dealer locates the oil buyer and seller and serves as a go-between for the swap, receiving payments from one party and passing them on to the other. In practice the fixed price paid by the buyer exceeds the fixed price received by the seller. This price difference is a [[Class Note 9 Bid and Ask Prices With Private Information|bid-ask spread]] and is the dealer’s fee.
+ The oil seller receives the spot price for oil and receives the swap price less the spot price, on net receiving the swap price. The oil buyer pays the spot price and receives the spot price less the swap price. The situation where the dealer matches the buyer and seller is called a back-to-back transaction or “matched book” transaction. The dealer bears the credit risk of both parties but is not exposed to price risk.

 ![500](IMG-20240913171236361.png)

+ A more interesting situation occurs when the dealer serves as counterparty and hedges the transaction using forward markets. Let’s see how this would work.
+ After entering the swap with the oil buyer, the dealer has the obligation to pay the spot price and receive the swap price. If the spot price rises, the dealer can lose money. The dealer has a short position in 1and 2-year oil.
+ The natural hedge for the dealer is to enter into long forward or futures contracts to offset this short exposure. Table 1 illustrates how this strategy works. As we discussed earlier, there is an implicit loan in the swap and this is apparent in Table 1. The net cash flow for the hedged dealer is a loan, where the dealer receives cash in year 1 and repays it in year 2.

| Year | Payment from Oil Buyer | Long Forward | Net |
| ---- | ---- | ---- | ---- |
| 1 |$110.483 - year 1 spot price | Year 1 spot price -$110 |$0.483 |
| 2 |$110.483 - year 2 spot price | Year 2 spot price -$111 | -$0.517 |

	- Positions and cash flows for a dealer who has an obligation to receive the fixed price in an oil swap and who hedges the exposure by going long year 1 and year 2 oil forwards.
	
+ This example shows that hedging the oil price risk in the swap, with forwards only, does not fully hedge the position. The dealer also has interest rate exposure. If interest rates fall, the dealer will not be able to earn a sufficient return from investing$0.483 in year 1 to repay$0.517 in year 2. Thus, in addition to entering oil forwards, it would make sense for the dealer to use Eurodollar contracts or [[A Guide to the Front End and Basis Swap Markets#Forward Rate Agreements (FRAs) Overview|Forward Rate Agreements]] to hedge the resulting interest rate exposure.

## THE MARKET VALUE OF A SWAP
+ When a swap is first entered, its market value is zero. Once payments begin, the market value is generally nonzero.
+ The market value comes from changes in forward prices over time as well as from the implicit borrowing/lending in the swap payments.
+ To exit a swap, one party can negotiate an offsetting swap to cancel out the original swap obligations. The difference in fixed prices on the original and new swaps determines the cash payment required.

So in summary, swaps are useful for hedging streams of commodity purchases or sales by fixing the effective price paid over time. Swap dealers offset their exposure using other derivatives markets. And swaps have nonzero market value once payments commence due to interest rates and price changes over time due to the implicit borrowing and lending.

+ A buyer wishing to exit the swap could negotiate terms with the original counterparty to eliminate the swap obligation.
	+ An alternative is to leave the original swap in place and enter into an offsetting swap with the counterparty offering the best price.
		+ The original swap called for the oil buyer to pay the fixed price and receive the floating price; the offsetting swap has the buyer receive the fixed price and pay floating.
		+ The original obligation would be cancelled except to the extent that the fixed prices are different.
		+ However, the difference is known, so oil price risk is eliminated. (There is still credit risk when the original swap counterparty and the counterparty to the offsetting swap are different. This could be a reason for the buyer to prefer offsetting the swap with the original counterparty.)
+ To see how a swap can change in value, suppose that immediately after the buyer enters the swap, the forward curve for oil rises by$2 in years 1 and 2.
+ Thus, the year1 forward price becomes$112 and the year-2 forward price becomes$113.
	+ The original swap will no longer have a zero market value.
+ Assuming interest rates are unchanged, the new swap price is$112.483.
+ The buyer could unwind the swap at this point by agreeing to sell oil at$112.483, while the original swap still calls for buying oil at$110.483. - Thus, the net swap payments in each year are (Spot price − 112.483 − spot price) =$2 Original swap New swap
	-The present value of this difference is$2 +$2 =$3.650 1.06 (1.065)2
	+ The buyer can receive a stream of payments worth$3.65 by offsetting the original swap with a new swap.
		-Thus,$3.65 is the market value of the swap.

 ![500](IMG-20240913171241643.png)

# Swaps Types

The swap rate calculation equates the value of a prepaid swap with the present value of the fixed swap payments.

## FIXED QUANTITY SWAPS

We first consider swaps with a notional amount that is fixed over time.^1^ Suppose there are n swap settlements, occurring on dates $t_i, i = 1, …, n$. The forward prices on these dates are given by $F_{0,t_i}$. We will account for interest rates by using bond price notation. The price of a zero-coupon bond maturing on date $t_i$ is $P(0, t_i)$. This price is the factor for discounting a fixed payment from date $t_i$ to date 0.

If the buyer at time zero were to enter into forward contracts to purchase one unit on each of the n dates, the present value of payments would be the present value of the forward prices, which equals the price of the prepaid swap: $$Prepaid\ Swap = \sum_{i=1}^{n} F_{0,t_i} P(0,t_i) \tag{1}$$
We determine the fixed swap price, R, by requiring that the present value of the swap payments equal the value of the prepaid swap. Thus, we have $$\sum_{i=1}^{n} R P(0,t_i) = \sum_{i=1}^{n} F_{0,t_i} P(0,t_i) \tag{2}$$
Solving for R gives $$R = \frac{\sum_{i=1}^{n} P(0,t_i) F_{0,t_i}}{\sum_{i=1}^{n} P(0,t_i)} \tag{3}$$
The expression $\sum_{i=1}^{n} P(0,t_i) F_{0,t_i}$ is the present value of payments implied by the strip of forward prices. The expression $\sum_{i=1}^{n} P(0,t_i)$is the present value of a$1 annuity. Thus, the swap rate annuitizes the interest payments on the floating-rate bond.

A different way to motivate the swap price calculation is to note that the present value of the differences between the swap price and the forward prices must equal zero:$$\sum_{i=1}^{n} P(0,t_i)[R - F_{0,t_i}] = 0 \tag{4}$$
This also gives rise to equation (3). 

We can rewrite equation (3) to make it easier to interpret:$$R = \sum_{i=1}^{n} \left[\frac{P(0,t_i)}{\sum_{j=1}^{n} P(0,t_j)} \right] F_{0,t_i}$$
The terms in square brackets sum to 1. This form of equation (3) emphasizes that the fixed swap rate is a weighted average of the forward prices, where zero-coupon bond prices are used to determine the weights.

Figure 6 displays a swap curve for natural gas, constructed using equation 3. The natural gas price exhibits seasonality. The swap price is a weighted average of natural gas forward prices over the life of the swap, and thus exhibits less variation. In Figure 6, the average natural gas futures price climbs so the swap curve climbs as well.

 ![500](IMG-20240913171244895.png)

A commodity buyer might prefer a swap in which quantities vary over time. For example, a natural gas buyer could enter into a swap supplying a greater quantity of gas during the heating season. A buyer might also wish to fix different prices in different seasons. For example, there could be seasonal variation in the price of the output produced using natural gas as an input. How do we determine the swap price with seasonally varying quantities and prices?

Let$Q_{t_i}$denote the quantity of the commodity to be purchased at time$t_i$. If a buyer pays in advance, the prepaid swap price is$$Prepaid\ Swap = \sum_{i=1}^{n} Q_{t_i} F_{0,t_i} P(0,t_i) \tag{5}$$
Consider a swap in which the buyer pays$RQ_{t_i}$for$Q_{t_i}$units of the commodity. The present value of these fixed payments (fixed per unit of the commodity) must equal the prepaid swap price, so that$$Prepaid\ Swap = \sum_{i=1}^{n} Q_{t_i} F_{0,t_i} P(0,t_i) \tag{6}$$

$$R = \frac{\sum_{i=1}^{n} Q_{t_i} P(0,t_i) F_{0,t_i}}{\sum_{i=1}^{n} Q_{t_i} P(0,t_i)} \tag{7}$$
The equation shows that if we are going to buy more gas when the forward price is high, we have to weight more heavily the forward price in those months. When$Q_t = 1$, the formula is the same as equation (3).

+ Once again, another way to derive this equation is to require that the present value of the quantity-weighted difference between the swap price and the forward prices is zero:$$\sum_{i=1}^{n} P(0,t_i) Q_{t_i} (R - F_{0,t_i}) = 0$$
+ We can also permit prices to be time-varying. If, for example, we let the summer swap price be denoted by$R_s$and the winter price by$R_w$, then the summer and winter swap prices can be any prices for which the value of the prepaid swap equals the present value of the fixed swap payments:$$\sum_{i \in summer} P(0,t_i)Q_{t_i}F_{0,t_i} + \sum_{i \in winter} P(0,t_i)Q_{t_i}F_{0,t_i} = \sum_{i \in summer} P(0,t_i)Q_{t_i}R_s + \sum_{i \in winter} P(0,t_i)Q_{t_i}R_w$$
+ The notations$i \in summer$and$i \in winter$mean to sum over only the months in those seasons. 
+ This gives us one equation and two unknowns,$R_s$and$R_w$.
+ Once we fix one of the two prices, the equation will give us the other.

# INTEREST RATE SWAPS  
## A SIMPLE INTEREST RATE SWAP

Suppose that XYZ Corp. has$200m of floating-rate debt at LIBOR—meaning that every year XYZ pays that year's current LIBOR—but would prefer to have fixed-rate debt with 3 years to maturity. There are several ways XYZ could effect this change.

First, XYZ could change their interest rate exposure by retiring the floating-rate debt and issuing fixed-rate debt in its place. However, an actual purchase and sale of debt has transaction costs.  

+ In other words, an interest rate swap is equivalent to borrowing at a floating rate to buy a fixed-rate bond.$$r_0(t_1,t_2) = \frac{P(0,t_1)}{P(0,t_2)} - 1$$
+ Therefore equation (4) can be rewritten

$$
\begin{aligned}\sum_{i=1}^nP(0,t_i)[R-r(t_{i-1},t_i)]&=\sum_{i=1}^nP(0,t_i)\left[R-\frac{P(0,t_{i-1})}{P(0,t_i)}+1\right]\end{aligned}
$$

Setting this equation equal to zero and solving for$R$gives us

You may recognize this as the formula for the coupon on a par coupon bond. This in turn can be rewritten as

$$
R\sum_{i=1}^nP(0,t_i)+P(0,t_n)=1
$$

This is the valuation equation for a bond priced at par with a coupon rate of$R$
The conclusion is that the swap rate is the coupon rate on a par coupon bond. This result is intuitive since a firm that swaps from floating-rate to fixed-rate exposure ends up with the economic equivalent of a fixed-rate bond.

# SWAP RATE AND BOND CALCULATIONS

The interest rate swap calculation we just illustrated is an application of equation (3), with the implied forward interest rate used as the forward price.

+ There is, however, an equivalent way to express the swap rate that is helpful in the case of an interest rate swap.  
+ The implied forward rate between times$t_1$and$t_2$,$r_0(t_1,t_2)$, is given by the ratio of zero-coupon bond prices, i.e.,$$r_0(t_1,t_2) = \frac{P(0,t_1)}{P(0,t_2)} - 1 \tag{10}$$
The conclusion is that the swap rate is the coupon rate on a par coupon bond.  

This result is intuitive since a firm that swaps from floating-rate to fixed-rate exposure ends up with the economic equivalent of a fixed-rate bond.

# 4. CURRENCY SWAPS
+ Firms sometimes issue debt denominated in a foreign currency.
+ A firm may do this as a hedge against revenues received in that currency, or because perceived borrowing costs in that currency are lower.
+ Whatever the reason, if the firm later wants to change the currency to which they have exposure, there are a variety of ways to do so.
+ The firm can use forward contracts to hedge exchange rate risk, or it can use a currency swap, in which payments are based on the difference in debt payments denominated in different currencies.
+ To understand these alternatives, let's consider the example of a dollar-based firm that has euro-denominated 3-year fixed-rate debt.
+ The annual coupon rate is ρ. The firm is obligated to make a series of payments that are fixed in euro terms but variable in dollar terms.
+ Since the payments are known, eliminating euro exposure is a straightforward hedging problem using currency forwards. 
	+ We have cash flows of −ρ each year, and −(1 + ρ) in the maturity year. 
	+ If currency forward prices are$F_{0,t}$, we can enter into long euro forward contracts to acquire at a known exchange rate the euros we need to pay to the lenders. 
	+ Hedged cash flows in year t are$−ρF_{0, t}$.
+ As we have seen in other examples, the forward transactions eliminate risk but leave the firm with a variable (but riskless) stream of cash flows. The variability of hedged cash flows is illustrated in the following example
	+ Suppose the effective annual euro-denominated interest rate is 3.5% and the dollar-denominated rate is 6%. 
	+ The spot exchange rate is$0.90/=C. 
	+ A dollar-based firm has a 3-year 3.5% euro-denominated bond with a =EUR 100 par value and price of =EUR 100.
+ The firm wishes to guarantee the dollar value of the payments.
+ Since the firm will make debt payments in euros, it buys the euro forward to eliminate currency exposure.
	+ Table 5 summarizes the transaction and reports the currency forward curve and the unhedged and hedged cash flows.
+ The value of the hedged cash flows is

| Year | Unhedged<br>Euro Cash Flow | Forward<br>Exchange Rate | Hedged<br>Dollar Cash Flow |
| ---- | ---- | ---- | ---- |
| 1 | -€3.5 | 0.922 | -$3.226 |
| 2 | -€3.5 | 0.944 | -$3.304 |
| 3 | -€103.5 | 0.967 | -$100.064 |

	- Unhedged and hedged cash flows for a dollar-based firm with euro-denominated debt.
+ The market-maker's net exposure in this transaction is long a dollar-denominated bond and short a euro-denominated bond. 
+ Table 6 shows that after hedging there is a series of net cash flows with zero present value. 

| Year | Rate ($/€) | Interest | Euro Interest | Flow |
| ---- | ---- | ---- | ---- | ---- |
| L | 0.9217 | $5.40 | - €3.5 × 0.9217 | $2.174 |
| 2 | 0.9440 | $5.40 | - €3.5 × 0.9440 | $2.096 |
| 3 | 0.9668 | 4.664 |     - ﻿€103.5 × 0.9668 | -$4.664 |

	- Unhedged and hedged cash flows for a dollar-based firm with euro-denominated debt. The effective annual dollar-denominated interest rate is 6% and the effective annual euro-denominated interest rate is 3.5%.

+ As in all the previous examples, the effect of the swap is equivalent to entering into forward contracts, coupled with borrowing or lending.
+ In this case, the firm is lending to the market-maker in the first 2 years, with the implicit loan repaid at maturity.