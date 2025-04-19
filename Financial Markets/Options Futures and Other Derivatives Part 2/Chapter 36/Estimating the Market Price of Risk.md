---
tags:
  - capital_asset_pricing_model
  - historical_analysis
  - investment_asset
  - market_price_risk
  - risk_neutral_world
aliases:
  - CAPM
  - MPR
  - Market Price of Risk
key_concepts:
  - Estimating market price of risk
  - Historical data correlation
  - Investment asset return
  - Real-options approach
  - Risk-neutral process
---

# 36.3 ESTIMATING THE MARKET PRICE OF RISK  

The real-options approach to evaluating an investment avoids the need to estimate riskadjusted discount rates in the way described in Section 36.1, but it does require market price of risk parameters for all stochastic variables. When historical data are available for a particular variable, its market price of risk can be estimated using the capital asset pricing model. To show how this is done, we consider an investment asset dependent solely on the variable and define:  

$\mu$ : Expected return of the investment asset $\sigma$ : Volatility of the return of the investment asset $\lambda$ : Market price of risk of the variable $\rho$ : Instantaneous correlation between the percentage changes in the variable and returns on a broad index of stock market prices   
$\mu_{m}$ : Expected return on broad index of stock market prices   
$\sigma_{m}$ : Volatility of return on the broad index of stock market prices $r$ :Short-term risk-free rate  

Because the investment asset is dependent solely on the market variable, the instantaneous correlation between its return and the broad index of stock market prices is also $\rho$ . From a continuous-time version of the capital asset pricing model, which is. presented in the appendix to Chapter 3,2  

$$
\mu\textrm{--}r=\frac{\rho\sigma}{\sigma_{m}}(\mu_{m}\textrm{--}r)
$$  

From equation (36.1), another expression for $\mu\mathrm{~-~}r$ is  

$$
\mu\mathrm{~-~}r=\lambda\sigma
$$  

It follows that  

$$
\lambda=\frac{\rho}{\sigma_{m}}(\mu_{m}-r)
$$  

This equation can be used to estimate $\lambda$  

# Example 36.2  

A historical analysis of company's sales, quarter by quarter, show that percentage changes in sales have a correlation of 0.3 with returns on the S&P 500 index. The volatility of the S&P 500 is $20\%$ per annum and based on historical data the expected excess return of the S&P 500 over the risk-free rate is $5\%$ . Equation (36.2) estimates the market price of risk for the company's sales as  

$$
\frac{0.3}{0.2}\times0.05=0.075
$$  

When no historical data are available for the particular variable under consideration, other similar variables can sometimes be used as proxies. For example, if a plant is being constructed to manufacture a new product, data can be collected on the sales of other similar products. The correlation of the new product's price with the market index can then be assumed to be the same as that of these other products. In some cases, the estimate of $\rho$ in equation (36.2) must be based on subjective judgment. If an analyst is convinced that a particular variable is unrelated to the performance of a market index, its market price of risk should be set to zero.  

For some variables, it is not necessary to estimate the market price of risk because the process followed by a variable in a risk-neutral world can be estimated directly. For example, if the variable is the price of an investment asset, its total return in a riskneutral world is the risk-free rate. If the variable is the short-term interest rate. $r$ Chapter 31 shows how a risk-neutral process can be estimated from the initial term structure of interest rates.  

For commodities, futures prices can be used to estimate the risk-neutral process, as. discussed in Chapter 35. Example 35.2 provides a simple application of the real options approach by using futures prices to evaluate an investment involving the breeding of cattle.  
