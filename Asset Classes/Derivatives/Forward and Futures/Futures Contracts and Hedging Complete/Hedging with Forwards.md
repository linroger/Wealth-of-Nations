---
Owner: RRoger Lin
tags: [Forwards-and-Futures,  Hedging]
aliases: [THE BASIC HEDGING DECISION, Forwards Contracts]
title: THE BASIC HEDGING DECISION
linter-yaml-title-alias: THE BASIC HEDGING DECISION
---

  [[0. Finance Notes/1. Financial Instruments/Derivatives/Forward and Futures/Forwards and Futures Notes]]

- Suppose that a 20-year$100 par value bond with a coupon rate of 12% is selling at par. Also suppose that this bond is the deliverable for a futures contract tract that settles in three months. If the current threeQ-month interest rate at which funds can be loaned or borrowed is 8% per year,  what should be the price of this futures contract? Suppose the price of the futures contract is 107. Consider the following strategy:

Suppose the price of the futures contract is 107. Consider the following strategy:

- Sell the futures contract at 107.
- Purchase the bond for 100.
- Borrow 100 for three months at 8% per year.

In contrast,  suppose that the futures price is 92 instead of 107. Consider the following strategy:
Buy the futures contract at 92.
Sell (short) the bond for 100.
Invest (lend) 100 for three months at 8% per year.

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

This strategy will guarantee a profit of 8. Moreover,  the profit is generated with no initial outlay because the funds used to purchase the bond are borrowed. The profit will be realized regardless of the futures price at the settlement date. In a well-functioning market,  arbitrageurs would buy the bond and sell the futures,  forcing the futures price down and bidding up the bond price so as to eliminate this profit. This strategy of purchasing a bond with borrowed funds and simultaneously selling a futures contract to generate an arbitrage profit is called a cash and carry trade.

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

Once again,  there is no initial cash outlay. Three months from now a bond will be purchased to settle the long position in the futures contract. That bond will then be used to cover the short position (i.e.,  to cover the short sale in the cash market). The outcome in three months would be as follows:

The 7 profit is a pure arbitrage profit. It requires no initial cash outlay and will be realized regardless of the futures price at the settlement date. Because this strategy involves initially selling the underlying bond,  it is called a reverse cash and carry trade.

- There is a futures price,  however,  that will eliminate the arbitrage profit. There will be no arbitrage if the futures price is 99. Let’s look at what would happen if the two previous strategies were followed and the futures price were 99. First,  consider the following cash and carry trade:

Sell the futures contract at 99.
Purchase the bond for 100.
Borrow 100 for three months at 8% per year.
In three months,  the outcome would be as follows:

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

Next,  consider the following reverse cash and carry trade:
Buy the futures contract at 99.
Sell (short) the bond for 100.
Invest (lend) 100 for three months at 8% per year.
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

Considering the arbitrage arguments just presented,  the equilibrium futures price can be determined on the basis of the following information:

- The price of the bond in the cash market.
- The coupon rate on the bond. In our example,  the coupon rate was 12% per annum.
- The interest rate for borrowing and lending until the settlement date. The borrowing and lending rate is referred to as the financing rate. In our example,  the financing rate was 8% per annum.
- Consider the following cash and carry trade that is initiated on a coupon date:

	 Sell the futures contract at F.
	 Purchase the bond for P.
	 Borrow P until the settlement date at r.
	 The outcome at the settlement date is as follows:

We will let
r = financing rate
c = current yield,  or coupon rate divided by the cash market price P = cash market price
F = futures price
t = time,  in years,  to the futures delivery date

- The profit will equal
	 - Profit = total proceeds – total outlay
	 - $$Profit = F + c_{t}P − (P + r_{t}P)$$
- In equilibrium,  the theoretical futures price occurs where the profit from this strategy is zero. Thus,  to have equilibrium,  the following must hold:
	 - $$0 = F + c_{t}P − (P + r_{t}P)$$
- Solving for the theoretical futures price,  we have
	 -$$F = P + P_{t}(r − c) = P[1 + t(r − c)]$$

The theoretical futures price may be at a premium to the cash market price (higher than the cash market price) or at a discount from the cash market price (lower than the cash market price),  depending on the value of (r − c). The term r − c is called the net financing cost because it adjusts the financing rate for the coupon interest earned. The net financing cost is more commonly called the cost of carry,  or simply carry. Positive carry means that the current yield earned is greater than the financing cost; negative carry means that the financing cost exceeds the current yield. The relationships can be expressed as follows:

|   |   |
|---|---|
|Carry|Futures Price|
|Positive (c > r)|Will sell at a discount to the cash price (F < P)|
|Negative (c < r)|Will sell at a premium to the cash price (F > P)|
|Zero (r= c)|Will be equal to the cash price (F = P)|

### THE SHORT-TERM INTEREST RATE (FINANCING RATE)

- In deriving the theoretical futures price,  it is assumed that the borrowing and lending rates are equal. Typically,  however,  the borrowing rate is greater than the lending rate. We will let
	 - rB = borrowing rate
	 - rL = lending rate
- Sell the futures contract at F.
	 Purchase the bond for P.
	 Borrow P until the settlement date at rB.
	 The futures price that would produce no arbitrage profit is$$F=P+P(r_B −c)$$
- Buy the futures contract at F
	- Sell (short) the bond for P.
	- Invest (lend) P at rL until the settlement date
	- The futures price that would produce no profit is$$F=P+P(r_L −c)$$

---

## INTEREST-RATE RISK CONTROL

- Interest-rate risk control is probably the most common use of interest-rate futures.
- This is accomplished by altering the portfolio’s duration. Money managers who have strong expectations about the direction of interest rates will adjust the duration of their portfolio to capitalize on their expectations.
	 - Specifically,  if they expect interest rates to increase,  they will shorten the duration of the portfolio;
	 - if they expect interest rates to decrease,  they will lengthen the duration of the portfolio.
- Also,  anyone using structured portfolio strategies must periodically adjust the portfolio duration to match the duration of some benchmark.

### CREATING SYNTHETIC SECURITIES FOR YIELD ENHANCEMENT

- A cash market security can be synthetically created by using a position in the futures contract together with the deliverable instrument. The yield on the synthetic security should be the same as the yield on the cash market security. If there is a difference between the two yields,  it can be exploited so as to enhance the yield on the portfolio.
- To see how,  consider an investor who owns a 20-year Treasury bond and sells Treasury futures that call for the delivery of that particular bond three months from now. The maturity of the Treasury bond is 20 years,  but the investor has effectively shortened the maturity of the bond to three months.
- Consequently,  the long position in the 20-year bond and the short futures position are equivalent to a long position in a three-month riskless security.
	 - The position is riskless because the investor is locking in the price that will be received three months from now—the futures price.
	 - By being long the bond and short the futures,  the investor has synthetically created a three-month Treasury bill.
	 - The return the investor should expect to earn from this synthetic position should be the yield on a three-month Treasury bill.
	 - If the yield on the synthetic three-month Treasury bill is greater than the yield on the cash market Treasury bill,  the investor can realize an enhanced yield by creating the synthetic shortterm security.
- The fundamental relationship for creating synthetic securities is as follows
	 - RSP = СВР - BFP
		  - СВР = cash bond position
				BFP = bond futures position
				RSP = riskless short-term security position

- The price of an interest rate futures contract moves opposite to changes in interest rates.
	 - When rates rise,  the futures price will fall as the present value of the underlying instrument declines.
	 - When rates fall,  the futures price will rise as the present value of the underlying instrument increases.
- Buying futures increases a portfolio’s exposure to interest rate changes by increasing its duration.
	 - The portfolio’s dollar duration increases with a net long futures position.
- Selling futures decreases a portfolio’s exposure to interest rate changes by decreasing its duration.
	 - The portfolio’s dollar duration decreases with a net short futures position.
- Using futures to alter duration has advantages over using cash market instruments:
	 1. Transaction costs are lower for futures than for trading in the cash market since there is no transfer of principal.
	 1. Margin requirements are lower for futures,  permitting greater leverage. Futures might require 1-2% margin versus 5-10% margin for underlying cash bonds.
	 1. Short selling is easier in the futures market than in the cash market due to fewer restrictions and lower costs.

## GENERAL PRINCIPLES OF INTEREST-RATE RISK CONTROL

- The general principle in controlling interest-rate risk with futures is to combine the dollar exposure of the current portfolio and the dollar exposure of a futures position so that the total dollar exposure is equal to the target dollar exposure.
- General principles for controlling interest rate risk with futures:
	 - Combine the dollar exposure of the portfolio and the dollar exposure of the futures position so that the total dollar exposure equals the target dollar exposure.
	 - To do this,  the dollar exposure of both the portfolio and futures contract must be accurately measured.
- Measures for approximating the dollar value change of bonds/portfolio with rate changes:
	 - Price value of a basis point (PVBP): the dollar price change from a 1 basis point yield change.
	 - Duration: the approximate percentage price change for a 100 basis point rate change.
		  - Effective duration should be used for bonds with embedded options.
		  - Effective dollar duration measures sensitivity for small basis point changes.
- Estimating effective dollar duration requires a valuation model to determine bond value changes when rates change.
	 - The valuation model is key for measuring dollar price exposure and for valuing futures contracts.
- The methodology for controlling interest rate risk with futures:
	 1. Determine a target duration based on rate expectations or specified by client.
	 1. Calculate the target dollar duration for a small basis point change using the target duration.
		  - For a 50 bp rate change,  multiply portfolio value by target duration and divide by 200.
	 1. Estimate the current dollar duration of the portfolio without futures.
		  - Multiply current duration by portfolio value and divide by 200.
	 1. Compare the target dollar duration to the current dollar duration without futures.
		  - The difference is the dollar exposure needed from the futures position.
				- If target exceeds current,  buy futures contracts to increase dollar exposure.
				- If target is less than current,  sell futures contracts to reduce dollar exposure.
- Number of futures contracts needed: this gives the approximate number of futures contracts that are necessary to adjust the portfolio’s dollar duration to the target dollar duration.
	 - A positive number means that the futures contract must be purchased; a negative number means that the futures contract must be sold.
		  - Notice that if the target dollar duration is greater than the current dollar duration without futures,  the numerator is positive,  and therefore,  futures contracts are purchased.
		  - If the target dollar duration is less than the current dollar duration without futures,  the numerator is negative,  and therefore,  futures contracts are sold.

$\text{Number of Futures Contracts}= \frac{\text{Target Dollar Duration}-\text{Current Dollar Duration}}{\text{Dollar Duration per Futures Contract}}$

	 - Target dollar duration specified by manager
	 - Current dollar duration based on portfolio composition
- Dollar duration per contract estimated from valuation model
- Dollar duration of a futures position:

$\text{Dollar Duration of a Futures Position}=\text{Number of Contracts}*\text{Dollar Duration per Futures Contract}$

	 - Number of contracts determined by manager
	 - Dollar duration per contract from valuation model
- Hedging with futures takes a temporary futures position as a substitute for intended future cash market transactions.
	 - Offsetting gains and losses on the positions locks in a rate or price.
- A short hedge sells futures contracts to lock in a bond sale price.
	 - It protects against a decline in the cash price.
	 - It transfers price risk to the buyer of the futures contract.
- A long hedge buys futures contracts to lock in a bond purchase price.
	 - It protects against an increase in the cash price.

### THE HEDGING PROCESS

1. Determine appropriate hedging instrument.
	 - High correlation between futures rate and risk rate is critical.
	 - Liquidity matters for large hedges.
1. Determine hedge target.
	 - Target rate or price expected to be locked in.
1. Determine position to take in hedging instrument.
	 - Number of futures contracts (hedge ratio).
1. Monitor and evaluate hedge.

- Hedge ratio - number of futures contracts: =

$\text{Hedge Ratio} = \frac{- \text{Current Dollar Duration}}{\text{Dollar Duration per Futures Contract}}$

	 - Current dollar duration: cash position without futures
	 - Dollar duration per contract: estimated from valuation model
- For Treasury bond and note futures:

$\text{Hedge Ratio} = -\frac{\text{Current Dollar Duration}}{\text{Dollar Duration of CTD Issue}}*\frac{\text{Dollar Duration of CTD Issue}}{\text{Dollar Duration per Futures Contract}}$

	 - Dollar duration depends on the cheapest-to-deliver (CTD) issue
	 - Conversion factor relates CTD price to futures price
- Hedging a non-deliverable bond is more complex:

$\text{Hedge Ratio} = \frac{- \text{Current Dollar Duration Without Futures}}{\text{Dollar Duration per Futures Contract}}$

	 - Involves the relationship between the CTD issue and the bond to be hedged
	 - The relative yield spread may change over time
	 - Can refine calculation using regression to estimate yield beta:
		  - Captures relative expected yield changes

## HEDGING WITH OPTIONS

- Basic hedging strategies using options:
	 1. Protective put buying strategy
		  - Long put position + long bond position
		  - Limits downside risk,  unlimited upside potential
	 1. Covered call writing strategy
		  - Short call position + long bond position
		  - Gives up some upside for downside protection
	 1. Collar strategy
		  - Long put position + short call position
		  - Limits upside and downside
- A protective put buying strategy purchases OTM put options on bonds or interest rate futures.
	 - As rates rise,  the puts increase in value to offset bond price declines.
- This strategy is like purchasing insurance:
	 - The premium paid is nonrefundable,  like an insurance cost
	 - The strike price is akin to the deductible
		  - A lower strike price means more protection at a higher cost
- There is no single optimal strike price:
	 - The optimal strike depends on risk preferences
- A covered call writing strategy sells OTM calls on bonds or interest rate futures.
	 - The call premium acts as a cushion against downward price moves
	 - However,  upside potential is forfeited
- Lower call strike prices provide more downside protection but limit upside potential.
- To illustrate hedging a bond with futures options:
	 - Use September 1999 Treasury bond futures options
	 - Hedge a$10 million FNMA 6.25% bond maturing 5/15/29
	 - Previously sold 112 futures contracts to hedge this bond
- The hedging process:
	 1. Determine appropriate options contract
		  - September futures options hedge the September futures position
	 1. Determine hedge objective
		  - Lock in effective sale price for the FNMA bond
	 1. Take options position
		  - Sell OTM put options
	 1. Evaluate effectiveness
		  - Compare effective sale price achieved to target
- Example protective put hedge:
	 - Sell 5 OTM 96 put options at premium of 2 points
	 - If rates rise,  puts increase in value to offset bond price drop
	 - Can lock in effective sale price close to target
- Hedging with futures options is complex with key parameters:
	 - Options premium cost
	 - Strike price choice
	 - Implied volatility of options
- Advantage vs futures hedge:
	 - Known,  limited downside risk
	 - Futures have unlimited downside risk
- Disadvantage vs futures:
	 - Options cost money,  futures are “free”
	 - Basis risk still present with options hedge

---

# THE BASIC HEDGING DECISION

- Hedging with futures can be viewed from two perspectives:
	 - Locking in the price or rate at which an anticipated future cash market transaction will occur. The goal is to eliminate the uncertainty over what price/rate will be received in the future.
	 - Substituting basis risk for price risk. Hedging reduces price risk but introduces basis risk,  which is uncertainty over the basis (price difference between cash and futures markets).
- Managers must make three key hedging decisions:
	 - What is the hedge target? The target should be based on the manager's view of fair forward values. There are two alternative target views:
		  1. Hedge targets the futures rate/price. This works only for hedges held to delivery date when the futures price converges to the cash market price.
				1. The manager can,  on average,  lock in the current spot rate for the security (i.e.,  current rate in the cash market).
		  1. Hedge targets the current spot rate/price. This works for hedges lifted before delivery date. Spot and futures prices likely converge over short horizon.
				1. The manager can,  on average,  lock in the rate at which the futures contracts are bought or sold.
	 - How many futures contracts should be used? This depends on the hedge ratio,  which is the optimal number of futures contracts to achieve the hedging objective.
	 - When should the futures contracts be removed? The manager must decide when is the optimal time to lift the hedge prior to futures contract expiration.

### THE HEDGING PROCESS CAN BE BROKEN DOWN INTO FOUR STEPS

- Step 1. Determining the appropriate hedging instrument
	 - A primary factor in determining which futures contract will provide the best hedge is the degree of correlation between the rate on the futures contract and the interest rate that creates the underlying risk that the manager seeks to eliminate.
		  - For example,  a long-term corporate bond portfolio can be better hedged with Treasury bond futures than with Treasury bill futures because long-term corporate bond rates are more highly correlated with Treasury bond futures than Treasury bill futures.
		  - Using the right delivery month is also important. A manager trying to lock in a rate or price for September will use September futures contracts because September futures contracts will give the highest degree of correlation.
		  - If the hedging program is of significant size,  liquidity becomes an important consideration and it might be necessary for the manager to spread the hedge across two or more different contracts.
- Step 2. Determining the target for the hedge
	 - Having determined the right contract and the right delivery months,  the manager then should determine what is expected from the hedge—that is,  what rate will,  on average,  be locked in by the hedge. This is the target rate or target price. If this target rate is too high (if hedging a future sale) or too low (if hedging a future purchase),  hedging may not be the right strategy for dealing with the unwanted risk.
- Step 3. Determining the position to be taken in the hedging instrument
- Step 4. Monitoring and evaluating the hedge
- Managers must make three key hedging decisions:

	 1. What is the hedge target?

	 - Target should be based on the manager's view of fair forward values

	 1. How many futures contracts should be used?

	 - Depends on the hedge ratio

	 1. When during the life of the hedge should the contracts be removed?
- Critical to define the hedge target properly to assess risk and expected return

## TARGETING THE FUTURES RATE/PRICE

### THE TARGET FOR HEDGES HELD TO DELIVERY

- Hedges that are held until the futures delivery date provide an example of a hedge that locks in the futures rate (i.e.,  the second view). The complication in the case of using Treasury bond futures and Treasury note futures to hedge the value of intermediateand long-term bonds is that because of the delivery options the manager does not know for sure when delivery will take place or which bond will be delivered. This is because of the delivery options granted to the short.
	 - Works only for hedges held to delivery date
	 - By convergence,  futures price = cash price of deliverable security
	 - Thus futures hedge locks in known futures price/rate
- **Example:** Hedging Treasury note using Treasury note futures contract

# TREASURY ISSUE HEDGE HELD TO DELIVERY

    - To illustrate how a Treasury bond futures held to the delivery date locks in the futures rate,  assume for the sake of simplicity that the manager knows which Treasury bond will be delivered and that delivery will take place on the last day of the delivery month.
    - Suppose that for delivery on the September 1999 futures contract,  the conversion factor for a deliverable Treasury issue is 1.283,  implying that the investor who delivers this issue would receive from the buyer 1.283 times the futures settlement price plus accrued interest.
    - An important principle to remember is that at delivery,  the spot price and the futures price times the conversion factor must converge.
        - Convergence refers to the fact that at delivery there can be no discrepancy between the spot price and futures price for a given security.
            - If convergence does not take place,  arbitrageurs would buy at the lower price and sell at the higher price and earn risk-free profits
    
    > Instrument to be hedged: $100 million 111/4% Treasury Bonds of 2/15/15  
    > Conversion factor for September 1999 = 1.283  
    > Price of futures contract when sold = 113  
    > Target price = (1.283 × 113) = 144.979  
    > Par value hedged = $100, 000, 000  
    > Number of futures contracts = 1, 283  
    > Futures position = Target = $144, 979, 000
    
    |   |   |   |   |   |   |
    |---|---|---|---|---|---|
    |(1)  <br>Actual Price for 11.25%  <br>T-Bonds|(2)  <br>Final Futures  <br>Price*|(3)  <br>Market Value of Treasury Bonds|(4)  <br>Value of Futures  <br>Position at Delivery Date|(5)  <br>Gain or Loss from Futures  <br>Positiont|(6)  <br>Effective  <br>Sale Pricet|
    |140|109.1192518|140, 000, 000|140, 000, 000|4, 979, 000|144, 979, 000|
    |141|109.898675|141, 000, 000|141, 000, 000|3, 979, 000|144, 979, 000|
    |142|110.6780982|142, 000, 000|142, 000, 000|2, 979, 000|144, 979, 000|
    |143|111.4575214|143, 000, 000|143, 000, 000|1, 979, 000|144, 979, 000|
    |144|112.2369447|144, 000, 000|144, 000, 000|979, 000|144, 979, 000|
    |145|113.0163679|145, 000, 000|145, 000, 000|-21, 000|144, 979, 000|
    |146|113.7957911|146, 000, 000|146, 000, 000|-1, 021, 000|144, 979, 000|
    |147|114.5752143|147, 000, 000|147, 000, 000|-2, 021, 000|144, 979, 000|
    |148|115.3546376|148, 000, 000|148, 000, 000|-3, 021, 000|144, 979, 000|
    |149|116.1340608|149, 000, 000|149, 000, 000|-4, 021, 000|144, 979, 000|
    |150|116.913484|150, 000, 000|150, 000, 000|-5, 021, 000|144, 979, 000|
    |151|117.6929072|151, 000, 000|151, 000, 000|-6, 021, 000|144, 979, 000|
    |152|118.4723305|152, 000, 000|152, 000, 000|-7, 021, 000|144, 979, 000|
    |153|119.2517537|153, 000, 000|153, 000, 000|-8, 021, 000|144, 979, 000|
    |154|120.0311769|154, 000, 000|154, 000, 000|-9, 021, 000|144, 979, 000|
    |155|120.8106002|155, 000, 000|155, 000, 000|-10, 021, 000|144, 979, 000|
    
    *By convergence,  must equal bond price divided by the conversion factor.
    
    $\text{Final Futures Price} = \text{Converted Price} $﻿
    
    - By Convergence,  $\text{Final Futures Price} = \text{Spot Price} \times \text{Conversion Factor}$﻿
    
    †Bond futures trade in even increments of 1/32. Accordingly,  the futures prices and margin flows are only approximate.
    
    ‡Transaction costs and the financing of margin flows are ignored.
    
    $\text{Converted Price} = \text{Spot Price} \times \text{Conversion Factor} $﻿
    
    **Final Futures Price  
    **The final futures price at the delivery date should equal the Treasury bond's actual sale price adjusted by the conversion factor. The adjustment formula is as follows:
    
    $\text{Final Futures Price} = \frac{\text{Treasury Bond's Actual Sale Price}}{\text{Conversion Factor}} $
    
    - Given that the conversion factor is 1.283 for the 111/4% Treasury issue and the actual sale price of the Treasury bond is $140,  we can calculate the final futures price as follows:
        - $\text{Final Futures Price} = \frac{140}{1.283} = 109.1193 $﻿
    
    **Market Value of Treasury Bonds  
    **The market value of the Treasury bonds is found by multiplying the actual sale price per $1 of par value by the $100 million par value:
    
    $\text{Market Value of Treasury Bonds} = \left(\frac{\text{Actual Sale Price}}{100}\right) \times \$100, 000, 000 $
    
    - $\text{Market Value of Treasury Bonds} = \left(\frac{140}{100}\right) \times \$100, 000, 000 = \$140, 000, 000$﻿
    
    **Value of the Futures Position at Delivery  
    **The value of the futures position at the delivery date is calculated using the final futures price,  the par value per contract of $100, 000,  and the number of futures contracts. In this illustration,  the number of futures contracts is 1, 283:
    
    $\text{Value of Futures Position} = \left(\frac{\text{Final Futures Price}}{100}\right) \times \$100, 000 \times \text{Number of Futures Contracts} $
    
    - $\text{Value of Futures Position} = \left(\frac{109.1193}{100}\right) \times \$100, 000 \times 1, 283 = \$140, 000, 062 $﻿
    
    **Gain or Loss from the Futures Position**
    
    - Recall that the futures contract was shorted. The futures price at which the contracts were sold was 113. Thus,  if the final futures price exceeds 113,  this means that there is a loss on the futures position—that is,  the futures contract is purchased at a price greater than for which it was sold. In con- trast,  if the futures price is less than 113,  this means that there is a gain on the futures position—that is,  the futures contract is purchased at a price less than for which it was sold
    
    $\text{Gain/Loss from Futures Position} = \left(\frac{113}{100} - \frac{\text{Final Futures Price}}{100}\right) \times \$100, 000 \times \text{Number of Futures Contracts} $
    
    - $\text{Gain or Loss from Futures Position} = \left(\frac{113}{100} - \frac{109.1193}{100}\right) \times \$100, 000 \times 1, 283 = \$4, 978, 938.1$﻿
    
    **Effective Sale Price for the Treasury Bond  
    **The effective sale price for the Treasury bond is obtained by adding the gain or loss from the futures position to the actual sale price of the Treasury bond:
    
    $\text{Effective Sale Price for Treasury Bond} = \text{Actual Sale Price of Treasury Bond} + \text{Gain or Loss from Futures Position}$
    
    $\text{Effective Sale Price for Treasury Bond} = \$140, 000, 000 + \$4, 978, 938.1 = \$144, 978, 938.1$﻿
    
    - The effective sale price for all the actual sale prices for the Treasury bond is the target price. However,  the target price is determined by the futures price,  so the target price may be higher or lower than the cash (spot) market price when the hedge is set.
    
### SOLUTION

    **Step 1: Sell futures contracts**
    
    - To lock in sale price,  sell futures contracts equal to:
        - Conversion factor x Par value of bonds
        - 1.283 x $100 million = $128.3 million
    - $128.3 million / $100, 000 per contract = 1, 283 contracts
    - Therefore,  sell 1, 283 Treasury bond futures contracts
    
    **Step 2: Calculate target price**
    
    - Sale price locked in = Futures price x Conversion factor
    - Futures price is 113
    - Conversion factor is 1.283
    - Therefore,  target price = 113 x 1.283 = $144.979
    
    **Step 3: Check convergence at delivery**
    
    - Actual Treasury bond sale price = $140
    - To satisfy convergence:
        - Actual sale price x Conversion factor = Final futures price
        - $140 x 1.283 = $109.119
    - Therefore,  final futures price must be 109.119
    
    **Step 4: Calculate gain/loss on futures**
    
    - Futures contracts sold initially at 113
    - Final futures price is 109.119
    - Gain per contract = 113 - 109.119 = 3.881
    - With 1, 283 contracts,  total futures gain is:
        - 3.881 x 1, 283 contracts = $4, 979, 000
    
    **Step 5: Determine effective sale price**
    
    $\text{Effective Sale Price} = \text{Actual Sale Price} + \text{Futures Gain/Loss}$﻿
    
    - Actual sale price of bonds = $140, 000, 000
    - Futures gain = $4, 979, 000
    - Therefore,  effective sale price = $140, 000, 000 + $4, 979, 000 = $144, 979, 000
    
    **Step 6: Confirm result**
    
    - Effective sale price = $144, 979, 000
    - This equals the target price calculated in Step 2
    - Therefore,  the futures rate is locked in
    
      
    

In summary,  if a manager establishes a futures hedge that is held until delivery,  the manager can be assured of receiving an effective price dictated by the futures rate (not the spot rate) on the day the hedge is set.

This example shows how a Treasury bond futures hedge set at 113 locks in a sale price of $144.979 regardless of the actual spot price at delivery.

- Gain or loss on futures offsets gain or loss on hedged security. Hedge locks in known futures delivery price

## TARGETING THE CURRENT SPOT RATE/PRICE

- When a manager must lift (remove) a hedge prior to the delivery date,  the effective rate that is obtained is much more likely to approximate the current spot rate than the futures rate the shorter the term of the hedge. The critical difference between this hedge and the hedge held to the delivery date is that convergence generally will not take place by the termination date of the hedge.
- When hedging,  a manager should not expect to lock in the futures rate (or price) just because he is hedging with futures contracts. The futures rate is locked in only if the hedge is held until delivery,  at which point convergence must take place. If the hedge is held for only one day,  the manager should expect to lock in the one-day forward rate,  which will very nearly equal the spot rate.
	 - View 2: Hedge targets the current spot rate/price
	 - Works for hedges removed before delivery date
	 - Spot price likely ≈ converted futures price in short hedges
	 - Thus locks in approximate current spot rate
- **Detailed Example:**
	 - Hedger owns$1 million face value of 6% Treasury note maturing on 6/30/99,  purchased at a discount to yield 6.5%
	 - Current spot price of the note =$88.50
	 - Current June 1999 Treasury note futures price = 96
	 - Cheapest-to-deliver (CTD) Treasury note into June 1999 contract is 6% of 8/15/99
		  - Conversion factor is 0.9605939
	 - Hedge will be lifted in 1 day
	 - In 1 day,  futures price likely ≈ current 96
	 - Thus,  target spot price = current spot price =$88.50
	 - To show the computations:
		  - Given:
				- Face value of Treasury note =$1, 000, 000
				- Current spot price =$88.50
				- Futures price = 96
				- Conversion factor for CTD note = 0.9605939
		  - Compute current spot price per$1 face value:
				-$88.50 /$1, 000, 000 =$0.0885
		  - Compute converted futures price per$1 face value:
				- Futures price = 96
				- Conversion factor = 0.9605939
				- Converted futures price per$1 face value:
					 - Futures price x Conversion factor
					 - 96 x 0.9605939 =$0.08858 (rounded)
		  - Current spot price per \$1 face value =$0.0885
		  - Converted futures price per \$1 face value =$0.08858
		  - The two values are approximately equal,  indicating that the current spot rate will be locked in by the hedge
- A short hedge locks in the approximate current spot price when lifted before delivery date
- Key points:
	 - Futures hedge removed before delivery locks in current spot rate/price,  not futures rate/price
	 - Converted futures price likely approximates spot price over short horizon
	 - Basis risk increases for longer-dated hedges

## HOW THE BASIS AFFECTS THE TARGET RATE FOR A HEDGE

- The proper target for a hedge that is to be lifted prior to the delivery date depends on the basis. The basis is simply the difference between the spot (cash) price of a security and its futures price; that is:
	 - Basis = spot price – futures price

### DEFINING THE BASIS

- Basis refers to the difference between spot and futures prices:
	 - Price basis = spot price - futures price
	 - Rate basis = spot rate - futures rate
- For bonds:
	 - Quoted futures price ≠ actual delivery price
	 - Must use futures _delivery_ price to calculate basis,  not quoted price
	 - Actual futures price = quoted futures price x conversion factor
- Basis should be defined in terms of:
	 - Rates (for understanding target effects)
	 - Prices (for projecting basis changes over time)

### TARGET RATE BASIS

- When a hedge is lifted prior to the delivery date,  one would not expect the basis to change very much in one day,  so the target rate basis equals the futures rate plus the current difference between the spot rate and futures rate,  that is,  the current spot rate.
- Target rate basis = expected rate basis when hedge is lifted
- Sets the hedge target rate:

$\text{Target rate for hedge} = \text{futures rate} + \text{target rate basis}$

- Similarly for price basis:

$\text{Target price for hedge} = \text{futures delivery price} + \text{target price basis}$

### BASIS RISK

- For the hedge held to delivery,  there is no uncertainty surrounding the target basis; by convergence,  the basis on the day the hedge is lifted is certain to be zero.
	 - For the short-lived hedge,  the basis probably will approximate the current basis when the hedge is lifted,  but its actual value is not known.
	 - For hedges longer than one day but ending prior to the futures delivery date,  there can be considerable basis risk because the basis on the day the hedge is lifted can end up being anywhere within a wide range.
	 - Thus the uncertainty surrounding the outcome of a hedge is directly related to the uncertainty surrounding the basis on the day the hedge is lifted (i.e.,  the uncertainty surrounding the target basis)
- The uncertainty about the value of the basis at the time the hedge is removed is called basis risk.
- For a given investment horizon,  hedging substitutes basis risk for price risk.
	 - Thus one trades the uncertainty of the price of the hedged security for the uncertainty of the basis. Consequently,  when hedges do not produce the desired results,  it is customary to place the blame on basis risk.
	 - Uncertainty about basis when hedge lifted = **basis risk**
	 - Basis risk reflects unpredictable changes in cash-futures price relationship
	 - **Key:** Define target basis properly to assess hedge risk

Determining the Number of Futures Contracts

### HEDGE RATIO

- Usually the hedge ratio is expressed in terms of relative par amounts. Accordingly,  a hedge ratio of 1.20 means that for every$1 million par value of securities to be hedged,  one needs$1.2 million par value of futures contracts to offset the risk
- Hedge ratio = number of futures contracts needed
- Sets target dollar duration = 0:

$\text{Number of futures contracts} = -\frac{\text{current dollar duration without futures}}{\text{dollar duration per futures contract}}$

### CROSS-HEDGE RATIO

- In bond portfolio management,  typically the bond or portfolio to be hedged is not identical to the bond underlying the futures contract. This type of hedging is referred to as cross-hedging
- Conceptually,  cross-hedging is somewhat more complicated than hedging deliverable securities because it involves two relationships. First,  there is the relationship between the cheapest-to-deliver (CTD) issue and the futures contract. Second,  there is the relationship between the security to be hedged and the CTD.
- The key to minimizing risk in a cross-hedge is to choose the right number of futures contracts. This depends on the relative dollar duration of the bond to be hedged and the futures position. The equation below indicated the number of futures contracts to achieve a particular target dollar duration. The objective in hedging is to make the target dollar duration equal to zero.
	 - Sets target dollar duration = 0

$\text{Number of futures contracts} = -\frac{\text{current dollar duration without futures}}{\text{dollar duration per futures contract}}$

- To calculate the dollar duration of a bond,  the manager must know the precise point in time that the dollar duration is to be calculated (because volatility generally declines as a bond matures),  as well as the price or yield at which to calculate dollar duration (because higher yields generally reduce dollar duration for a given yield change).
- The relevant point in the life of the bond for calculating volatility is the point at which the hedge will be lifted. Dollar duration at any other point is essentially irrelevant because the goal is to lock in a price or rate only on that particular day.
- Similarly,  the relevant yield at which to calculate dollar duration initially is the target yield.
- For non-deliverable (cross-hedge) security:

$\text{Number of futures contracts} = -\frac{\text{current dollar duration without futures}}{\text{dollar duration of CTD issue}} \&\times \text{conversion factor for CTD issue}$

- Accounts for dollar duration and conversion factor of CTD issue

|   |   |
|---|---|
|Date|6/24/99|
|Investment|$10 million par value of a 6.25% Fannie Mae (FNMA) option-free bond maturing on 5/15/29|
|Price of FNMA Bond|88.39|
|Yield of FNMA Bond|7.20%|
|Hedge Instrument|September 1999 Treasury bond futures|
|Price of Treasury Bond Futures|113|
|Cheapest to Deliver (CTD) Issue|11.25% of 2/15/15|
|Price of CTD Issue|146.19|
|Yield of CTD Issue|6.50%|
|Conversion Factor for CTD Issue|1.283|
|Assumption|Yield spread between the FNMA bond and the CTD issue remains at 0.70% (70 basis points)|
|Anticipated Sale Date|Last business day in September 1999|

# HEDGING A NONDELIVERABLE BOND TO A DELIVERY DATE WITH FUTURES

> Instrument to be hedged: $10 million FNMA 6.25% of 05/15/29 Price of FNMA as of hedge date (6/24/99) = 88.39 Conversion factor for September 1999 = 1.283
> Price of futures contract when sold = 113
> Target price for FNMA bonds = 87.76
> Par value hedged = $10, 000, 000
> Number of futures contracts = 112
> Futures position = $12, 656, 000
> Target market value for FNMA bonds = $8, 776, 000

|   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|
|(1)  <br>Actual  <br>Sale  <br>Price of  <br>FNMA  <br>Bonds  <br>8, 000, 000|(2)  <br>Yield at  <br>Sale  <br>8.027|(3)  <br>Yield of 11.25%  <br>Treasury  <br>Bond*  <br>7.327|(4)  <br>Price of 11.25%  <br>Treasury  <br>Bond  <br>135.813|(5)  <br>Futures  <br>Pricet  <br>105.85581|(6)  <br>Value of Futures  <br>Position  <br>11, 855, 850|(7)  <br>Gain or  <br>Loss on  <br>Futures  <br>Position  <br>800,  150|(8)  <br>Effective  <br>Sale  <br>Pricet  <br>8, 800,  150|
|8,  100, 000|7.922|7.222|137.031|106.80514|11, 962,  176|693, 824|8, 793, 824|
|8, 200, 000|7.818|7.118|138.234|107.74279|12, 067, 193|588, 807|8, 778, 807|
|8, 300, 000|7.717|7.017|139, 422|108.66875|12, 170, 899|485,  101|8, 785,  101|
|8, 400, 000|7.617|6.917|140.609|109.59392|12, 274, 519|381, 481|8, 781, 481|
|8, 500, 000|7.520|6.820|141.781|110.50740|12, 376, 829|279, 171|8, 779,  171|
|8, 600, 000|7.424|6.724|142.938|111.40920|12, 477, 830|178, 170|8, 778,  170|
|8, 700, 000|7.330|6.630|144.094|112.31021|12, 578, 744|77, 256|8, 777, 256|
|8, 800, 000|7.238|6.538|145.250|113.21122|12, 679, 657|-23, 657|8, 776, 343|
|8, 900, 000|7.148|6.448|146.391|114.10055|12, 779, 261|-123, 261|8, 776, 739|
|9, 000, 000|7.059|6.359|147.531|114.98909|12, 878, 778|-222, 778|8, 777, 222|
|9,  100, 000|6.972|6.272|148.656|115.86594|12, 976, 985|-320, 985|8, 779, 015|
|9, 200, 000|6.886|6.186|149.766|116.73110|13, 073, 883|-417, 883|8, 782,  117|
|9, 300, 000|6.802|6.102|150.875|117.59548|13, 170, 694|-514, 694|8, 785, 306|
|9, 400, 000|6.719|6.019|151.984|118.45986|13, 267, 504|-611, 504|8, 788, 496|
|9, 500, 000|6.637|5.937|153.078|119.31255|13, 363, 005|-707, 005|8, 792, 995|

*By assumption,  the yield on the cheapest-to-deliver issue is 70 basis points lower than the yield on the FNMA bond. †By convergence,  the futures price equals the price of the cheapest-to-deliver issue divided by 1.283 (the conversion factor).
‡Transaction costs and the financing of margin flows are ignored.

- **Example:** Hedging Fannie Mae (FNMA) bond with Treasury bond futures
	 - Hedging$10 million face value 6.25% FNMA bond maturing 5/15/29,  purchased to yield 7.2%
	 - September 1999 Treasury bond futures price = 113
	 - CTD issue = 11.25% of 2/15/15,  yield 6.5%,  conversion factor = 1.283
	 - Target yield for FNMA bond = 7.26%,  corresponding target price = 87.76
	 - Dollar duration per$100 face value:
		  - CTD issue =$6.255
		  - FNMA bond =$5.453
	 - Number of futures contracts = (-$10, 000, 000/$100 ×$5.453) / ($6, 255 × 1.283) = 112 contracts
- Calculate number of futures contracts:

$\text{Dollar duration without futures} = \text{\$10, 000, 000/100} \times \text{\$5, 453} = \text{\$545, 300}\\\text{Dollar duration of CTD issue} = \text{\$6, 255}\\\text{Conversion factor} = \text{1.283}\\\therefore \text{Number of futures contracts} = \frac{-\$545, 300}{\$6, 255} \times \text{1.283} = -112 \text{ contracts}$

---

### REFINING FOR CHANGING YIELD SPREAD

- Yield spreads between CTD issue and hedged bond change over time
- Use regression analysis to estimate relationship:

$\text{Yield on bond to hedge} = a + b \times \text{yield on CTD issue} + \text{error}$

- b = estimated relative yield change (yield beta)
- Adjust number of futures contracts:

$\text{Number of futures contracts} =\\ -\frac{\text{current dollar duration without futures}}{\text{dollar duration of CTD issue}} \times \text{conversion factor for CTD issue} \times \text{yield beta}$

- **Example:**
	 - Based on regression,  estimated yield beta = 1.05
	 - Without beta,  optimal futures contracts = 100 contracts
	 - With yield beta refinement:
		  - Number of futures contracts = 100 x 1.05 = 105 contracts

### MONITORING THE HEDGE

- Little need for active monitoring for most futures hedges
	 - Overactive adjustment often detrimental
	 - Typically best to let hedge run its course
	 - Not enough new information to change strategy
	 - Over management often hurts more than undermanagement
	 - But some adjustments may be warranted
- Exceptions:
	 - As rates change,  dollar durations change → hedge ratio may need adjustment
	 - Evidence of changed yield beta → may alter hedge ratio
- Best to stick with original hedge ratio in most cases

### EVALUATING THE COMPLETED HEDGE

- Evaluate after hedge is lifted to assess sources of error
- Assess how closely the target rate was achieved
- Compare outcome to no-hedge scenario to interpret errors
- Three major sources of hedging errors:
	 1. Incorrect dollar duration estimate
	 1. Inaccurate projected basis
	 1. Inaccurate regression estimates (yield beta)
- **Duration estimate errors:**
	 - Hedged security may have complex features not captured in duration model
	 - Example: embedded options throw off valuation under rate changes
- **Basis projection errors:**
	 - No simple satisfactory models to project basis changes
	 - Basis equilibrium relationships hard to model simply
	 - Basis modeling is a key challenge in effective hedging