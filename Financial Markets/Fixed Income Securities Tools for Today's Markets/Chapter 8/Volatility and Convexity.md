---
tags:
  - binomial_tree
  - convexity
  - interest_rates
  - volatility
  - zero_coupon_bonds
aliases:
  - Bond Pricing
  - Jensen's Inequality
  - Volatility and Convexity
key_concepts:
  - Binomial tree
  - Bond price curve
  - Forward rates
  - Interest rate volatility
  - Jensen's inequality
  - Short-term rates
  - Zero coupon bonds
---

# 8.2 VOLATILITY AND CONVEXITY  

While investors have expectations about future short-term rates, they recognize the limits of their analyses, that is, realized rates are assumed to fluctuate randomly around expectations. Continuing with the framework of the previous chapter, consider the binomial tree for the one-year rate in the top part. of Figure 8.1. The step size is one year, and the probabilities of all transitions are $50\%$ (not shown). The level of rates and their volatility is exaggerated in this tree to illustrate the concepts of this chapter. Note that the expected. value of the short-term rate in one year is $9\%$ , as is the expected short-term rate in two years,  

$$
\begin{array}{r}{50\%\times13\%+50\%\times5\%=9\%}\ {50\%[50\%\times17\%+50\%\times9\%]+50\%[50\%\times9\%+50\%\times1\%]=9\%}\end{array}
$$  

Note also that the volatility of the change in rate at any transition is $4\%$ , Or 400 basis points. For example, with the mean of the first transition calculated in Equation (8.2) to be $9\%$ , the volatility of that transition is,  

$$
\sqrt{50\%13\%-9\%]^{2}+50\%[5\%-9\%]^{2}}=4\%
$$  

The price of a one-year zero in this model is simply. $1/1.09$ , or 0.917431. Assuming, for the moment, that investors are risk neutral, the price trees of the two- and three-year zeros can be calculated by expected discounted value, as explained in the previous chapter. These trees are shown in the bottom of Figure 8.1, with the supporting calculations left to the reader. Table 8.1 collects the prices of the three zero coupon bonds, along with the associated forward rates. The striking feature of the table is that the term structure of forward rates is downward sloping, despite the fact that interest rate expectations are flat at $9\%$ . This result can be explained by the interaction of interest rate volatility with the convexity of bond prices.  

![](b5357265c248d862370cea4cebe6b9b23dac98060320ff4de3bc022c1d2fcd0a.jpg)  
FIGURE 8.1 Binomial Rate Tree and Price Trees for Two- and Three-Year Zero. Coupon Bonds. Steps Are Annual, and the Probabilities of All Transitions Are $50\%$  

TABLE 8.1 Prices of Zero Coupon Bonds and Their Associated Forward Rates from the Rate Tree in Figure 8.1. Rates Are in Percent.   


<html><body><table><tr><td>Term</td><td>Price</td><td>Forward Rate</td></tr><tr><td>1</td><td>0.917431</td><td>9.0000</td></tr><tr><td>2</td><td>0.842815</td><td>8.8532</td></tr><tr><td>3</td><td>0.776366</td><td>8.5590</td></tr></table></body></html>  

A short detour is required at this point to present and explain Jensen's inequality as applied to bond pricing. For a random variable, like the one-year rate, $r$  

$$
E\left[\frac{1}{1+r}\right]>\frac{1}{E[1+r]}=\frac{1}{1+E[r]}
$$  

In words, the expected price of a bond is greater than the price of a bond at the expected interest rate.  

![](d7528895cf70580f4c42ca74cb5d468f74b1cdb213096ab6874ad64d643b6b6d.jpg)  
FIGURe 8.2  An Illustration of Jensen's Inequality as Applied to Bond Pricing.  

This inequality is easily explained by Figure 8.2. In the figure, the rate can take on two values,. $r^{d}$ and $r^{u}$ , with equal probability, resulting in an expected value just between them, $E[r]$ . Each possible value of. $r$ has an associated price, and the expected value of that price, $E[1/(1+r)]$ , is graphically depicted as the vertical-axis coordinate of the dotted line connecting the points $\{r^{d},1/(1+r^{d})\}$ and $\{r^{u},1/(1+r^{u})\}$ . Because of the curvature or con-. vexity of the price-rate curve, however, this expected price exceeds the price at a rate of $E[r]$ , which is $1/(1+E[r])$ . And this is exactly the relationship described in Equation (8.5)..  

Returning to the role of volatility and convexity, let $f$ denote the one-year rate, one year forward, and consider the date-0 price of a two-year zero coupon bond, as expressed in Equation (8.6). By definition, the price of the two-year zero equals its unit face amount discounted by. $9\%$ over the first year and by $f$ over the second year. By the logic of pricing along the tree, this price also equals the discounted expected value of the date-1 price of the bond. Multiplying both sides of (8.6) by 1.09 and invoking Jensen's. inequality in Equation (8.5), gives (8.7). And from this equation, (8.8) follows directly: the one-year rate, one year forward, is less than the expected. one-year rate in one year,  

$$
0.8428\equiv\frac{1}{(1.09)(1+f)}=\frac{1}{1.09}\left[50\%\times\frac{1}{1.13}+50\%\times\frac{1}{1.05}\right]
$$  
