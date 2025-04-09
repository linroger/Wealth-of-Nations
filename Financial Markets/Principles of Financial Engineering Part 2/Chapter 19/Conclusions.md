# 19.7 CONCLUSIONS  

In this chapter, we saw how we can apply the financial engineering and option pricing principles to value equity. Equity can be viewed as an option on the assets of the firm with a strike price equal to the debt value. Structural models of default thus establish a link between equity markets and bond or CDS markets. The development of credit derivative markets has accelerated the use of structural models of default in practice. Their applications range from the forecasting of default to capital structure arbitrage. Convertible bonds are hybrid products that can be converted from debt to equity. Convertible bond arbitrage strategies are based on exploiting cheap volatility while delta hedging the position. In the next chapter, we will review various structure products including reverse convertibles. Unlike convertible bonds, in reverse convertibles, the conversion option is conveyed to the issuer of the product and not the buyer. Both types of instruments have thus embedded options whose value depends on the implied volatility.  

# SUGGESTED READING  

This chapter has provided a simple introduction to structural models of default and hybrid equity products. The reader may want to follow up on the discussion in two ways. Das and Sundaram (2010) provide an accessible summary and application of the Merton (1974) model. Sundaresan (2013) reviews recent developments in research on structural models of default. Tepla (2004) provides a nice example and case study of convertible and capital structure arbitrage strategies based on KBC Investment Management. The discussion of capital arbitrage profits in this chapter is based on the case study.  

Ayache et al. (2003) provide a review of valuation of convertible bonds with credit risk. Several books deal with the current state of hybrid equity instruments. Das (2o00) is one example. Duffie and Singleton (2003) is also a good reference. The reader may also want to learn more about the technical issues related to pricing, hedging, and risk-managing hybrid equity products.  

Kat (2001) deals with some of the related issues. Damadoran (2012) is a good reference for discounted cash flow and other equity valuation approaches under the real-world probability measure which we do not discuss in this chapter.  

# EXERCISES  

1. Explain why debt in the Merton (1974) model is viewed as an option.   
2. Assume that company A has an asset volatility of $20\%$ . The current value of its assets is $\$100$ million and the face value of its 1-year maturity zero-coupon debt is $\$50$ million. The risk-free rate of interest is $2\%$ . Use the Merton (1974) model to calculate the value of the firm's equity. What is the value of the debt?   
3. Consider company B which issued equity and zero-coupon bonds with a maturity of 1 year. Assume that the value of the firm is $\$100$ and the value of the equity is $\$50$ million. The risk-free rate is. $2\%$ . The equity volatility is $30\%$ a. What is the market value of debt and the implied credit spread? b. Assume that the company has 1 million shares outstanding. Plot the credit spread against the share price for a range of different share price values. c. Plot the hedge ratios for different values of the share price.   
4. What variables and real-world complications are important in practice but ignored by the basic Merton model.   
5. Consider two convertible bonds X and Y, which for simplicity are assumed to be riskless. The following table provides information about the two bonds. Calculate the conversion value. What is the yield to maturity of the convertible bonds based on the actual bond price?  

<html><body><table><tr><td></td><td>ConvertibleBondX</td><td>ConvertibleBondY</td></tr><tr><td>Annualcoupon</td><td>50</td><td>50</td></tr><tr><td>Timetomaturity</td><td>5 years</td><td>5 years</td></tr><tr><td>Conversionratio</td><td>30</td><td>40</td></tr><tr><td>Stock price</td><td>$25</td><td>$30</td></tr><tr><td>Conversionvalue</td><td>？</td><td>？</td></tr><tr><td>Yieldon5-yearTreasuries</td><td>5%</td><td>5%</td></tr><tr><td>Value of straight debt</td><td>913.41</td><td>913.41</td></tr><tr><td>Actualconvertiblebondprice</td><td>920</td><td>1207</td></tr><tr><td>Yield to maturity of convertible</td><td>？</td><td>？</td></tr></table></body></html>  

Examine the information given in Table 19.2 in the text. Consider a trader that buys the convertible bond because it views the implied volatility as cheap and expects the implied volatility of the bond to correct. If the trader decides to hedge the long convertible bond position, how many. shares does he have to short to be delta neutral?.  

This page intentionally left blank  

# ESSENTIALS OF STRUCTURED 20 PRODUCT ENGINEERING  

# SHAPTER OUTLINE  

I.1 Introduction... 696   
0.2 Purposes of Structured Products. 697   
20.2.1 Equity Structured Products. 698   
20.2.2 The Tools. 702   
20.2.2.1 Touch and digital options. 704   
20.2.2.2 Rainbow options.. 705   
20.2.2.3 Reverse convertibles. 705   
20.2.2.4 Cliquets. 709   
20.2.3 Forward Volatility..... 710   
20.2.4 Prototypes 712   
20.2.4.1 Case I: A structure with built-in cliquet. 713   
20.2.4.2 Case II: Structures with mountain options 714   
20.2.4.3 Case III: The Napoleon and Vega hedging costs. 717   
20.2.5 Similar FX Structures. 718   
1.3 Structured Fixed-Income Products... .718   
20.3.1 Yield Curve Strategies. 718   
20.3.2 The Tools... 719   
20.3.3 CMS.. 719   
20.3.4 Yield Enhancement in Fixed-Income Products. 720   
20.3.4.1 Method 1: Sell cap volatility 721   
20.3.4.2 Method 2: Sell swaption volatility. 723   
20.4 Some Prototypes... .724   
20.4.1 The Components . 724   
20.4.2 CMS-Linked Structures. . 725   
20.4.3 Engineering a CMS-Linked Note 726   
20.4.3.1 A contractual equation. 726   
20.4.4 Engineering a CMS Spread Note.. 728   
20.4.5 The Engineering.. 729   
20.4.5.1 A contractual equation.. 733   
20.4.6 Some Other Structures. 733  
