---
aliases:
- Alias_272_Treasury Futures.md
- '**TREASURY BOND FUTURES CONTRACT**'
- Alias_269_Treasury Futures.md
linter-yaml-title-alias: '**TREASURY BOND FUTURES CONTRACT**'
tags:
- tag_example
title: '**TREASURY BOND FUTURES CONTRACT**'
---


# **TREASURY BOND FUTURES CONTRACT**

- The Treasury bond (T-bond) futures contract is the most successful interest rate futures contract, traded on the Chicago Mercantile Exchange (CME).
- Prices are quoted in terms of a hypothetical 20-year 6% T-bond, but many different actual T-bonds can be delivered.
- Any T-bond with 15-25 years remaining maturity on the first day of the delivery month is acceptable.
- The Ultra Long T-bond futures contract differs in requiring ≥ 25 years remaining maturity.
- The short seller must deliver$100,000 face value of a qualifying T-bond.
- The futures price is adjusted by a conversion factor reflecting the price the bond would sell for at 6% yield.
- The conversion factor is constant over time for a given bond and delivery month.
- The short seller chooses which qualifying bond to deliver and when in the delivery month.
- The buyer pays the futures price x conversion factor + accrued interest.
- The contract is physically settled by delivery of a qualifying bond, not cash-settled.
- The delivery mechanism provides options that make the contract successful:
	 - **Cheapest-to-deliver option**: The short can deliver the cheapest qualified bond and make a more profitable delivery.
	 - **Timing option**: Within CME guidelines, the short chooses the delivery date and can time it advantageously.
	 - **Wildcard play**: The short can give delivery notice after the settlement price is fixed. In a falling market, this allows profiting from the fixed price.

---

## **TREASURY NOTE FUTURES**

- There are 7 different Treasury note futures contracts that trade on the Chicago Mercantile Exchange (CME):
	 - 10-year on-the-run Treasury note futures
	 - 10-year Treasury note futures
	 - Ultra 10-year Treasury note futures
	 - 5-year on-the-run Treasury note futures
	 - 5-year Treasury note futures
	 - 2-year on-the-run Treasury note futures
	 - 2-year Treasury note futures
- The 10-year, 5-year, and 2-year Treasury note futures contracts are modeled after the Treasury bond futures contract in terms of delivery options and settlement. These 4 contracts are physically settled by delivery of actual Treasury notes.
	 - The on-the-run note futures contracts (10-year, 5-year, and 2-year) are cash settled rather than physically settled.
- The 10-year Treasury note futures contract is based on a hypothetical$100,000 face value 10-year Treasury note with a 6% coupon. There are several Treasury notes with different coupons and maturities that are acceptable for delivery by the short to fulfill the contract. A note is eligible for delivery if its maturity is between 6.5 years and 10 years from the first day of the delivery month.
- The short seller of the 10-year note futures has the same delivery options as the Treasury bond futures contract. They can choose the cheapest qualifying note to deliver, time the delivery advantageously, and potentially make a wildcard play if rates move in their favor after settlement.
- The underlying instrument for the 5-year Treasury note futures contract is$100,000 face value of a Treasury note with an original maturity of 5 years and 3 months or less, and a remaining maturity of at least 4 years and 2 months on the first day of the delivery month.
- The 2-year Treasury note futures contract is based on a hypothetical 2-year Treasury note with a$200,000 face value. Deliverable notes must have between 1 year 9 months and 2 years remaining maturity on the first day of the delivery month, with an original maturity of 5 years 3 months or less.
- The hypothetical 6% coupon used for the futures contracts is much higher than current Treasury note yields. This inflates the quoted futures price relative to actual note prices. When notes are delivered to settle the contract, they are converted to the equivalent price based on the 6% coupon via a conversion factor.
- The short seller will choose to deliver the note that converts to the lowest price, making it the cheapest-to-deliver. Typically, shorter duration notes are cheapest-to-deliver when yields are below 6%, while longer duration notes are cheapest when yields are above 6%.

**Example 1**

> To illustrate this, let us take a look at the 2020 September 10-year Treasury futures contract as of June 10, 2020. The futures price is 138-05+, optically quite high, given the gap between the 6% theoretical coupon and the below 1% 10-year yield these days. The following table shows three of the many eligible securities:

|   |   |   |   |
|---|---|---|---|
|Security|Price|Conversion Factor|Gross Basis|
|Т 2 3/8 05/15/27|112-05 ¼|0.8072|20.215|
|T 2 ¼ 08/15/27|111-18 ¾|0.7943|58.753|
|Т 0 5/8 03/31/27|100-09|0.7142|51.165|

_Question: Which bond is the cheapest-to-deliver?_

**Solution:** To find the cheapest-to-deliver, we look at the gross basis. The lower the gross basis, the cheaper it is to deliver that bond.

The first bond, T 2 3/8 05/15/27, has the lowest gross basis of 20.215. Therefore, this is the cheapest-to-deliver bond.

## **TREASURY BILL FUTURES**

The Treasury bill futures contract was the first futures contract introduced for a short-term debt instrument. It is traded on the International Money Market, a division of the CME.

The contract is based on$1 million face value of 3-month Treasury bills. The futures price is quoted differently than other futures contracts - it represents the interest rate rather than the price.

Specifically, the futures price is equal to 100 minus the annualized interest rate. For example, a quoted price of 97.50 corresponds to an interest rate of 2.50%.

The actual invoice price paid by the buyer of the futures contract is calculated using the standard T-bill pricing formula:

Invoice Price =$1,000,000 x [1 - (rate x days to maturity/360)]

Where the rate is expressed as a decimal, not percent.

As this formula shows, a 0.01 change in the futures price is equivalent to a$25 change in the invoice price for a 90-day T-bill.

**Example 2**

> The actual price that the buyer pays the seller is calculated using the usual formula for Treasury bills:
> Invoice price =$1,000,000 × [1 − rate × (days to maturity/360)]
> where the rate is expressed in decimal form. As this formula shows, each basis point change in the interest rate (or each 0.01 change in the futures price) leads to a$25 change in the invoice price for a 90-day bill.

_Question: If the 90-day T-bill futures price is 96.50 (implying a rate of 3.50%), what is the invoice price for a contract with 60 days to maturity?_

**Solution:**

- Futures price = 96.50
- Rate = 100 - Futures price = 100 - 96.50 = 3.50%
- Days to maturity = 60
- Rate in decimal form = 0.035

Plugging into the formula:

- Invoice price =$1,000,000 x [1 - 0.035 x (60/360)] =$1,000,000 x [1 - 0.0175] =$1,000,000 x 0.9825 =$982,500

Therefore, with a futures price of 96.50 and 60 days to maturity, the invoice price is$982,500.

The Treasury bill futures contract is simpler than the Treasury bond and note futures contracts in several ways:

- There is effectively only one deliverable security - Treasury bills with exactly 3 months remaining maturity.
- The delivery window is very narrow, just 3 days, and set well in advance.
- There are no conversion factors or wildcard play possible.

Despite its simplicity, the T-bill futures contract provides an important means to hedge or speculate on the short end of the yield curve. The T-bill rate is a benchmark for other short-term rates, so the futures contract fills a key need for many market participants.

---

## **TREASURY NOTE FUTURES**
- There are 7 Treasury note futures contracts:
	 - 10-year on-the-run
	 - 10-year
	 - Ultra 10-year
	 - 5-year on-the-run
	 - 5-year
	 - 2-year on-the-run
	 - 2-year
- 4 are modeled after the T-bond futures contract and traded on CME.
- The on-the-run contracts are cash-settled.
- 10-year note futures:
	 - Underlying is$100,000 face of hypothetical 10-year 6% note.
	 - Deliverable notes must have 6.5-10 year maturity on first delivery day.
	 - Same delivery options as T-bond futures.
- 5-year note futures:
	 - Underlying is$100,000 face note with 4-5 year maturity on first delivery day.
- 2-year note futures:
	 - Underlying is$200,000 face note with 1-2 year maturity on first delivery day.
	 - Original maturity ≤ 5 years, 3 months.
- The 6% coupon is far from current yields, inflating futures price.
- Actual delivery bonds are converted to 6% theoretical bond.
- Cheapest-to-deliver has lowest converted futures price. Typically lower duration when yields < 6%, higher when > 6%.

## **TREASURY BILL FUTURES**

- First short-term debt instrument futures contract.
- Based on$1 million face value 3-month T-bills.
- Quoted as "price" which is 100 - annualized rate.
- Example: 97.50 price = 2.50% rate.
- Invoice price depends on rate and days to maturity.
- Simpler than T-bond/note futures:
	 - Only one deliverable issue - 3-month T-bills.
	 - Narrow delivery window, set in advance.
	 - No conversion factors or wildcard play.
- Provides means to hedge/speculate on short end of yield curve.
- Suppose that a 20-year$100 par value bond with a coupon rate of 12% is selling at par. Also suppose that this bond is the deliverable for a futures contract tract that settles in three months. If the current threeQ-month interest rate at which funds can be loaned or borrowed is 8% per year, what should be the price of this futures contract? Suppose the price of the futures contract is 107. Consider the following strategy:

Suppose the price of the futures contract is 107. Consider the following strategy:

- Sell the futures contract at 107.
- Purchase the bond for 100.
- Borrow 100 for three months at 8% per year.

In contrast, suppose that the futures price is 92 instead of 107. Consider the following strategy:

- Buy the futures contract at 92.
- Sell (short) the bond for 100.
- Invest (lend) 100 for three months at 8% per year.

|   |   |
|---|---|
|From settlement of the futures contract||
|Flat price of bond|107|
|Accrued interest (12% for three months)|+3|
|Total proceeds|110|
|From the loan||
|Repayment of principal of loan|100|
|Interest on loan (8% for three months)|+2|
|Total outlay|102|
|Profit|8|

This strategy will guarantee a profit of 8. Moreover, the profit is generated with no initial outlay because the funds used to purchase the bond are borrowed. The profit will be realized regardless of the futures price at the settlement date. In a well-functioning market, arbitrageurs would buy the bond and sell the futures, forcing the futures price down and bidding up the bond price so as to eliminate this profit. This strategy of purchasing a bond with borrowed funds and simultaneously selling a futures contract to generate an arbitrage profit is called a cash and carry trade.

|   |   |
|---|---|
|From settlement of the futures contract||
|Flat price of bond|92|
|Accrued interest (12% for three months)|+3|
|Total outlay|95|
|From the loan||
|Principal received from maturing investment|100|
|Interest earned from the three-month investment (8% for three months)|+2|
|Total proceeds|102|
|Profit|7|

Once again, there is no initial cash outlay. Three months from now a bond will be purchased to settle the long position in the futures contract. That bond will then be used to cover the short position (i.e., to cover the short sale in the cash market). The outcome in three months would be as follows:

The 7 profit is a pure arbitrage profit. It requires no initial cash outlay and will be realized regardless of the futures price at the settlement date. Because this strategy involves initially selling the underlying bond, it is called a reverse cash and carry trade.

- There is a futures price, however, that will eliminate the arbitrage profit. There will be no arbitrage if the futures price is 99. Let’s look at what would happen if the two previous strategies were followed and the futures price were 99. First, consider the following cash and carry trade:
	- Sell the futures contract at 99.
	- Purchase the bond for 100.
	- Borrow 100 for three months at 8% per year.

In three months, the outcome would be as follows:

|   |   |
|---|---|
|From settlement of the futures contract|99|
|Flat price of bond||
|Accrued interest (12% for three months)|+3|
|Total proceeds  <br>From the loan|102|
|Repayment of principal of the loan  <br>100||
|Interest on the loan (8% for three months)|+2|
|Total outlay|102|
|Profit|0|

Next, consider the following reverse cash and carry trade:
	- Buy the futures contract at 99.
	- Sell (short) the bond for 100.
	- Invest (lend) 100 for three months at 8% per year.

The outcome in three months would be as follows:

|   |   |
|---|---|
|From settlement of the futures contract||
|Flat price of bond|99|
|Accrued interest (12% for three months)|+3|
|Total outlay|102|
|From the loan||
|Principal received from maturing investment|100|
|Interest earned from the three-month investment(8% for three months)|+2|
|Total proceeds|102|
|Profit||

Thus neither strategy results in a profit. The futures price of 99 is the equilibrium price because any higher or lower futures price will permit arbitrage profits.

### THEORETICAL FUTURES PRICE BASED ON ARBITRAGE MODEL

Considering the arbitrage arguments just presented, the equilibrium futures price can be determined on the basis of the following information:

- The price of the bond in the cash market.
- The coupon rate on the bond. In our example, the coupon rate was 12% per annum.
- The interest rate for borrowing and lending until the settlement date. The borrowing and lending rate is referred to as the financing rate. In our example, the financing rate was 8% per annum.
- Consider the following cash and carry trade that is initiated on a coupon date:
	- Sell the futures contract at$F$.
	- Purchase the bond for$P$.
	- Borrow$P$until the settlement date at$r$.
 The outcome at the settlement date is as follows:

We will let
$r$ = financing rate
$c$ = current yield, or coupon rate divided by the cash market price P = cash market price
$F$ = futures price
$t$= time, in years, to the futures delivery date

- The profit will equal
	 - Profit = total proceeds – total outlay$$\text{Profit} = F + c_tP − (P + r_tP)$$
- In equilibrium, the theoretical futures price occurs where the profit from this strategy is zero. Thus, to have equilibrium, the following must hold:-$$0 = F + c_tP − (P + r_tP)$$
- Solving for the theoretical futures price, we have$$F = P + P_t(r − c) = P[1 + t(r − c)]$$

The theoretical futures price may be at a premium to the cash market price (higher than the cash market price) or at a discount from the cash market price (lower than the cash market price), depending on the value of (r − c). The term r − c is called the net financing cost because it adjusts the financing rate for the coupon interest earned. The net financing cost is more commonly called the cost of carry, or simply carry. Positive carry means that the current yield earned is greater than the financing cost; negative carry means that the financing cost exceeds the current yield. The relationships can be expressed as follows:

|   |   |
|---|---|
|Carry|Futures Price|
|Positive (c > r)|Will sell at a discount to the cash price (F < P)|
|Negative (c < r)|Will sell at a premium to the cash price (F > P)|
|Zero (r= c)|Will be equal to the cash price (F = P)|

### THE SHORT-TERM INTEREST RATE (FINANCING RATE)

- In deriving the theoretical futures price, it is assumed that the borrowing and lending rates are equal. Typically, however, the borrowing rate is greater than the lending rate. We will let
	 - $r_B$= borrowing rate
	 - $r_L$= lending rate
- Sell the futures contract at$F.$
	- Purchase the bond for$P$.
	- Borrow P until the settlement date at$r_B.$
The futures price that would produce no arbitrage profit is
$$F=P+P(r_B −c)$$
- Buy the futures contract at$F.$
- Sell (short) the bond for$P.$
- Invest (lend)$P$at$r_L$until the settlement date.
The futures price that would produce no profit is$$F=P+P(r_L −c)$$