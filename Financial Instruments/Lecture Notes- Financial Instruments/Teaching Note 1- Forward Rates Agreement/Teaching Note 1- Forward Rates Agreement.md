---
cssclasses: academia
linter-yaml-title-alias: LECTURE NOTE 1 FORWARD RATES AGREEMENT
title: Teaching Note 1Forward Rates Agreement
tags:
  - backwardation
  - commodity_forwards
  - contango
  - forward_curve
  - lease_rate
  - short_selling
  - storage_costs
aliases:
  - FRA
  - commodity forward
  - forward strip
key_concepts:
  - Commodity forward prices
  - Contango and backwardation
  - Equilibrium pricing
  - Lease rate definition
  - Short-selling commodity
---

# Teaching Note 1Forward Rates Agreement

%% Begin Waypoint %%

- **[[Teaching Note 1- Forward Rates Agreement]]**
	- [[Carry Trade]]
	- [[Ch1 Introduction to Derivative Markets]]
	- [[Contango And Backwardation In Arbitrage-Free Futures-Markets]]
	- [[Deriving Forward Exchange Rate Numerical Example]]
	- [[Foreign Exchange Quoting Conventions]]
	- [[Forward Contracts on Exchange Rates]]
	- [[Forwards and Futures Notes]]
	- [[Hedging Strategies with Forwards]]
	- [[Interest Rates,  Carry Trades,  and Exchange Rate Movements]]
	- [[Primary vs. Secondary Commodities]]
	- [[Teaching Note 1- Forward Rates Agreement]]

%% End Waypoint %%

[[Carry Trade]]

	- [[Ch1 Introduction to Derivative Markets]]

	- [[Chapter 6 (Hull) Hedging Strategies with Forwards]]

	- [[Deriving Forward Exchange Rate Numerical Example]]

	- [[Differences Between Co[[Primary vs. Secondary Commodities]]uoting Conventions]]

	- [[Forward Contracts on Exchange Rates]]

	- [[Forwards and Futures Notes]]

	- [[Hedging Strategies with Forwards]]

	- [[Financial Instruments/Lecture Notes/Teaching Note 1- Forward Rates Agreement/Interest Rates,       Carry Trades,       and Exchange Rate Movements]]

	- [[Teaching Note 1 Forward Rates Agreement]]

[PSET 1-Financial Instruments](PSET%201-Financial%20Instruments.md)

## INTRODUCTION TO COMMODITY FORWARDS

- Commodity forward prices can be described by the same formula as that for financial forward prices$$\begin{equation*}
	  F_{0,      T} = S_{0} e^{(r - \delta)T}
	 \end{equation*}$$

## INTRODUCTION TO COMMODITY FORWARD
- For financial assets,  $\delta$ is the dividend yield
- For commodities,  $\delta$is the commodity lease rate
	- The lease rate is the return that makes an investor willing to buy and then lend a commodity
	- The lease rate for a commodity can typically be estimated only by observing the forward prices
- Differences between commodities and financial assets include
	- Storage costs
	- Carry markets
	- Lease rate
	- Convenience yield
- The set of prices for different expiration dates for a given commodity is called the **forward rate** (or the **forward strip**) for that date
- If on a given date the forward curve is upward sloping,  then the market is in **contango**.
- If the forward curve is downward sloping,  the market is in **backwardation**
	- Note that forward curves can have portions in backwardation and portions in contango

## EQUILIBRIUM PRICING OF COMMODITY FORWARDS
- As with financial forwards,  the commodity forward price is a biased estimate of the expected spot price,  $E(S_{T})$,

  with the bias due to the risk premium on the commodity,  $r - \alpha$. (_**NB**_:$r - \alpha = -(\alpha - r)$).$$\begin{equation*}

	F_{0,      T} = E_{0}(S_{T})e^{-(\alpha - r)T}

  \end{equation*}$$

- The set of prices for different expiration dates for a given commodity is called the **forward curve** (or the
  **forward strip**) for that date
- If on a given date the forward curve is upward sloping,  then the market is in **contango**.
- If the forward curve is downward sloping,  the market is in **backwardation**
	- Note that forward curves can have portions in backwardation and portions in contango
- As with financial forwards,  the commodity forward price is a biased estimate of the expected spot price,
$E_{0}(S_{T})$,  with the bias due to the risk premium on the commodity,  $r - \alpha$. (Note that $r - \alpha =-(\alpha - r)$)

  $$F_{0,      T} = E_{0}(S_{T})e^{-(\alpha - r) T}$$

- Different commodities have their distinct forward curves,  reflecting different properties of
	- Storability
	- Storage costs
	- Production
	- Demand
	- Seasonality

## SHORT-SELLING AND THE LEASE RATE

- Suppose we engage in a reverse cash-and-carry for copper. The price of copper today is$\$3$and the price of copper in one year is$F_{0,  1}$. The risk-free rate is$10\%$.
- A copper borrower must make an extra payment,  a lease payment,  due to the difference in the current and forward prices.
- The lease rate is the difference between the commodity discount rate,  $\alpha$,  and the expected growth rate of the
  commodity price

$$\begin{equation*}
 \delta_{1} = \alpha - \frac{1}{T} \ln{\left[E_{0}(S_{T}) / S_{0}\right]}
\end{equation*}$$

- For a commodity owner who lends the commodity,       the lease rate is like a dividend
	* With the stock,       the dividend yield,       $\delta$,       is an observable characteristic of the stock
	* With a commodity,       the lease rate,       $\delta_{1}$,       is income earned only if the commodity is loaned. It is not
	  directly observable,       except if there is a lease market

## SHORT-SELLING AND THE LEASE RATE (CONT'D)

- The lease rate has to be consistent with the forward price
- Therefore,       when we observe the forward price,       we can infer what the lease rate would have to be if a lease market existed
- The annualized lease rate $$\begin{equation*}
     \delta_{1} = r - \frac{1}{T} \ln{F_{0,      T} / S}
    \end{equation*}$$

# PRICING COMMODITY FORWARDS BY ARBITRAGE

## NO-ARBITRAGE PRICING INCORPORATING STORAGE COSTS

- A commodity for which the forward price compensates a commodity owner for costs of storage is called a __carry market
- The cost of storing a physical item such as corn or copper can be large relative to its value
- Moreover,       some commodities deteriorate over time,       which is also a storage cost
- Cash-and-carry arbitrage when the storage costs from time $0$ to $T$ are $\lambda(0,      T)$
- $F_{0,      1}$ should not exceed $(1+R)S_{0} + \lambda(0,      1)$. If the forward price were greater,       you could undertake a
  simple cash-and-carry after paying storage costs and interest

- A copper borrower must make an extra payment,       a lease payment,       due to the difference in the current and forward prices.
- The lease rate is the difference between the commodity discount rate,       $\alpha$,       and the expected growth rate of the commodity price

$$\begin{equation*}
 \delta_{1} = \alpha - \frac{1}{T} \ln{\left[E_{0}(S_{T}) / S_{0}\right]}
\end{equation*}$$

- For a commodity owner who lends the commodity,       the lease rate is like a dividend
	* With the stock,       the dividend yield,       $\delta$,       is an observable characteristic of the stock
	* With a commodity,       the lease rate,       $\delta_{1}$,       is income earned only if the commodity is loaned. It is not
	  directly observable,       except if there is a lease market

- The lease rate has to be consistent with the forward price
- Therefore,       when we observe the forward price,       we can infer what the lease rate would have to be if a lease market existed
- The annualized lease rate $$\begin{equation*}
     \delta_{1} = r - \frac{1}{T} \ln{F_{0,      T} / S}
    \end{equation*}$$
## NO-ARBITRAGE PRICING INCORPORATING STORAGE COSTS (CONT'D)

- If $F_{0,      T}$ is greater than or equal to $(1+R)S_{0} + \lambda(0,      1)$ then storage will occur because the forward
  premium is great enough that sale proceeds in the future compensate for the financial costs of storage $(RS_{0})$ and the physical costs of storage ($\lambda(0,      1)$)
- When costly storage occurs,       the forward rate can rise faster than the interest rate
- We can view storage costs as a negative dividend
- Storage costs can include depreciation of the commodity,       which is less a problem for metals such as copper than it is for commodities such as strawberries or electricity
- If interest rates and storage costs are paid continuously and are proportional to the value of the commodity,       and there is no arbitrage

$$\begin{equation*}
 F_{0,      T} = S_{0} e^{(r + \lambda)T}
\end{equation*}$$

- If the forward price were greater,       you could undertake a simple cash-and-carry and earn a profit after paying both storage costs and interest on the position
- Some holders of a commodity receive benefits from physical ownership (e.g.,       a commercial user). This benefit is called the commodity's __convenience yield__
- If there is a continuously compounded convenience yield,       $c$,       then $$\begin{equation*}
     F_{0,      T} \ge S_{0}e^{(r + \lambda - c)T}
    \end{equation*}$$

- A user who buys and stores the commodity will be compensated for interest and physical storage costs less a convenience yield
- The commodity lease rate will be $\delta_{1} = c - \lambda$
### CORN
- Corn is harvested primarily in the fall. In order to be consumed when it is not produced,       it must be stored.
- In a typical year,       once the harvest begins,       storage is no longer necessary. Those storing corn will plan to deplete inventory as harvest approaches and to replenish inventory from the new harvest. The corn price will fall at harvest,      only to begin rising again after the harvest
### ENERGY MARKETS: ELECTRICITY
- Electricity has the following characteristics
	* It cannot be easily stored. Therefore,       it is not possible to engage in arbitrage
	* At any point in time,       the maximum supply of electricity is fixed
	* Demand for electricity varies substantially by season,       by day of week,       and by time of day

- Given these characteristics,       electricity forwards have large price swings over the day. Price swings reflect changes in the expected spot price,       which in turn reflects changes in demand over the day
### SYNTHETIC COMMODITIES

- A synthetic commodity can be created by combining a forward contract with a zero-coupon bond

| Investment strategy                                      | Cost at time 0  |                   Payoff at time T                    |
| -------------------------------------------------------- | :-------------: | :---------------------------------------------------: |
| A long commodity forward contract at the price $F_{0,      T}$ |       $0$       |                   $S_{T} - F_{0,      T}$                   |
| A zero-coupon bond that pays $F_{0,      T}$ at time T         | $F_{0,      T}/(1+R)$ |                       $F_{0,      T}$                       |
| Total                                                    | $F_{0,      T}/(1+R)$ | $S_{T} =$ the value unit of the commodity at time $T$ |