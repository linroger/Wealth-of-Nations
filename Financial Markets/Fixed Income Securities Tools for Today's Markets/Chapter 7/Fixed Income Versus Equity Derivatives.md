---
tags:
  - black_scholes_merton
  - bond_pricing
  - equity_derivatives
  - fixed_income
  - interest_rates
aliases:
  - BSM Model
  - Bond Option Pricing
  - Fixed Income vs. Equity Derivatives
key_concepts:
  - BSM option pricing
  - Bond price convergence
  - Interest rate volatility
  - Short-term rate modeling
  - Term structure evolution
---

# 7.9 FIXED INCOME VERSUS EQUITY DERIVATIVES  

The famous Black-Scholes-Merton (BSM) pricing analysis of stock options can be summarized as follows. Under the assumptions that the stock price evolves according to a particular random process and that the short-term interest rate is constant, it is possible to form a portfolio of the underlying stock and short-term bonds that replicates the option. Therefore, by arbitrage arguments, the price of the option equals the price of the replicating portfolio.  

Consider applying this logic to price an option on a five-year bond. The.   
starting point might be an assumption about how the price of the five-year.   
bond evolves over time, but the task is considerably more complicated than.   
for the price of a stock. First, the price of a bond converges to its face value.   
at maturity, while the stock price has no similar constraint. Second, because of the maturity constraint, the volatility of a bond's price must decline as the.  

bond approaches maturity. Hence, the simple assumption that the volatility of a stock is constant is not as appropriate for bonds. Third, because stock volatility is very large relative to short-term rate volatility, it is often acceptable to assume that the short-term interest rate is constant. By contrast, it seems inconsistent to assume that bond prices - which depend on interest rates - follow some random process, while assuming that the short-term interest rate is constant.  

These objections led researchers to make assumptions about the random. evolution of the interest rate rather the bond price. In that way, bond prices naturally approach par, price volatilities naturally approach zero, and no interest rate is assumed to be constant. But this approach raises another set of questions. Which interest rate is assumed to evolve in a particular way? Assumptions about the five-year spot rate, for example, are not sufficient for two reasons. First, five-year coupon bond prices depend on shorter-term. spot rates as well. Second, an option on a particular five-year bond soon depends on the prices of a bond that is no longer a five-year bond, but a bond with slightly less time to maturity. Therefore, assumptions usually have to be made about the evolution of the entire term structure of interest rates to price bond options and other derivatives. This chapter shows that, in a one-factor model, assumptions about the evolution of the short-term rate are sufficient to model the evolution of the entire term structure..  

In short, there are several arguments to move beyond BSM in the fixed. income context. Nevertheless, for simplicity, practitioners do use versions of BSM to price and hedge several classes of fixed income derivatives. These. methodologies are described at length in Chapter 16..  

# Expectations, Risk Premium, Convexity, and the Shape of the Term Structure  

tions about the evolution of the short-term rate and by assumptions about the risk premium demanded by investors for bearing interest rate risk. The first few sections of the chapter present concepts by way of example, in the simple, binomial tree framework of the previous chapter. The last section of the chapter presents the same ideas in more general setting, though at the cost of some higher-level mathematics. Chapter 9 concludes the presentation of term structure models with a detailed description of two well-known models.  
