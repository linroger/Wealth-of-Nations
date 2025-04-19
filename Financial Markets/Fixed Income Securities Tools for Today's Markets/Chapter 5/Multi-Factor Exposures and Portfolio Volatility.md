---
tags:
  - interest_rate_risk
  - portfolio_volatility
  - principal_component_analysis
  - regression_hedging
  - risk_metrics
aliases:
  - Multi-Factor Exposures
  - Portfolio Volatility
key_concepts:
  - Hedging interest rate risk
  - Principal component analysis (PCA)
  - Quantifying portfolio volatility
  - Term structure of interest rates
  - Two-variable regression hedging
---

# 5.7 MULTI-FACTOR EXPOSURES AND PORTFOLIO VOLATILITY  

As discussed in this chapter and Chapter 4, risk metrics are useful for quantifying the effect of a change in rates on prices and for hedging interest rate risk. This section makes the point that risk metrics are also useful for quantifying portfolio volatility.  

Say that a portfolio has a DV01 of $\$10,000$ and that interest rates have a volatility of 100 basis points per year. It follows that the portfolio has an annual volatility of $\$10,000$ times 100, or $\$1$ million. This, of course, is a one-factor formulation of interest rate volatility.  

The motivation for multi-factor exposures, however, is that portfolios. are exposed to changes in interest rates all along the curve and that these changes are not perfectly correlated. The discussion here quantifies portfolio. volatility in the simple, multi-factor setting of two key rates. The ideas, however, are easily extended to additional key rates and to partial and forward-bucket $^{\circ_{01s}}$  

To estimate portfolio volatility with two key rates, follow these steps. First, empirically estimate the volatility of changes in each key rate and the correlation between them. Second, compute the key-rate $^{\ '}01s$ of the portfolio. Third, compute the variance or volatility of the portfolio. To illustrate this third step, denote the change in the value of the portfolio by $\Delta P$ ; the change in the two key rates by. $\Delta y_{1}$ and $\Delta y_{2}$ ; and the key rates of the portfolio. by $K R01_{1}$ and $K R01_{2}$ . Then, by the definition of key-rate. $^{\ '}01s$  

$$
\Delta P\approx K R01_{1}\times\Delta y_{1}+K R01_{2}\times\Delta y_{2}
$$  

Furthermore, denoting the volatility of changes in portfolio value and changes in the two key rates by $\sigma_{P},\sigma_{1}$ , and $\sigma_{2}$ , respectively, and the correlation between changes in the key rates by $\rho$ , Equation (5.14) and the rules for computing variances and standard deviations imply that,  

$$
\sigma_{P}\approx\sqrt{K R01_{1}^{2}\sigma_{1}^{2}+K R01_{2}^{2}\sigma_{2}^{2}+2K R01_{1}K R01_{2}\rho\sigma_{1}\sigma_{2}}
$$  

Of course, as the number of key rates or, more generally, factors, increases, more volatility and correlation inputs are required..  

# Regression Hedging and. Principal Component Analysis  

across rates of different terms. The assumptions are typically motivated by a combination of economic theory, empirical analysis of historical data, and views about future economic and financial developments. This chapter introduces approaches that rely explicitly on historical data. It would be an oversimplification, however, to categorize the techniques of Chapters 4 and 5 as subjective, while categorizing the approaches of this chapter as objective. Empirical methods also require assumptions, such as the number of rates or instruments used in the analysis, the particular rates or instruments chosen, and the historical time period selected for estimation.  

The first section of this chapter describes single-variable regression hedging in the context of hedging a 40-year Johnson $\&$ Johnson (JNJ) bond with a 30-year Treasury. The second section describes two-variable regression hedg. ing in the context of a relative value trade of 20-year versus 10- and 30-year Treasuries. The third and fourth sections discuss two other issues that arise in the context of regression hedging, namely, the choice between level and change regressions, and reverse regressions.  

One conceptual problem with using regression hedging in practice is that each regression is essentially a different model of the term structure of interest rates with different underlying assumptions. Consider, for example, the manager of a trading desk in which some traders are using singlevariable regressions and some two-variable regressions, or some are estimating regressions from one month of historical data and others from six months.  

The final section of the chapter introduces a unified empirical description of how the entire term structure evolves, namely, principal component analysis (PCA). PCA provides both an empirical hedging methodology, which can be used consistently across the term structure, along with easily interpreted descriptions of how the term structure fluctuates over time. While presentations of PCA tend to be highly mathematical, great effort has been made in this chapter to make the material more broadly accessible.  
