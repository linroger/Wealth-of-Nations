---
title: Credit Markets Session 4
---

# Credit Markets Session 4
## CALIBRATION AND MODEL PRICES
1. Recap: Parametric IR Models
	- Smooth yield curve models
	- The Nelson-Siegel model for smooth yield curves
	- The Nelson-Siegel-Svensson extension
1. Parametric Credit Models
	- What problem are we trying to solve?
	- Smooth Hazard Rate models
1. Calibration And Model Prices
	- Calibration results in hazard rate space
	- Model edges and alpha signals
	- Interpreting model results
1. Quant Credit Trading
	- Quantitative Trading Approach
	- Searching for alphas
	- Risk models
	- Portfolio construction
	- Strategy Backtesting

## US TREASURY YIELDS AS OF 2023-05-05

![](225b26a767221a869c20a844ff79ecdc.png)

MOTIVATION FOR "SMOOTH" US TREASURY CURVE

Observation: ~380 US cash treasury instruments (bills,  notes and bonds) actively traded in the market … quoted at different prices/yields,  based on coupon,  maturity and liquidity profile (~380 dimensional problem) Question: can we compute model prices for all US Treasuries using one sparse parametric model (dimensionality reduction)? Main idea: find a "smooth"/parametric spot/zero rates curve that best fits the market

## THE NELSON-SIEGEL MODEL FOR SMOOTH YIELD CURVES

The Nelson-Siegel '87 Model
Idea: decompose the spot/zero yield curve $y(\,  T)$ into 3 "basis function shapes":

Level: $$\theta_{1}\cdot1$$

Slope: $$\theta_{2}\cdot\frac{1-e^{-\,  T/\lambda}}{T/\lambda}$$

Curvature/"hump": $$\theta_{3}\cdot\left(\frac{1-e^{-\,  T/\lambda}}{T/\lambda}-e^{-\,  T/\lambda}\right)$$

- … and calibrate/control the yield curve shape via
	- "basis loadings" q1,  q2,  q3 parameters and
	- "curve location" l parameter
- Svensson '94 extension
	- added "second hump" shape: q4 ·

$${\frac{1-e^{-\,  T/\lambda_{2}}}{T/\lambda_{2}}}-e^{-\,  T/\lambda_{2}}$$

## NELSON-SIEGEL BASIS FUNCTIONS

![](2c2b5972e868740a1f11862ad6d83b5b.png)

The Nelson-Siegel model for smooth yield curves

## NELSON-SIEGEL CALIBRATION (US TREASURIES ON 2023-05-05)

![](d342c99a055cc3ffb8a44c55590c2183.png)

## NELSON -SIEGEL-SVENSSON BASIS FUNCTIONS

![](d04cf54c46c0dc59abc61043eeabb6ac.png)

## NELSON-SIEGEL-SVENSSON CALIBRATION (US TREASURIES ON 2023-05-05)

![](333decbe6d5db1897b671bcb15c425d0.png)

## VERIZON YIELDS VS TREASURIES VS SOFR SWAPS ON 2023-10-30

![](d6c511c3843236e954bbc44a40587e9b.png)
What problem are we trying to solve?

## VERIZON BOND US TREASURY G-SPREADS ON 2023-10-30

![](9b39d280b21bb5494545405eb62b0563.png)

## VERIZON BOND SOFR I-SPREADS ON 2023-10-30

![](7f4a50ea3ebd1e5c71d972828083eec0.png)
What problem are we trying to solve?

## MOTIVATION FOR "SMOOTH" CREDIT CURVES
- Verizon has about 60 actively traded USD cash corporate bonds
- … quoted at different prices/yields/spreads,  based on coupon,  maturity and liquidity profile
- Main idea: find a sparse parametric hazard rates curve model that best fits the market for VZ cash corporate bonds
- Reminder: corporate spreads capture the credit default risk only (they "live" on the top of US Treasury or SOFR curve)!
- Comment: corporate credit spread curves have "nice" curve shapes and should be "easier to model"
## NELSON-SIEGEL YIELD CALIBRATION FOR VERIZON BONDS ON 2023-10-30

![](bdc4b4faec673c05ff9d0de72d4df2ba.png)

## NELSON-SIEGEL G-SPREAD CALIBRATION FOR VERIZON ON 2023-10-30

![](c348a2cca3553a26f10b263281d41e95.png)

RECAP: PRICING RISKY INSTRUMENTS (CASH BONDS AND CDS)

- For a given issuer and seniority rank,  prices for all risky instruments (with known specs) can be computed from
- … the discount factor curve $DF(0,   T),   T ≥ t ≥ 0$,  calibrated to risk-free rates market (TSY & SOFR) and
- … the hazard rate curve $h(t,   T),   T ≥ t ≥ 0$.
- Very useful to think of "average" hazard rates $H(t,   T)$

$$H(t,  \,  T)=\frac{1}{T-t}\int_{t}^{T}h(t,  s)ds\tag{1}$$

$$SP(t,  \,  T)=\exp\left[(t-T)\cdot H(t,  \,  T)\right]\tag{2}$$

## IMPLEMENTING A "SMOOTH" CREDIT RISK MODEL

Main idea: use parametric form for average hazard rate curve as of time $t$

$$H(t,  T)=H(t,  T|\theta_{t})\tag{3}$$

Parameter vector $\theta_{t}$ controls the "shape" (level,  slope,  convexity,  etc) of the credit curve.
The implied parametric form for the survival probability curve is given by

$${\mathcal{S}}P(t,  T)={\mathcal{S}}P(t,  T|\theta_{t})=\exp\left[(t-T)\cdot H(t,  T|\theta_{t})\right]\tag{4}$$

![](9877b9bbc57ca3163a1e0785f4f9bbd9.png)

![](a9826267ca8e8fbc2111f8621df36bf1.png)
q1 = 3%,  q2 = −1%,  q3 = −0.1%,  l = 5 q1 = 3%,  q2 = −1%,  q3 = −0.1%,  l = 5

## IMPLEMENTATION/CALIBRATION OF SMOOTH CREDIT RISK MODEL
- For a given issuer and seniority rank,  collect market prices for all bonds and CDS at time $t$.
- For each instrument,  determine calibration weights based on liquidity and riskiness,  e.g. $w_i = \frac{"*LiqScore_i"}{DV 01_i}$
- Model calibration consists of minimizing the SSE ("Sum of Squared Errors") between model and market prices:

$$SSE(t,  \theta):=\sum_{i=1}^{N}w_{i}\cdot\left|MarketPrice_{t}^{i}-ModelPrice_{t}^{i}(\theta)\right|^{2},  \tag{5}$$

$$\theta_{t}^{*}=\begin{array}{c}\mbox{\it argmin}\\ \theta\end{array}\left\{SSE(t,  \theta)\right\}\tag{6}$$

## NELSON-SIEGEL CALIBRATION: VERIZON G-SPREADS

![](6c276589e0eda536ed419a27c5ed7850.png)

## NELSON-SIEGEL CALIBRATION: VERIZON YIELDS

![](6e41901458bfb2f3e217464b9b0e4775.png)

ASSESSING MODEL CALIBRATION RESULTS

- Differences between model and market prices are called "model edges"
- "Model edges" can be converted from price into yield or spread space,  by using DV01/sensitivities
- Can we think of the calibrated model prices as "fair prices" for the given instruments,  at least on a relative basis?
- Is there an "economic interpretation" to our "fair prices" assumption above,  outside of our model?

## NELSON-SIEGEL CALIBRATION: VERIZON G-SPREAD EDGES

![](b29e010516883f76be52d53d15b40ef2.png)

## NELSON -SIEGEL: EDGE TIME SERIES FOR VERIZON BOND

![](00b7eff8428d7c53102785b13ed2c422.png)

VISUALIZING SMOOTH MODEL CURVES

- Once the credit curve model is calibrated,  we obtain
	- the smooth Yield or G-Spread surfaces for the issuer (across coupon and maturities)
	- and model prices of any CDS or bond: existing or "new issue"
- Intuitive way to visualize the dynamics of curve shapes through time
	- create hypothetical/synthetic bond for standardized maturities: 2Y,  3Y,  5Y,  7Y,  10Y,  20Y and 30Y
	- issued at "par price": bond coupon = bond yield Plot yields and g-spreads time series

## VERIZON "SMOOTH"/MODEL YIELD SURFACE

![](b8b194732e96b7b0778edf6fdc91e23a.png)

## VERIZON "SMOOTH"/MODEL G-SPREAD SURFACE

![](43eff7a89ad965492c316e106913dc31.png)

## VERIZON "SMOOTH"/MODEL I-SPREAD SURFACE

![](b61a23994ba94ca90e3d3ceaae848d4a.png)

## TIME SERIES OF VERIZON "SMOOTH" CREDIT CURVES

![](63f8bcaa7f8a7859ff40c1b18c1b2f58.png)

## FROM MODEL EDGES TO TRADING STRATEGIES
- Assuming we do have the "fair price" of securities
	- can we construct a portfolio strategy (e.g. pairs trading) of "edge dislocated" instruments with an "above average" strategy PnL?
- Is this a "pure arbitrage" or a "statistical arbitrage" strategy?
- Is the strategy executable: liquidity,  transaction costs,  capacity,  cost of financing,  etc?
- Can we validate via strategy simulation/backtesting?

#### QUANT TRADING
- use technology + math + automation for investment decisions
- little human interaction "at run-time"
#### METHODS
- calibrate models to identify "edges"/alphas
- evaluate strategy performance via backtesting
- select optimal model parameters
#### GOALS
- maximizing alpha capture: PnL,  Sharpe/Sortino ratios
- while minimizing risk: low factor risks,  limited portfolio draw-downs

## IG BOND MARKET (~15K BONDS): G-SPREADS BY TTM AND LIQUIDITY

![](9937f66b3808b4ca03c86812cf270947.png)

"FAIR" PRICES,  MARKET PRICES AND EDGES

- use quant models to estimate "fair" value of securities
- "edge"/"alpha" = temporary dislocations between fair and market prices
- alpha raw metrics: current edge dislocation,  estimated edge volatility
- alpha convergence metrics: stationarity,  mean-reversion speed and signal half-life

## RISK MODELS
- Joint securities dynamics decomposed into
	- factors risks
	- idiosyncratic risks
- Portfolio factor risks aggregated at portfolio level via "betas"/factor loadings
- Knowledge of factor Co-Variance matrix & individual "idio" vols enables risk predictions on portfolio level

#### RISK MODEL: EXAMPLES

MARKET OBSERVABLE RISK FACTORS

- Interest Rates: DV01,  IR01
- Credit Default: CS01,  Gamma,  Jump-To-Default
- Liquidity
#### CROSS-SECTIONAL REGRESSION MODELS
- BARRA-style models
- known factor loadings,  regressed returns
#### STATISTICAL RISK FACTORS
- PCA factor models

## PORTFOLIO CONSTRUCTION: INGREDIENTS
- Alpha signals
	- multiple edges can be "mixed" into aggregated edge
- Risk model(s)
- Transaction costs model
- Portfolio constraints (notional and risk limits)
- Numerical optimizer (linear-quadratic/convex optimization)

## EXPECTED UTILITY OPTIMIZATION FORMULA
- Maximize total alpha capture,
- penalize risk/variance and "re-balancing volume"
- … while taking into account position and risk constraints
- … and transaction costs

## STRATEGY BACKTESTING
- For a given set of model parameters,  implement a simulator/backtester of the strategy Positions/PnL/Volume metrics on historical data
- Run the strategy backtests on a (multi-dimensional) grid of the model parameter space
- Analyze the results and decide the optimal model parameters,  to be used in "production" trading
- Adjust the production/optimal model parameters based on LIVE trading feedback,  in order to maximize the strategy performance

## STRATEGY BACKTEST EXAMPLE: 2D PARAMETER GRID SEARCH

![](2ac231018a3f33f9b809d64e88ee839d.png)

## Q &A

PARAMETRIC YIELD CURVE MODELS

- Recap: parametric interest rate models
- Nelson-Siegel models for smooth yield curves
- Parametric models for smooth hazard rate curves
QUANTITATIVE CREDIT TRADING
- Alpha and Risk models
- Portfolio construction
- Strategy backtesting
