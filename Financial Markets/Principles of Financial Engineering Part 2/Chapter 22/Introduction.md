---
tags:
  - '#correlation_trading'
  - '#credit_derivatives'
  - '#credit_risk'
  - '#credit_risk_modeling'
  - '#default_correlation'
  - '#default_risk'
  - '#structured_products'
  - '#tranche_values'
---
# 22.1 INTRODUCTION  

There are three major issues with the credit sector. First there is the understanding and engineering of the credit risk itself. In other words, how does one strip the default risk component of a bond or a loan and trade it separately? The engineering of a CDS serves this purpose and was done in Chapter 18.  

The second dimension in studying credit risk is the modeling aspect. Without modeling one cannot implement pricing, hedging, and risk management problems. Modeling helps to go from descriptive or graphical discussion to numbers. In credit risk, the modeling has a "novel' component. The risk in question is an event, the default. They are zero-one type random variables and are different than risk factors such as interest rates and stock prices which can be approximated by continuous state stochastic processes.' Credit risk, being a zero-one event, introduces a new dimensions in modeling.  

The third major dimension of the credit sector has to do with the tranching of default risks. The main point of Chapter 21 was that tranching credit risk can eventually lead to stripping the default correlation.. In this chapter, we talk about modeling default correlation and the resulting financial engineering of. default correlation. We learn how to strip, hedge, and trade it. The recent correlation market provides the. real-world background.  

As we discussed in the previous chapter, banks extended the securitization process to CDOs, CLOs, and other products. The intermediate or mezzanine tranches were sold to investors. The very high-quality tranches, called senior and super senior, were also kept on banks' books because their. implied return was too small for many investors. As a result, the banks found themselves long equity tranche and long senior and super senior tranches. They were short the mezzanine tranche which paid a good return and was rated investment grade. It turns out, as we will see in this chapter, that the equity tranche value is positively affected by the default correlation while the super senior tranche value is negatively affected. The sum of these positions formed the correlation books of the banks. Banks had to learn correlation trading, hedging, and pricing as a result.  

The connection between default correlation and tranche values is a complex one and needs to be clarified step by step. We discuss market examples of how this idea can be exploited in setting up correlation trades and can be exploited in setting up new structured products. The first issue that we need to introduce is the dependence of the tranche pricing on the default correlation.  
