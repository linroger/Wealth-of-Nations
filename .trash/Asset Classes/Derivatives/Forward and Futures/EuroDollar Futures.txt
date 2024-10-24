---
aliases:
- Alias_262_EuroDollar Futures.md
- Alias_259_EuroDollar Futures.md
tags:
- tag_example
title: EuroDollar Futures
---



# EuroDollar Futures
- The Eurodollar contract is based on a$1 million 3-month deposit earning LIBOR (the London Interbank Offer Rate),  which is the average borrowing rate faced by large international London banks. The 1-month LIBOR contract is similar.
- Suppose that current LIBOR is 1.5% over 3 months.
	- By convention,  this is annualized by multiplying by 4,  so the quoted LIBOR rate is 6%. Assuming a bank borrows$1 million for  3 months,    a change in annualized LIBOR of 0.01% (1 basis point) would raise its borrowing cost by 0.0001/4 ×$1 million =$25
- The Eurodollar futures price at expiration of the contract is $100 − \text{Annualized } 3-month LIBOR$

Thus,  if LIBOR is 6% at maturity of the Eurodollar futures contract,  the final futures price will be 100 − 6 = 94. It is important to understand that the Eurodollar contract settles based on current LIBOR,  which is the interest rate quoted for the next 3 months. Thus,  for example,  the price of the contract that expires in June reflects the 3-month interest rate between June and September. With the futures contract,  as with a$1 million LIBOR deposit,    a change of 0.01% in the rate is worth$25.

### SPECIFICATIONS FOR THE EURODOLLAR FUTURES CONTRACT

Like most money-market interest rates,  LIBOR is quoted assuming a 360-day year. Thus,  the annualized 91-day rate,  $r_{91}$,  can be extracted from the futures price,  F,  by computing the 90-day rate and multiplying by 91/90. The quarterly effective rate is then computed by dividing the result by 4:$$r_{91} = (100-F) \times \frac{1}{100} \times \frac{1}{4} \times \frac{91}{90}\tag{19}$$
Three-month Eurodollar contracts have maturities out to 10 years,  which means that it is possible to use the contract to lock in a 3-month rate as far as 10 years in the future.

If the Eurodollar futures contract maturing 60 months from today has a price of 95.25,  this means that the contract can be used to lock in an annualized rate of 4.75% for a period beginning 60 months from today and terminating 63 months from today.

The Eurodollar futures strip (the set of futures prices with different maturities at one point in time) provides basic interest rate information that is commonly used to price other futures contracts and to price swaps.

Figure 5 depicts the Eurodollar strip for four dates. Each point on the graph is the annualized 3-month interest rate implied by the Eurodollar futures price maturing that many months in the future.

Let's see how the Eurodollar contract can be used to hedge interest rate risk. For a borrower,  for example,  a short position in the contract is a hedge because it pays when the interest rate rises and requires payment when the interest rate falls. 

To see this,  suppose that 7 months from today we plan to borrow$1 million for 90 days,    and that our borrowing rate is the same as LIBOR. The Eurodollar futures price for 7 months from today is 94; this implies a 90-day rate of (100 − 94) × 90/360 × 1/100 = 1.5%. Now suppose that 7 months hence,    3-month LIBOR is 8%,    which implies a Eurodollar futures price of 92. The implied 90-day rate is 2%. Our extra borrowing expense over 90 days on$1 million will therefore be (0.02 − 0.015) ×$1m =$5000.

This extra borrowing expense is offset by gains on the short Eurodollar contract. The Eurodollar futures price has gone down,  giving us a gain of$25 per basis point,    or$25 × 100 × (94 − 92) =$5000.

The short position in the futures contract compensates us for the increase in our borrowing cost0.\1 In the same way,  a long position can be used to lock in a lending rate.

The Eurodollar futures price is a construct,  not the price of an asset. In this sense Eurodollar futures are different from the futures contracts we have already discussed. Although Eurodollar LIBOR is closely related to a number of other interest rates,  there is no one specific identifiable asset that underlies the Eurodollar futures contract

LIBOR is quoted in currencies other than dollars,  and comparable rates are quoted in different locations. In addition to LIBOR,  there are PIBOR (Paris),  TIBOR (Tokyo),  and Euribor (the European Banking Federation).

Finally,  you might be wondering why we are discussing LIBOR rather than rates on Treasury bills. Business and bank borrowing rates move more in tandem with LIBOR than with the government's borrowing rate. Thus,  these borrowers use the Eurodollar futures contract to hedge. LIBOR is also a better measure of the cost of funds for a market-maker,  so LIBOR is typically used to price forward contracts.

It might occur to you that the Eurodollar contract pays us at the time we borrow,  but we do not pay interest until the loan matures,  91 days hence. Since we have time to earn interest on the change in the value of the contract,  the hedge ratio should be less than 1 contract per \$1 million borrowing.

![](CleanShot%202024-01-28%20-000164@2x.png)