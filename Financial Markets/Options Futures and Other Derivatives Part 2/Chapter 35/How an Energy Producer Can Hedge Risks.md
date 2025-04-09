# 35.8 HOW AN ENERGY PRODUCER CAN HEDGE RISKS  

There are two components to the risks facing an energy producer. One is the risk associated with the market price for the energy (the price risk); the other is risk associated with the amount of energy that will be bought (the volume risk). Although prices do adjust to reflect volumes, there is a less-than-perfect relationship between the two, and energy producers have to take both into account when developing a hedging strategy. The price risk can be hedged using the energy derivative contracts. The volume risks can be hedged using the weather derivatives. Define:  

Y: Profit for a month.   
$P$ : Average energy prices for the month.   
T: Relevant temperature variable (HDD or CDD) for the month.  

An energy producer can use historical data to obtain a best-fit linear regression relationship of the form  

$$
Y=a+b P+c T+\epsilon
$$  

where $\epsilon$ is the error term. The energy producer can then hedge risks for the month by taking a position of $-b$ in energy forwards or futures and a position of. $-c$ in weather  

forwards or futures. The relationship can also be used to analyze the effectiveness of alternative option strategies.  

# SUMMARY  

When there are risks to be managed, derivatives markets have been very innovative in developing products to meet the needs of the market..  

There are a number of different types of commodity derivatives. The underlyings include agricultural products that are grown, livestock, metals, and energy products. The models used to value them usually incorporate mean reversion. Sometimes seasonality is modeled explicitly and jumps are incorporated. Energy derivatives with oil, natural gas, and electricity as the underlying are particularly important and have been the subject of models that are as sophisticated as the most sophisticated models used for stock prices, exchange rates, and interest rates.  

In the weather derivatives market, two measures, HDD and CDD, have been developed to describe temperature during a month. These are used to define payoffs on both exchange-traded and over-the-counter derivatives. As the weather derivatives market develops, contracts on rainfall, snow, and other weather-related variables may become more widely used.  

Insurance derivatives are an alternative to traditional reinsurance as a way for insurance companies to manage the risk of a catastrophic event such as a hurricane. or an earthquake. We may see other sorts of insurance, such as life and automobile. insurance, being traded in a similar way in the future..  

Weather and insurance derivatives have the property that the underlying variables have no systematic risk. This means that the derivatives can be valued by estimating expected payoffs using historical data and discounting the expected payoff at the risk-free rate.  

# FURTHER READING  

# On Commodity Derivatives  

Clewlow, L., and C. Strickland. Energy Derivatives: Pricing and Risk Management. Lacima Group, 2000.   
Edwards, D. W. Energy, Trading, and Investing: Trading, Risk Management and Structuring Deals in the Energy Markets. Maidenhead: McGraw-Hill, 2010.   
Eydeland, A., and K. Wolyniec. Energy and Power Risk Management. Hoboken, NJ: Wiley, 2003.   
Geman, H. Commodities and Commodity Derivatives: Modeling and Pricing for Agriculturals,. Metals, and Energy. Chichester: Wiley, 2005.   
Gibson, R., and E. S. Schwartz. "Stochastic Convenience Yield and the Pricing of Oil Contingent Claims,' Journal of Finance, 45 (1990): 959-76.   
Schofield, N. C. Commodity Derivatives: Markets and Applications. Chichester: Wiley, 2011.   
On Weather Derivatives   
Alexandridis, A. K., and A. D. Zapranis. Weather Derivatives: Modeling and Pricing Weather. Related Risk. New York: Springer, 2013.   
Cao, M., and J. Wei. "Weather Derivatives Valuation and the Market Price of Weather Risk,' Journal of Futures Markets, 24, 11 (November 2004), 1065-89.  

# On Insurance Derivatives  

Canter, M. S., J. B. Cole, and R. L. Sandor. "Insurance Derivatives: A New Asset Class for the Capital Markets and a New Hedging Tool for the Insurance Industry,' Journal of Applied Corporate Finance (Autumn 1997): 69-83.   
Froot, K. A. "The Market for Catastrophe Risk: A Clinical Examination,' Journal of Financial Economics, 60 (2001): 529-71.   
Litzenberger, R. H., D. R. Beaglehole, and C. E. Reynolds. "Assessing Catastrophe ReinsuranceLinked Securities as a New Asset Class, Journal of Portfolio Management (Winter 1996): 76-86.  

# Practice Questions  

35.1. What is meant by HDD and CDD?  

35.2. How is a typical natural gas forward contract structured?   
35.3. Distinguish between the historical data and the risk-neutral approach to valuing a derivative. Under what circumstance do they give the same answer?   
35.4. Suppose that each day during July the minimum temperature is $68^{\circ}$ Fahrenheit and the maximum temperature is $82^{\circ}$ Fahrenheit. What is the payoff from a call option on the cumulative CDD during July with a strike of 250 and a payment rate of $\$5,000$ per degree-day?   
35.5. Why is the price of electricity more volatile than that of other energy sources?   
35.6. Why is the historical data approach appropriate for pricing a weather derivatives contract and a CAT bond?   
35.7. HDD and CDD can be regarded as payoffs from options on temperature." Explain this statement.   
35.8. Suppose that you have 50 years of temperature data at your disposal. Explain carefully the analyses you would carry out to value a forward contract on the cumulative CDD for a particular month..   
35.9. Would you expect the volatility of the 1-year forward price of oil to be greater than or less than the volatility of the spot price? Explain your answer.   
35.10. What are the characteristics of an energy source where the price has a very high volatility and a very high rate of mean reversion? Give an example of such an energy source.   
35.11. How can an energy producer use derivatives markets to hedge risks?   
35.12. Explain how a $5\times8$ option contract on electricity with daily exercise works. Explain how a $5\times8$ option contract on electricity with monthly exercise works. Which is worth more?   
35.13. Explain how CAT bonds work.   
35.14. Consider two bonds that have the same coupon, time to maturity, and price. One is a B-rated corporate bond. The other is a CAT bond. An analysis based on historical data shows that the expected losses on the two bonds as a function of time are the same. Which bond would you advise a portfolio manager to buy and why?   
35.15. Consider a commodity with constant volatility $\sigma$ and an expected growth rate that is a function solely of time. Show that, in the traditional risk-neutral world,  

$$
\ln S_{T}\sim\phi[\ln F(T)-{\textstyle{\frac{1}{2}}}\sigma^{2}T,\sigma^{2}T]
$$  

where $S_{T}$ is the value of the commodity at time $T,F(t)$ is the futures price at time O for a contract maturing at time $t$ , and $\phi(m,\nu)$ is a normal distribution with mean $m$ and variance $\nu$  

35.16. How is the tree in Figure 35.2 modified if the 1- and 2-year futures prices are $\$21$ and $\$22$ instead of $\$22$ and $\$23$ , respectively. How does this affect the value of the American option in Example 35.3.  

![](images/5cb877fbe52da52dcdda1ae2af3582df52904f086d3fc7835e098ed6f7340cc6.jpg)  

# Real Options  

Up to now we have been almost entirely concerned with the valuation of financial assets. In this chapter we explore how the ideas we have developed can be extended to assess capital investment opportunities in real assets such as land, buildings, plant, and. equipment. Often there are options embedded in these investment opportunities (the. option to expand the investment, the option to abandon the investment, the option to defer the investment, and so on.) These options are very difficult to value using. traditional capital investment appraisal techniques. The approach known as real options. attempts to deal with this problem using option pricing theory..  

The chapter starts by explaining the traditional approach to evaluating investments in real assets and shows how difficult it is to correctly value embedded options when this approach is used. It then explains how the risk-neutral valuation approach can be. extended to handle the valuation of real assets and presents a number of examples illustrating the application of the approach in different situations..  
