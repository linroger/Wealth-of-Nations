---
tags:
  - brownian_motion
  - equity_correlation
  - implied_volatility
  - interest_rate_sector
  - market_practices
  - option_pricing
  - stochastic_volatility
  - stock_price_crashes
  - stop_loss_hedge
  - volatility_smile
aliases:
  - Conclusions
  - Excel Exercise
  - Exercises
  - MATLAB Exercises
  - Volatility Smile
key_concepts:
  - implied volatility
  - nongeometric brownian motion
  - option pricing
  - stochastic volatility
  - stock price crashes
  - stop-loss hedged portfolio
  - trading equity correlation
  - volatility smile
---

# 16.18 CONCLUSIONS  

The volatility smile is a fascinating topic in finance. Yet, it is also a complex phenomenon and. more research needs to be done on its causes and on the ways to model it. This chapter offered a simple introduction. However, it has illustrated some of the essential points associated with this. topic.  

# SUGGESTED READING  

Allen and Granger (2005) provide an excellent overview of techniques for trading equity correlation. The text by Brigo and Mercurio (2006) deals with the volatility smile in the interest rate sector. For equity smiles, the reader should consult the papers by Derman et al. (1994) and (1996), at a minimum. A comprehensive treatment of the volatility smile is provided in Lipton (2002). Taleb (1996) is the source that we used to discuss most market practices. There is also a flurry of papers dealing with empirical and theoretical issues involving the volatility smile. One recent source is Johnson and Lee (2o03). The cited sources contain further references on the previous research.  

# EXERCISES  

1. Consider the following table displaying the bid-ask prices for all options on the OEX index passed on January 10, 2002, at 9:46. These options have February 22, 2002, expiry and at the time of data collection, the underlying was at 589.14.  

<html><body><table><tr><td>Calls</td><td>Bid</td><td>Ask</td><td>Vol</td><td>Puts</td><td>Bid</td><td>Ask</td><td>Vol</td></tr><tr><td>Feb 400</td><td>188.9</td><td>191.9</td><td>0</td><td>Feb 400</td><td>0.05</td><td>0.2</td><td>0</td></tr><tr><td>Feb 420</td><td>169</td><td>172</td><td>0</td><td>Feb 420</td><td>0.1</td><td>0.4</td><td>0</td></tr><tr><td>Feb 440</td><td>149.2</td><td>152.2</td><td>0</td><td>Feb 440</td><td>0.25</td><td>0.55</td><td>0</td></tr><tr><td>Feb 460</td><td>129.4</td><td>132.4</td><td>0</td><td>Feb 460</td><td>0.45</td><td>0.75</td><td>0</td></tr><tr><td>Feb 480</td><td>109.6</td><td>112.6</td><td>0</td><td>Feb 480</td><td>0.8</td><td>1.1</td><td>0</td></tr><tr><td>Feb 500</td><td>90.2</td><td>92.7</td><td>0</td><td>Feb 500</td><td>1.4</td><td>1.7</td><td>0</td></tr><tr><td>Feb 520</td><td>71</td><td>73.5</td><td>0</td><td>Feb 520</td><td>2.5</td><td>2.8</td><td>0</td></tr><tr><td>Feb 530</td><td>61.6</td><td>64.1</td><td>0</td><td>Feb 530</td><td>2.8</td><td>3.5</td><td>0</td></tr><tr><td>Feb 540</td><td>52.4</td><td>54.9</td><td>0</td><td>Feb 540</td><td>3.7</td><td>4.4</td><td>0</td></tr><tr><td>Feb 550</td><td>43.8</td><td>45.8</td><td>0</td><td>Feb 550</td><td>4.9</td><td>5.6</td><td>1</td></tr><tr><td>Feb 560</td><td>35.4</td><td>37.4</td><td>0</td><td>Feb 560</td><td>6.6</td><td>7.3</td><td>0</td></tr><tr><td>Feb 570</td><td>27.9</td><td>29.4</td><td>0</td><td>Feb 570</td><td>8.9</td><td>9.6</td><td>0</td></tr><tr><td>Feb 580</td><td>20.8</td><td>22</td><td>0</td><td>Feb 580</td><td>11.8</td><td>12.8</td><td>0</td></tr><tr><td>Feb 590</td><td>14.8</td><td>15.8</td><td>0</td><td>Feb 590</td><td>15.8</td><td>16.8</td><td>1</td></tr><tr><td>Feb 600</td><td>10</td><td>10.7</td><td>1</td><td>Feb 600</td><td>20.8</td><td>22</td><td>0</td></tr><tr><td>Feb 610</td><td>6.1</td><td>6.8</td><td>0</td><td>Feb 610</td><td>27.1</td><td>28.6</td><td>0</td></tr><tr><td>Feb 615</td><td>4.6</td><td>5.3</td><td>0</td><td>Feb 615</td><td>31</td><td>32</td><td>0</td></tr><tr><td>Feb 620</td><td>3.4</td><td>4.1</td><td>0</td><td>Feb 620</td><td>34.3</td><td>36.3</td><td>0</td></tr><tr><td>Feb 630</td><td>1.9</td><td>2.2</td><td>0</td><td>Feb 630</td><td>42.8</td><td>44.8</td><td>0</td></tr><tr><td>Feb 640</td><td>0.9</td><td>1.2</td><td>0</td><td>Feb 640</td><td>52</td><td>54</td><td>0</td></tr><tr><td>Feb 650</td><td>0.4</td><td>0.7</td><td>0</td><td>Feb 650</td><td>61.4</td><td>63.9</td><td>0</td></tr><tr><td>Feb 660</td><td>0.15</td><td>0.45</td><td>0</td><td>Feb 660</td><td>71.2</td><td>73.7</td><td>0</td></tr><tr><td>Feb 680</td><td>0</td><td>0.25</td><td>0</td><td>Feb 680</td><td>90.8</td><td>93.8</td><td>0</td></tr><tr><td>Feb 700</td><td>0</td><td>0.2</td><td>100</td><td>Feb 700</td><td>110.8</td><td>113.8</td><td>0</td></tr></table></body></html>  

a. Using the out-of-the-money ask prices for the puts, calculate the implied volatility for the relevant strikes. Plot the volatility smile against K/S..   
b. Using the out-of-the-money bid prices for the puts, calculate the implied volatility for the relevant strikes. Plot the volatility smile against K/S. Are the bid-ask spreads for these vols constant?   
c. Using the out-of-the-money ask prices for the calls, calculate the implied vol for the relevant strikes. Plot the volatility smile against K/S. When you put this figure together with the outof-the-money put volatilities, do you obtain a smile or a skew?.  

# EXCEL EXERCISE  

2. (Stop-loss hedge). Write a VBA program to show the stop-loss hedged portfolio adjustments and cash flows for 100 long calls from the dealers' perspective with the following data:  

$$
S(0)=100;K=100;T=1;\quad r=8\%;\sigma=30\%;\&\mathrm{~realized~volatility}=50\%
$$  

# MATLAB EXERCISES  

3. Write a MATLAB program to observe the volatility payoff of stop loss hedged long call position and measure the performance of this strategy of replicating long call position when the frequency of adjustment is increased during the time interval until the call expires. Use the following data for the calculation  

$$
S(0)=100;K=100;T=1;\quad r=8\%;\sigma=30\%;\&\mathrm{{realized}~v o l a t i l i t y}=50\%
$$  

Plot the graph for the volatility payoff for 30 instances for these sets of adjustment. frequency [10, 20, 50, 100, 500]. Also show the performance of the method on the graph as a plot of mean return of the hedging strategy versus frequency of adjustment..  

4. (Stochastic volatility) Write a MATLAB program to observe the implied volatility smile for the. option based on the stock price having stochastic volatility. Use the following data for the calculation.  

$$
S(0)=100;K=100;T=0.5;\quad r=8\%;\sigma=30\%;\sigma_{\sigma}=10\%,r_{\sigma}=10\%
$$  

Plot the graph of the estimated implied volatility against the moneyness of the option.  

5. (Nongeometric Brownian motion) Write a MATLAB program to observe the implied volatility smile for the option based on the stock price following the dynamics of nongeometric Brownian motion. Use the following data for the calculation.  

$$
S(0)=100;K=100;T=0.5;\quad r=8\%;\sigma=30\%;\alpha=0.8
$$  

Plot the graph of the estimated implied volatility against the moneyness of the option. 6. (Stock price crashes and jumps)  

Write a MATLAB program to observe the implied volatility smile for the option based on the stock price having jumps (particularly crashes). Use the following data for the calculation.  

$$
S(0)=100;K=100;T=0.5;\quad r=8\%;\sigma=30\%;\lambda=0.3;\alpha_{J}=-2\%;\sigma_{J}=5\%
$$  

Plot the graph of the estimated implied volatility against the moneyness of the option.  

7. (VIX calculation) Using the S&P 500 option data on the chapter website (collected on July 4, 2013 for options expiring on July 25, 2013), calculate the VIX index value following the procedure discussed in the book. Take the risk-free interest rate value to be $5\%$ for the purpose of calculation. Also highlight the strike price $K_{0}$ and show the contribution by strike for all the options.  

# CAPS/FLOORS AND SWAPTIONS 17 WITH AN APPLICATION TO MORTGAGES  

# CHAPTER OUTLINE  

7.1 Introduction... . 591   
17.2 The Mortgage Market.. 592   
17.2.1 The Life of a Typical Mortgage 593   
17.2.2 Hedging the Position. 597   
17.2.3 Assumptions Behind the Model . 597   
17.2.4 Two Risks .. 598   
17.3 Swaptions.. . 599   
17.3.1 A Contractual Equation.. 601   
7.4 Pricing Swaptions ... 601   
17.4.1 Swap Measure. . 601   
17.4.2 The Forward Swap Rate as a Martingale . 604   
17.4.3 Swaption Value 605   
17.4.4 Real-World Complications ... 607   
17.5 Mortgage-Based Securities. .607   
17.6 Caps and Floors . 608   
17.6.1 Pricing Caps and Floors 610   
17.6.2 A Summary. . 612   
17.6.3 Caplet Pricing and the Smile. 612   
17.7 Conclusions. 613   
Suggested Reading . .613   
<ercises . 613   
EXCEL Exercises 617  
