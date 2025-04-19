---
tags:
  - duration
  - fixed_rate_security
  - interest_rate_risk
  - mbs
  - model_error
  - mortgage_pricing
  - oas
  - prepayment_model
  - relative_value_trades
  - risk_neutral_model
aliases:
  - MBS pricing
  - Mortgage duration
  - OAS
  - Option-adjusted spread
key_concepts:
  - Fixed cash flow duration
  - MBS cash flows
  - Mean reverting OAS
  - Model error misspecification
  - Model price vs market price
  - Mortgage risk sensitivities
  - Negative convexity
  - Option-adjusted spread (OAS)
  - Prepayment impact on price
  - Relative value trades
---

# 15.7 MORTGAGE PRICING, SPREADS, AND DURATION  

Combining a prepayment model with a risk-neutral model of the term structure, MBS can be computed as the expected discounted value of their cash flows. Because the model price of a given MBS typically does not perfectly match its market price, an option-adjusted spread (OAS) is defined as the spread that, when added to the initial, benchmark term structure, results in a model MBS price that equals the market price. OAS is the equivalent of bond spread introduced in Chapter 3 and discussed in Chapter 7. In particular, the OAS can be interpreted as the extra return earned when interest rate risk is correctly hedged by the model with securities that are fairly priced by the model.  

A straightforward use of OAS is to buy cheap securities, those with high OAS; to sell rich securities, those with low OAS; and, more aggressively, to engage in relative value trades that simultaneously buy high-OAS and short low-OAS securities. A practical challenge to investing and trading with OAS is model error or misspecification. It is unusual for a model to find that a particular MBS is cheap or rich, while other MBS, with similar characteristics, are fair. More usual is to find that a particular sector, for example, pools with high loan balances, is cheap or rich relative to other MBs. In that case, the success of any trades based on those OAS depends crucially on whether the model is really better than the market at valuing pools with different loan sizes. Another challenge, particularly for relative value trades, is whether OAS are mean reverting. A model may be correctly specified in concluding that a sector is cheap, so that buying and holding MBs in that sector outperforms other sectors over time. But if the sector stays cheap for an extended period of time, a relative value strategy of buying that sector and shorting another might not profit quickly enough to compensate for the use of capital and the costs of financing over time.  

Another important use of mortgage pricing models is to estimate the risk sensitivities of MBs. Calculating the duration of the mortgage in Table 15.4 as if its cash flows were fixed, that is, by shifting the discount rate. alone, along the lines of Chapter 4, gives a duration of about 11.7. But this fixed cash flow or static duration greatly overstates the extent to which the value of a 30-year MBS increases as rates fall. While the value of surviving cash flows does increase as rates fall, all balances prepaid by homeowners are worth only par. To illustrate, Figure 15.5 graphs the price of CA2797 as a function of the five-year Treasury rate from November 30, 2018, to. December 21, 2021, excluding the worst of the market turmoil from the. pandemic and economic shutdowns, from March 2, 2020, to May 15, 2020.10 For intermediate and higher rates in the graph, the price of the pool behaves like that of a fixed-rate security: price falls with rates in a close to linear or slightly positively convex manner. But as rates fall, price does not rise monotonically, but levels off at between about 111 and 112 per 100 face amount. Price does not increase further, despite the $4.500\%$ coupon, because of prepayments. But the price does rise significantly about 100, because many homeowners do not prepay, and the present values of their $4.500\%$ cash flows increase significantly in the markedly lower rate environment. Note too that the price-rate curve implicit in Figure 15.5 is negatively convex when rates are below $1.25\%$ or so, that is, as defined in Chapter 4, interest rate sensitivity falls as rates fall.  

![](0e48682fd7f412ee0672c9f133859f79c15eb455e997fc20ca2b346d776d89cd.jpg)  
FIGURE 15.5  Prices of FN CA2797 Versus the Five-Year Treasury Rate, from November 30, 2018, to February 28, 2020, and from May 18, 2020, to December 21, 2021.  

A mortgage model, with its prepayment modules, can calculate duration. meaningfully by shifting both discount factors and cash flows in response to. a shift in the benchmark curve. In other words, as benchmark rates increase, discount factors decrease, and prepayments decrease. Along these lines, the percentage change in price scaled for a 100-basis-point decrease in rates gives an option-adjusted duration or OAD.11 Using one particular model, Figure 15.6 graphs the OAD of an index of 30-year FNMA MBS, along with the five-year Treasury rate, over a 10-year period. The OAD in the graph averages 4.3 and ranges from 1.5 to 6.3. As expected, all of these values are significantly less than the static duration of a 30-year $4.5\%$ mortgage, calculated earlier as 11.7. The negative convexity of MBS can be seen clearly from this graph as well. For most time periods, OAD increases as the five-year Treasury rate increases, and OAD decreases as the five-year rate decreases.  

![](9b11a0f85e28dc1ada0464e1527b55515b84b9b7c190267af65e99b667f959f4.jpg)  
FIGURE 15.6 OAD for a FNMA 30-Year Index and the Five-Year Treasury Rate, December 21, 2011, to December 21, 2021.  
