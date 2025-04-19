---
tags:
  - defined_benefit
  - investment_strategy
  - pension_funds
  - risk_allocation
  - sovereign_funds
aliases:
  - Pension Fund Risk
  - Risk Management
  - Sovereign Fund Risk
key_concepts:
  - Alternative investments
  - Defined benefit plans
  - Pension fund investment
  - Risk budgeting approach
  - Sovereign fund investments
---

# 14.2 RISK ALLOCATION FOR PENSION FUNDS AND SOVEREIGN FUNDS  

Pension funds and sovereign funds, while subject to guidelines set by their governing bodies, enjoy great discretion in allocating their investment dollars, and often do not shy from alternative investments. These include commercial real estate and land development, hedge funds and private equity. In addition to investment (asset) management, pension funds and endowments often have extensive disbursement obligations on the liability side. Pension fund assets must be liquidated to satisfy monthly disbursements to pensioners; endowments provide specific dollar amounts or guaranteed rates of return to the universities, cultural institutions, or charities they support. Sovereign funds in particular, but pension funds and endowments too, may be subject to political pressures to allocate funds in a particular way or provide extraordinary disbursements. Table 14.1 shows the largest six pension and sovereign funds in the world.  

# 14.2.1 Defined Benefit Pension Funds and Endowments  

The management of the defined benefit pension plans and endowments is of special interest as it shares some features of insurance companies. Defined benefit plans often give the employees they cover a specified retirement formula. In the USA, a popular plan is $2\%$ per number of years worked times the last year's or last 5 years' average salary. There may be a kicker where the percentage gradually increases from $2\%$ to $3\%$ if the number of years exceeds 25 or 30, and there is a specified minimum retirement age. University endowments guarantee to disburse a dollar amount equal to a guaranteed interest rate. Both these arrangements are similar to life insurance policies which credit cash accounts with a declared interest rate and offer a guaranteed life benefit. The attitudes to funding life insurance vary around the world with British companies carrying more equity in their investment portfolios, and their American counterparts carrying hardly any. After all, the liability here is quite fixed. Many scholars question the practice of incurring fixed liabilities and funding them with an equity portfolio. Often the liabilities end up being grossly underfunded as the discount rates assumed to present-value the future obligations are quite high (based on long-term equity returns). Several researchers have suggested funding them with high-grade fixed income investments, perhaps enhanced with some equity options. Few of these serious suggestions have been taken seriously by the plan sponsors - governments, workers' unions, or private corporations.  

Table 14.1 Top 6 Pension and Sovereign Funds in the World   


<html><body><table><tr><td>Pension Fund</td><td>Dec2009Assetsin$bn</td></tr><tr><td>Government Pension Investment Fund, Japan</td><td>$1,315</td></tr><tr><td>GovernmentPensionFund,Norway</td><td>$476</td></tr><tr><td>StichtingPensioenfondsABP,Netherlands</td><td>$300</td></tr><tr><td>Korea's National Pension Corp</td><td>$235</td></tr><tr><td>FederalRetirementThrift,USA</td><td>$234</td></tr><tr><td>California Public Employees’ Retirement System, USA</td><td>$199</td></tr><tr><td>SovereignFund</td><td>Dec2010Assetsin$bn</td></tr><tr><td>AbuDhabiInvestmentAuthority</td><td>$627</td></tr><tr><td>SAMA Foreign Holdings,Saudi Arabia</td><td>$415</td></tr><tr><td>SAFEInvestment Company,China</td><td>$347</td></tr><tr><td>ChinaInvestment Corporation</td><td>$289</td></tr><tr><td>GovernmentofSingaporeInvestmentCorporation</td><td>$248</td></tr><tr><td>Hong Kong Monetary Authority Investment Portfolio</td><td>$228</td></tr></table></body></html>  

Given that state of affairs, pension plans and endowments have to aggressively pursue risk. in order to maximize return. The standard allocation method is the same as for individuals except that it includes alternative illiquid asset classes. The total dollars coming in to be invested are divided among the different classes dependent on the duration of the liabilities. The total investment portfolio, governed by the plan's investment committee, is rebalanced quarterly or semi-annually, with the objective to meet the statutory return rate with the lowest amount of risk (classic mean variance approach enhanced with some VaR tools). In the last 10 years, another approach called \*risk-budgeting" has gained some traction. The approach has. been pitched by many advisers at various conferences and specialized training programs. The. approach is not revolutionary, but offers some interesting insights. The next section describes its main principles.  

# 14.2.2 The Risk Budget Allocation Process  

The central idea in risk-budgeting is to allocate a specific percentage of risk rather than. investment dollars to a specific asset class. This necessitates the definition of risk and the specification of the overall risk tolerance for the fund. This does not avoid making standard decisions on active-passive split and specific active manager allocations. However, it leads to interestingly different emphasis from the traditional investment amount allocation..  

We present the ideas using the mean-variance risk framework, but everything that follows could be translated into the VaR framework..  

Consider a US-based pension fund allocating its portfolio to three risky assets: US stocks, developed country non-US stocks, and emerging markets stocks. We label them: US, EAFE,. and EM. Let us start with a $40\%/40\%/20\%$ allocation, as in Table 14.2, and show the volatility. and correlation assumptions.  

The US and EAFE parts of the portfolio are highly correlated. The sum of the weights times the volatilities is equal to $24\%$ . The total volatility of the portfolio, $19.86\%$ , is computed using the individual weights, volatilities, and correlations. The difference is due to (correlation) diversification. Table 14.3 shows the same portfolio through a lens of risk attribution.  

The unit Marginal risk contribution (MRC) is computed by blipping the weight by $0.1\%$ recomputing the total volatility of the portfolio and scaling it by 10. The interpretation is that a $1\%$ increase in the volatility of the US part of the portfolio would lead to a $0.15\%$ increase in the total volatility. The next column multiplies that number by weight, and the last column represents the result in percentages of the total volatility. While the US may have the lowest unit MRC, because it is $40\%$ of the portfolio, a unit change in volatility leads to. roughly the same change in risk as a unit change in EM volatility even though EM is only $20\%$ of the portfolio. The interesting result portrayed in Table 14.3 is that EAFE's and EM's. contributions to risk are larger than their investment weights while the US's contribution is. disproportionately smaller. This is due to the lower volatility of the US returns and higher. correlation of EAFE with EM than US with EM. The main objective of the risk attribution is to see these not always intuitive co-dependencies of volatilities and correlations.  

Table 14.2 The volatilities and correlations for the US/EAFE/EM portfolio   


<html><body><table><tr><td></td><td>Weight</td><td>Volatility</td><td></td><td colspan="3">Correlation matrix</td></tr><tr><td></td><td></td><td></td><td></td><td>US</td><td>EAFE</td><td>EM</td></tr><tr><td>US</td><td>40%</td><td>18.0%</td><td>US</td><td>1.00</td><td>0.85</td><td>0.20</td></tr><tr><td>EAFE</td><td>40%</td><td>22.0%</td><td>EAFE</td><td>0.85</td><td>1.00</td><td>0.50</td></tr><tr><td>EM</td><td>20%</td><td>40.0%</td><td>EM</td><td>0.20</td><td>0.50</td><td>1.00</td></tr><tr><td>Total</td><td>100%</td><td>19.9%</td><td></td><td></td><td></td><td></td></tr></table></body></html>  

The lesson here is that we are overweighted in the US and underweighted in the EM in terms of return contributions; we are grossly underweighted in the US and overweighted in the EAFE and EM in terms of risk! That may be a completely unintended consequence of the asset allocation percentages for this US-based pension fund.  

Let us perform a simple experiment. Suppose we wanted to limit to $20\%$ the allocation of risk to the EM. Table 14.4 shows one such possible scenario.  

The upshot is that we need to reallocate. $4.63\%$ of the portfolio from the EM to the US. part. Note that we may further desire to reallocate some of the EAFE investment to the US to reduce its contribution to risk, too.  

The risk-budgeting process includes the following steps:  

Set an overall target volatility level - absolute for a defined contribution plan, incremental in excess of guaranteed return for a defined benefit plan.   
Allocate to passive and active management - assume zero correlation between the two if active is managed as a portable alpha; passive presumably has the lion's share of the $\%$ risk attribution. Allocate within the passive part not to exceed the allocated risk ceiling.   
Select active asset classes and active managers.  

Table 14.3Marginal (MRC) and total risk contribution (TRC)   


<html><body><table><tr><td></td><td colspan="2">MRC</td><td>% Risk</td></tr><tr><td></td><td>Unit</td><td>× Weight</td><td>attribution</td></tr><tr><td>US</td><td>0.15%</td><td>5.9%</td><td>29.7%</td></tr><tr><td>EAFE</td><td>0.21%</td><td>8.4%</td><td>42.2%</td></tr><tr><td>EM</td><td>0.28%</td><td>5.6%</td><td>28.1%</td></tr><tr><td>Total</td><td></td><td>19.9%</td><td>100.0%</td></tr></table></body></html>  

Table 14.4Weights, MRC and TRC with a $20\%$ limit on EM risk.   


<html><body><table><tr><td colspan="4">MRC</td><td rowspan="2">%Risk attribution</td></tr><tr><td></td><td></td><td>Unit</td><td>× Weight</td></tr><tr><td>US</td><td>44.63%</td><td>0.16%</td><td>7.0%</td><td>36.0%</td></tr><tr><td>EAFE</td><td>40.00%</td><td>0.21%</td><td>8.5%</td><td>44.0%</td></tr><tr><td>EM</td><td>15.37%</td><td>0.25%</td><td>3.9%</td><td>20.0%</td></tr><tr><td>Total</td><td>100.00%</td><td></td><td>19.3%</td><td>100.0%</td></tr></table></body></html>  

Suppose we decide on the overall risk not to exceed $8\%$ volatility. Suppose we think the passive benchmark can be tracked with a mixed asset portfolio subject to $10\%$ volatility, and an active portfolio subject to $4\%$ volatility. Then we must allocate $79.6\%$ of the investment dollars to passive and $20.4\%$ to active management. This comes from the simple act of solving for the weights of a two non-correlated asset portfolio.  

We then repeat the process for the passive and active parts by solving for the investment. dollars allocated to each asset category within the passive and active parts of the portfolio. The calculation includes our assumptions about the individual volatilities and pairwise correlations, similar to our experiment in Table 14.4 but with. $7\%$ and $4\%$ targets. In the active part, many correlations should, but need not, be assumed zero. In the passive part, they are computed. from market data or can be input.  

The risk budget imposes a different discipline on the fund sponsors from standard asset allocation. In the classic approach, everything is return-driven. To stick to the prescribed. asset allocation, the quarterly or annual rebalancing implies selling a winner and buying. underperformers. In the risk-budgeting approach, it is the market volatility that drives the. rebalancing not relative performance. Another implication is that since our allocation was based on risk, less risky areas (fixed income) will tend to be overweighted relative to riskier classes (commodities, equities).  

The most obvious criticism of the risk-budgeting approach is that the initial allocation is based on risk calculations of historical volatility and correlation estimates. Yet risk changes over time and in extreme tail events correlations dramatically increase. The answer to this criticism is that standard allocation is implicitly based on realized return histories which may be just as unreliable. After all, we tend to allocate to equities and emerging markets because we expect higher returns there. What if they don't materialize?  

![](fafb6f362f67e8ad1648ab8848c8a61862430d6c6c33ed358a8635f2ea783f06.jpg)  