---
linter-yaml-title-alias: GOVERNMENT OF CANADA BOND FUTURES
title: Carry Trade
tags:
  - arbitrage
  - carry_trade
  - futures_market
  - market_neutral
  - spot_market
aliases:
  - Cash-and-Carry
  - Reverse Carry Trade
key_concepts:
  - Arbitrage strategy
  - Contango and backwardation
  - Futures vs spot prices
  - Market neutral strategy
  - Profit from price spread
---

[Lecture Note 1- Forward Rates Agreement](Lecture%20Note%201-%20Forward%20Rates%20Agreement.md)
[Teaching Note 2-Futures Contracts](Teaching%20Note%202-Futures%20Contracts.md)
[Currency Forward](Currency%20Forward.md)

[[Carry Trade]]
	- [[Ch1 Introduction to Derivative Markets]]
	- [[Chapter 6 (Hull) Hedging Strategies with Forwards]]
	- [[Deriving Forward Exchange Rate Numerical Example]]
	- [[Primary vs. Secondary Commodities]]
	- [[Foreign Exchange Quoting Conventions]]
	- [[Forward Contracts on Exchange Rates]]
	- [[Forwards and Futures Notes]]
	- [[Hedging Strategies with Forwards]]
	- [[Financial Instruments/Lecture Notes/Teaching Note 1- Forward Rates Agreement/Interest Rates,     Carry Trades,     and Exchange Rate Movements]]
	- [[Teaching Note 1 Forward Rates Agreement]]

## WHAT IS A CARRY TRADE?

A [Interest Rates,  Carry Trades,  and Exchange Rate Movements](Asset%20Classes/Derivatives/Forward%20and%20Futures/Forward%20Exchange%20Rate%20Contracts/Foreign%20Exchange%20Notes/Interest%20Rates,  %20Carry%20Trades,  %20and%20Exchange%20Rate%20Movements.md) is a form of arbitrage that takes advantage of price discrepancies between futures and spot prices. When performing a [Interest Rates,  Carry Trades,  and Exchange Rate Movements](Asset%20Classes/Derivatives/Forward%20and%20Futures/Forward%20Exchange%20Rate%20Contracts/Foreign%20Exchange%20Notes/Interest%20Rates,  %20Carry%20Trades,  %20and%20Exchange%20Rate%20Movements.md),  the trader will take a position in the spot market and simultaneously take the opposite position in the futures market. Since one leg makes money as the other loses money,  the strategy is referred to as “market neutral.” When trading a market-neutral strategy,  the trader doesn’t care which direction the underlying asset’s price moves. 

The strategy’s profitability relies on the fact that futures contracts are often priced above or below the spot price. A futures contract’s price represents a market’s perception of where its underlying asset is heading by its settlement date. Therefore,  futures prices often drift from the current spot price,  presenting an opportunity to profit with relatively little risk. 

When the spot price is below the futures price,  the market is said to be in _contango_,  and a [Interest Rates,  Carry Trades,  and Exchange Rate Movements](Asset%20Classes/Derivatives/Forward%20and%20Futures/Forward%20Exchange%20Rate%20Contracts/Foreign%20Exchange%20Notes/Interest%20Rates,  %20Carry%20Trades,  %20and%20Exchange%20Rate%20Movements.md) will often result in profits. When the opposite is true,  the market is said to be in _backwardation_,  and a reverse [Interest Rates,  Carry Trades,  and Exchange Rate Movements](Asset%20Classes/Derivatives/Forward%20and%20Futures/Forward%20Exchange%20Rate%20Contracts/Foreign%20Exchange%20Notes/Interest%20Rates,  %20Carry%20Trades,  %20and%20Exchange%20Rate%20Movements.md) (i.e.,  shorting in the spot market and longing the futures contract) will be a more favorable strategy. 

When performing a [Interest Rates,  Carry Trades,  and Exchange Rate Movements](Asset%20Classes/Derivatives/Forward%20and%20Futures/Forward%20Exchange%20Rate%20Contracts/Foreign%20Exchange%20Notes/Interest%20Rates,  %20Carry%20Trades,  %20and%20Exchange%20Rate%20Movements.md),  a trader will look for as wide a spread as possible between the spot price and futures price. As settlement approaches,  this spread will naturally narrow because the time in which the spot price can increase or decrease reduces. By settlement,  the two prices will have converged. The trader can close both positions for a profit whenever the spread is narrower than it was at entry. 

Alternatively,  a trader who settles the futures leg of a [Interest Rates,  Carry Trades,  and Exchange Rate Movements](Asset%20Classes/Derivatives/Forward%20and%20Futures/Forward%20Exchange%20Rate%20Contracts/Foreign%20Exchange%20Notes/Interest%20Rates,  %20Carry%20Trades,  %20and%20Exchange%20Rate%20Movements.md) can opt to “roll over” their trade to a later-dated futures contract. If there is a wide spread between the spot price and a longer-term contract when closing the first futures position,  simply shorting the further out contract and continuing to hold the spot position will create a new [Interest Rates,  Carry Trades,  and Exchange Rate Movements](Asset%20Classes/Derivatives/Forward%20and%20Futures/Forward%20Exchange%20Rate%20Contracts/Foreign%20Exchange%20Notes/Interest%20Rates,  %20Carry%20Trades,  %20and%20Exchange%20Rate%20Movements.md) with a new settlement date.

---
#### REVERSE CASH-AND-CARRY ARBITRAGE

A reverse cash-and-carry arbitrage is the exact opposite to a cash-and –carry transaction. Instead of buying the underlying security because it is underpriced,  you sell it short (because it is overpriced),  take the proceeds and go long a futures position on the underlying security. Before the futures position expires you close out the position by taking delivery and returning the borrowed shares you were short.

---
# Carry Trade

## MONTRÉAL EXCHANGE: CASH-AND-CARRY TRADE

A bond trader notes that the price relationship between the CTD Can 2% December 1,  2051 bond and the LGB contract is out-of-line.

The trader’s observation is supported by:

1. An actual repo rate (0.20%) that is lower than the repo rate (1.85%) implied by the price of the LGB contract—a condition that provides a trader an arbitrage profit by initiating a cash-and-carry trade (whereby the trader sells bond futures and finances the purchase of the cash bond at a rate below the rate implied by the futures price). The bond is then held until it is delivered to fulfill the obligation of the sale of the futures contract; and
1. A net basis (basis after carry) reflecting that the actual LGB contract is overpriced relative to its theoretical fair value.

| Specification | Value |
| ---- | ---- |
| Last Delivery Day | 2022-03-31 |
| Price of LGB Contract | 220.72 |
| Valuation Date | 2021-11-18 |
| Coupon | 2% |
| Maturity | December 2051 |
| Bond Price | 98.964 |
| Conversion Factor | 0.4481 |
| Implied Repo | 1.85% |
| Actual Repo | 0.20% |
| Net Basis | -0.595 |
|  |  |

| Setting                                           | Value      |
|---------------------------------------------------|------------|
| Price of the CTD Can 2% December 1,     2051 bond     | 98.964     |
| Accrued interest: (170/365) x 2                   | 0.932      |
| (170 days = June 1 to November 18 settlement date)|            |
| Financing rate (actual repo rate)                 | 0.20%      |
| Conversion factor                                 | 0.4481     |
| Price of the LGB contract                         | 220.72     |
| Days from settlement to futures delivery          | 133        |
| (November 18 to March 31)                        |            |
| Days from next coupon to futures delivery         | 120        |
| (December 1 to March 31)                          |            |

### LGB MARCH 2022

- **Last Delivery Day:** 2022-03-31
- **Price of LGB Contract:** 220.72
- **Valuation Date:** 2021-11-18

#### COUPON MATURITY BOND PRICE
- **Conversion Factor:** 0.4481
- **Implied Repo:** 1.85%
- **Actual Repo:** 0.20%
- **Net Basis:** -0.595

#### SETTING

- **Price of the CTD Can 2% December 1,  2051 bond:** 98.964
- **Accrued interest:** (170/365) x 2 (170 days = June 1 to November 18 settlement date)
- **Financing rate (actual repo rate):** 0.20%
- **Conversion factor:** 0.4481
- **Price of the LGB contract:** 220.72
- **Days from settlement to futures delivery (November 18 to March 31):** 133
- **Days from next coupon to futures delivery (December 1 to March 31):** 120

The trader initiates a cash-and-carry trade that involves the following steps:

1. Pay for the purchase of the CTD bond (bond price + accrued interest).
1. Finance the bond purchase at the current short-term financing rate (actual repo rate).
1. Receive any intervening coupon plus reinvestment income during the life of the futures contract.
1. Receive the futures invoice price + intervening coupon accrued interest from delivering the bond (i.e.,  collect the anticipated receipt from delivering bond to the buyer).
1. Repay the cash amount borrowed to purchase the CTD bond + interest.
1. Calculate arbitrage profit.

### CASH-AND-CARRY TRANSACTION AMOUNT

(per$100,  000.00 notional amount)

- **Purchase the CTD bond:**$98,    964 +$932 =$99,  896 (Price of bond + Accrued interest)
- **Financing costs until LGB delivery:**$99,    896 x 0.0020 x 133/365 =$73 (Amount borrowed to buy bond × Short-term financing rate × Number of days/365)
- **Income during the life of the LGB contract:**$1,    000 + ($1,  000 x 0.0020 x 120/365) = C$1,  001 (Coupon income + (Coupon income × Short-term financing rate × Number of days/365))
- **Total costs of the bond position:**$99,    896 +$73 -$1,    001 = C$98,  968 (Investment + Financing - Income)

### DELIVERY PRICE OF THE DELIVERABLE BOND AT LGB FUTURES DELIVERY

($220,    720 x 0.4481) +$658* =$99,    563 (*$100,  000 x 2% coupon x 30/365)

- Futures invoice price × Conversion factor + Accrued interest received by the seller from the bond buyer

### ARBITRAGE PROFIT (PER LGB FUTURES)

$99,    563 -$98,  968 =$595 (Delivery price of the deliverable bond - Total costs of the bond position)

In the present strategy the cash-and-carry transaction results in a profit of$595 per contract.

# CASH-AND-CARRY TRANSACTION

(per$100,  000.00 notional amount)

| Item                                   | AMOUNT                                      | COMMENTS                                                        |
|----------------------------------------|---------------------------------------------|-----------------------------------------------------------------|
| Purchase the CTD bond                  |$98,    964 +$932 =$99,    896                    | Price of bond + Accrued interest                                |
| Financing costs until LGB delivery     |$99,    896 x 0.0020 x 133/365 =$73            | Amount borrowed to buy bond × Short-term financing rate × Number of days/365 |
| Income during the life of the LGB contract (credit and reinvestment of the coupon: December 1 to March 31) |$1000 + ($1000 x 0.0020 x 120/365) = C$1001 | Coupon income + (Coupon income × Short-term financing rate × Number of days/365) |
| Total costs of the bond position       |$99,    896 +$73 -$1001 = C$98,    968            | Investment + Financing - Income                                 |
| Delivery price of the deliverable bond at LGB futures delivery | ($220,    720 x 0.4481) +$658* =$99,    563       | Futures invoice price × Conversion factor + Accrued interest received by the seller from the bond buyer |
| Arbitrage profit (per LGB futures)     |$99,    563 -$98,    968 =$595                    | Delivery price of the deliverable bond - Total costs of the bond position |

- $100,  000 x 2% coupon x 30/365
