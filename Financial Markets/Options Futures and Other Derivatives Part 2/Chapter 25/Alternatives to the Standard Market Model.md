# 25.11 ALTERNATIVES TO THE STANDARD MARKET MODEL  

This section outlines a number of alternatives to the one-factor Gaussian copula model that has become the market standard..  

# Heterogeneous Model  

The standard market model is a homogeneous model in the sense that the time-todefault probability distributions are assumed to be the same for all companies and the copula correlations for any pair of companies are the same. The homogeneity assumption can be relaxed so that a more general model is used. However, this model is more complicated to implement because each company has a different probability of defaulting by any given time and $P(k,t\mid F)$ can no longer be calculated using the binomial formula in equation (25.7). It is necessary to use a numerical procedure such as that described in Andersen et al. (2003) and Hull and White (2004).10  

# Other Copulas  

The one-factor Gaussian copula model is a particular model of the correlation between times to default. Many other one-factor copula models have been proposed. These include the Student $t$ copula, the Clayton copula, Archimedean copula, and Marshall-- Olkin copula. We can also create new one-factor copulas by assuming that. $F$ and the $Z_{i}$ in equation (24.7) have nonnormal distributions with mean 0 and standard deviation 1. Hull and White show that a good fit to the market is obtained when $F$ and the $Z_{i}$ have Student t distributions with four degrees of freedom.11 They call this the double t copula..  

Another approach is to increase the number of factors in the model. Unfortunately, the model is then much slower to run because it is necessary to integrate over several. normal distributions instead of just one.  

# Random Recovery and Factor Loadings  

Andersen and Sidenius have suggested a model where the copula correlation $\rho$ in equation (25.5) is a function of $F$ and the recovery rate is negatively related to the default. rate.12  

In general, $\rho$ increases as $F$ decreases. This means that in states of the world where the default rate is high (i.e., states of the world where $F$ is low) the default correlation is also high. There is empiricalevidence suggesting that this is the case.13 Andersen and Sidenius find that this model fits market quotes much better than the standard market model.  

# The Implied Copula Model  

Hull and White show how a copula can be implied from market quotes.14 The simplest. version of the model assumes that a certain average hazard rate applies to all companies. in a portfolio over the life of a CDO. That average hazard rate has a probability. distribution that can be implied from the pricing of tranches. The calculation of the implied copula is similar in concept to the idea, discussed in Chapter 20, of calculating an implied probability distribution for a stock price from option prices..  

# Dynamic Models  

The models discussed so far can be characterized as static models. In essence they. model the average default environment over the life of the CDO. The model constructed for a 5-year CDO is different from the model constructed for a 7-year CDO, which is in turn different from the model constructed for a 10-year CDO. Dynamic. models are different from static models in that they attempt to model the evolution of the loss on a portfolio through time. There are three different types of dynamic. models:  

1. Structural Models: These are similar to the models described in Section 24.6 except that the stochastic processes for the asset prices of many companies are. modeled simultaneously. When the asset price for a company reaches a barrier,. there is a default. The processes followed by the assets are correlated. The problem. with these types of models is that they have to be implemented with Monte Carlo. simulation and calibration is therefore difficult..   
2. Reduced Form Models: In these models the hazard rates of companies are modeled.. In order to build in a realistic amount of correlation, it is necessary to assume that there are jumps in the hazard rates.  

3. Top Down Models: These are models where the total loss on a portfolio is modeled directly. The models do not consider what happens to individual companies..  

# SUMMARY  

Credit derivatives enable banks and other financial institutions to actively manage their credit risks. They can be used to transfer credit risk from one company to another and to diversify credit risk by swapping one type of exposure for another.  

The most common credit derivative is a credit default swap. This is a contract where one company buys insurance from another company against a third company (the reference entity) defaulting on its obligations. The payoff is designed to equal the difference between the face value of a bond issued by the reference entity and its value immediately after a default. Credit default swaps can be analyzed by calculating the present value of the expected payments and the present value of the expected payoff in a risk-neutral world.  

A forward credit default swap is an obligation to enter into a particular credit default. swap on a particular date. A credit default swap option is the right to enter into a. particular credit default swap on a particular date. Both instruments cease to exist if the reference entity defaults before the date.A kth-to-default CDS is defined as a CDS that pays off when the kth default occurs in a portfolio of companies..  

A total return swap is an instrument where the total return on a portfolio of creditsensitive assets is exchanged for a floating rate plus a spread. Total return swaps are often used as financing vehicles. A company wanting to purchase a portfolio of assets will approach a financial institution to buy the assets on its behalf. The financial institution then enters into a total return swap with the company where it pays the return on the assets to the company and receives a floating rate plus a spread. The advantage of this type of arrangement is that the financial institution has less exposure than if it had lent the company money to buy the portfolio.  

In a collateralized debt obligation a number of different securities are created from a portfolio of corporate bonds or commercial loans. There are rules for determining how credit losses are allocated. The result of the rules is that securities with both very high and very low credit ratings are created from the portfolio. In a synthetic collateralized debt obligation, cash flows on tranches are defined from a reference portfolio of credit default swaps. The standard market model for pricing both a kth-to-default CDS and tranches of a synthetic CDO is the one-factor Gaussian copula model for time to default.  

# FURTHER READING  

Andersen, L. B. G., and J. Sidenius, "Extensions to the Gaussian Copula: Random Recovery and Random Factor Loadings," Journal of Credit Risk, 1, No. 1 (Winter 2004): 29-70.   
Andersen, L. B. G., J. Sidenius, and S. Basu, "All Your Hedges in One Basket," Risk, 16, 10 (November 2003): 67-72.   
Das, S., Credit Derivatives: Trading & Management of Credit & Default Risk, 3rd edn. New York: Wiley, 2005.   
Hull, J. C., and A. White, "Valuation of a CDO and nth to Default Swap without Monte Carlo Simulation," Journal of Derivatives, 12, No. 2 (Winter 2004): 8-23.   
Hull, J. C., and A. White, "Valuing Credit Derivatives Using an Implied Copula Approach," Journal of Derivatives, 14, 2 (Winter 2006), 8-28.   
Hull, J. C., and A. White, "An Improved Implied Copula Model and its Application to the Valuation of Bespoke CDO Tranches," Journal of Investment Management, 8, 3 (2010), 11-31.   
Laurent, J.-P., and J. Gregory, "Basket Default Swaps, CDOs and Factor Copulas," Journal of. Risk, 7, 4 (2005), 8-23.   
Li, D. X., "On Default Correlation: A Copula Approach," Journal of Fixed Income, March 2000: 43-54.   
Schonbucher, P. J., Credit Derivatives Pricing Models. New York: Wiley, 2003.   
Tavakoli, J. M., Credit Derivatives & Synthetic Structures: A Guide to Instruments and Applications, 2nd edn. New York: Wiley, 2019.  

# Practice Questions  

25.1. Explain the difference between a regular credit default swap and a binary credit default Swap.   
25.2. A 5-year credit default swap requires a quarterly payment at the rate of 60 basis points per year. The principal is $\$300$ million and the credit default swap is settled in cash. A default occurs after 4 years and 2 months, and the price of the cheapest deliverable bond is estimated as. $40\%$ of its face value shortly after the default. List the cash flows and their timing for the seller of the credit default swap.   
25.3. Explain the difference between a cash CDO and a synthetic CDO.   
25.4. Explain the term "single-tranche trading.".   
25.5. What is a first-to-default credit default swap? Does its value increase or decrease as the default correlation between the companies in the basket increases? Explain your answer..   
25.6. Explain the difference between risk-neutral and real-world default probabilities. Which should be used for valuing CDSs?.   
25.7. Explain why a total return swap can be useful as a financing tool.   
25.8. Suppose that the risk-free zero curve is flat at $7\%$ per annum with continuous compounding and that defaults can occur halfway through each year in a new 5-year credit default swap. Suppose that the recovery rate is. $30\%$ and the hazard rate is $3\%$ Estimate the credit default swap spread. Assume payments are made annually.   
25.9. What is the value of the swap in Problem 25.8 per dollar of notional principal to the protection buyer if the credit default swap spread is 150 basis points?.   
25.10. What is the credit default swap spread in Problem 25.8 if it is a binary CDS?   
25.11. How does a 5-year nth-to-default credit default swap work? Consider a basket of 100 reference entities where each reference entity has a probability of defaulting in each year. of $1\%$ . As the default correlation between the reference entities increases what would you expect to happen to the value of the swap when (a) $n=1$ and (b) $n=25$ . Explain your answer.   
25.12. What is the formula relating the payoff on a CDS to the notional principal and the recovery rate?   
25.13. Show that the spread for a new plain vanilla CDS should be $(1-R)$ times the spread for.  

a similar new binary CDS, where. $R$ is the recovery rate.  

25.14. Verify that, if the CDS spread for the example in Tables 25.1 to 25.4 is 100 basis points, the hazard rate must be $1.63\%$ per year. How does the hazard rate change when the recovery rate is $20\%$ instead of $40\%?$ Verify that your answer is consistent with the implied hazard rate being approximately proportional to $1/(1-R)$ , where $R$ is the recovery rate.  

25.15. A company enters into a total return swap where it receives the return on a corporate bond paying a coupon of. $5\%$ and pays a floating rate. Explain the difference between. this and a regular swap where $5\%$ is exchanged for a floating rate.   
25.16. Explain how forward contracts and options on credit default swaps are structured.   
25.17. "The position of a buyer of a credit default swap is similar to the position of someone who is long a risk-free bond and short a corporate bond." Explain this statement.   
25.18. Why is there a potential asymmetric information problem in credit default swaps?   
25.19. Does valuing a CDS using real-world default probabilities rather than risk-neutral default probabilities overstate or understate its value? Explain your answer.   
25.20. What is the difference between a total return swap and an asset swap?   
25.21. Suppose that in a one-factor Gaussian copula model the 5-year probability of default for each of 125 names is $3\%$ and the pairwise copula correlation is 0.2. Calculate, for factor values of $-2,-1,0,1$ , and 2: (a) the default probability conditional on the factor value and (b) the probability of more than 10 defaults conditional on the factor value.   
25.22. Explain the difference between base correlation and compound correlation..   
25.23. In Example 25.2, what is the tranche spread for the $9\%$ to $12\%$ tranche assuming ae tranche correlation of 0.15?   
25.24. Suppose that the risk-free zero curve is flat at $6\%$ per annum with continuous. compounding and that defaults can occur at times 0.25 years, 0.75 years, 1.25 years, and 1.75 years in a 2-year plain vanilla credit default swap with semiannual payments. Suppose that the recovery rate is $20\%$ and the unconditional probabilities of default (as seen at time zero) are $1\%$ at times 0.25 years and 0.75 years, and $1.5\%$ at times 1.25 years and 1.75 years. What is the credit default swap spread? What would the credit default spread be if the instrument were a binary credit default swap?.   
25.25. Assume that the hazard rate for a company is $\lambda$ and the recovery rate is $R$ . The risk-free interest rate is $5\%$ per annum. Default always occurs halfway through a year. The spread for a 5-year plain vanilla CDS where payments are made annually is 120 basis points and the spread for a 5-year binary CDS where payments are made annually is 160 basis points. Estimate $R$ and $\lambda$   
25.26. Explain how you would expect the returns offered on the various tranches in a synthetic CDO to change when the correlation between the bonds in the portfolio increases..   
25.27. Suppose that:   
(a) The yield on a 5-year risk-free bond is $7\%$   
(b) The yield on a 5-year corporate bond issued by company. $\boldsymbol{\mathrm X}$ is $9.5\%$   
(c) A 5-year credit default swap providing insurance against company $\boldsymbol{\mathrm X}$ defaulting costs 150 basis points per year.  

What arbitrage opportunity is there in this situation? What arbitrage opportunity would. there be if the credit default spread were 300 basis points instead of 150 basis points?  

25.28. In Example 25.3, what is the spread for (a) a first-to-default CDS and (b) a second-todefault CDS?   
25.29. In Example 25.2, what is the tranche spread for the $6\%$ to $9\%$ tranche assuming a tranche correlation of 0.15?   
25.30. Table 25.6 shows the 5-year iTraxx index was 77 basis points on January 31, 2008. Assume the risk-free rate is $5\%$ for all maturities, the recovery rate is. $40\%$ , and payments are quarterly. Assume also that the spread of 77 basis points applies to all maturities. Use the DerivaGem CDS worksheet to calculate a hazard rate consistent with the spread. Use this in the CDO worksheet with 10 integration points to imply base. correlations for each tranche from the quotes for January 31, 2008..  

![](images/75fb9e1b4b107455cf93261456eb5ebe61b97a478e5a419397c2a509065ad9b7.jpg)  

# Exotic Options  

Derivatives such as European and American call and put options are what are termed plain vanilla products. They have standard well-defined properties and trade actively. Their prices or implied volatilities are quoted by exchanges or by interdealer brokers on a regular basis. One of the exciting aspects of the over-the-counter derivatives market is the number of nonstandard products that have been created by financial engineers. These products are termed exotic options, or simply exotics. Although they usually constitute a relatively small part of its portfolio, exotics are important to a derivatives dealer because they are generally much more profitable than plain vanilla products.  

Exotic products are developed for a number of reasons. Sometimes they meet a genuine hedging need in the market; sometimes there are tax, accounting, legal, or. regulatory reasons why corporate treasurers, fund managers, and financial institutions find exotic products attractive; sometimes the products are designed to reflect a view on potential future movements in particular market variables; occasionally an exotic. product is designed by a derivatives dealer to appear more attractive than it is to an. unwary corporate treasurer or fund manager..  

In this chapter, we describe some of the more commonly occurring exotic options. and discuss their valuation. We assume that the underlying asset provides a yield at rate $q$ . As discussed in Chapters 17 and 18, for an option on a stock index. $q$ should be set equal to the dividend yield on the index, for an option on a currency it should be set equal to the foreign risk-free rate, and for an option on a futures contract it should be set equal to the domestic risk-free rate. Many of the options discussed in this chapter can be valued using the DerivaGem software..  
