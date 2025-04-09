# 14.10 CONCLUSIONS  

This chapter was devoted to the connections between the swap, FRA, and bond markets. Our discussion led us to the issue of constructing a satisfactory yield curve, which is the fundamental task of a financial engineer. Two main tools were introduced in the chapter. The first was the $T.$ forward measures and the second was the related measure change technology. This permitted setting up convenient arbitrage-free dynamics for a sequence of forward rates. These dynamics were then used as a tool for calculating the desired quantities using the formulas that connect swap rates, forward rates, and their derivatives.  

The next topic was the Forward LIBOR Model. Here, the essential idea was to obtain sequential correction factors to express the dynamics of various forward rates under a single forward measure.  

# SUGGESTED READING  

The standard readings for this chapter will make interesting reading for a financial engineer. Brace et al. (1997) and Jamshidian (1997) are the fundamental readings. Miltersen et al. (1997) is another important reference. Glasserman and Zhao (2ooo) is a good source on the discretization of BGM models. Finally, the text by Brigo and Mercurio (2006) provides a comprehensive treatment of all this material. Rebonato (2002) is a good introduction.  

# EXERCISES  

1. You are given the following quotes for liquid FRAs paid in arrears. Assume that all time intervals are measured in months of 30 days..  

<html><body><table><tr><td>Term Bid/Ask</td></tr><tr><td>3×6 4.5-4.6</td></tr><tr><td>6×9 4.7-4.8</td></tr><tr><td>9 × 12 5.0-5.1</td></tr><tr><td>12 × 15 5.5-5.7</td></tr><tr><td>15 × 18 6.1-6.3</td></tr></table></body></html>  

You also know that the current 3-month LIBOR rate is $4\%$ a. Calculate the discount bond prices $B(t_{0},t_{i})$ , where $t_{i}=6$ ,9, 12, 15, and 18 months. b. Calculate the yield curve for maturities 018 months. c. Calculate the swap curve for the same maturities.. d. Are the two curves different? e. Calculate the par yield curve. f. Calculate the zero-coupon yield curve.  

2. You are given the following quotes for liquid swap rates. Assume that all time intervals are measured in years.  

<html><body><table><tr><td>Term Bid/Ask</td></tr><tr><td>2 6.2-6.5</td></tr><tr><td>3 6.4-6.7</td></tr><tr><td>4 7.0-7.3</td></tr><tr><td>5 7.5-7.8</td></tr><tr><td>6 8.1-8.4</td></tr></table></body></html>  

You know that the current 12-month LIBOR rate is $5\%$  

a. Calculate the FRA rates for the next 5 years, starting with a $1\times2$ FRA.   
b. Calculate the discount bond prices $B(t_{0},t_{i})$ , where $t_{i}=1,....,6$ years.   
c. Calculate the yield curve for maturities of 0-18 months.   
d. Calculate the par yield curve.  

3. Going back to the data given in Exercise 2, calculate the following:  

a. The bid--ask on a forward swap that starts in 2 years with maturity in 3 years. The swap is against 12-month LIBOR.   
b. The forward price of a coupon bond that will be delivered at time 2. The bond pays coupon $7\%$ and matures in 2 years.  

# EXCEL EXERCISES  

4. Write a VBA program to determine the bond price and swap rates from the set of forward. rates given below and plot the yield curves along with the swap curve. Comment on their characteristics.  

<html><body><table><tr><td>Term (Month)</td><td>Forward Rate</td></tr><tr><td>0</td><td>4.00%</td></tr><tr><td>3</td><td>4.50%</td></tr><tr><td>6</td><td>4.70%</td></tr><tr><td>6</td><td>5.00%</td></tr><tr><td>12</td><td>5.50%</td></tr><tr><td>15</td><td>6.10%</td></tr><tr><td>18</td><td>6.40%</td></tr><tr><td>21</td><td>6.46%</td></tr><tr><td>24</td><td>7.00%</td></tr></table></body></html>  

5. Write a VBA program to determine the bond price and forward rates from the set of swap rates below with the term of 1 year as the input. Assume that the current LIBOR rate is $5.00\%$ . Plot the yield curves along with swap curve to observe their characteristic.  

<html><body><table><tr><td>Term (Years)</td><td>Swap Rate</td></tr><tr><td>2</td><td>6.20%</td></tr><tr><td>3</td><td>6.40%</td></tr><tr><td>4</td><td>7.00%</td></tr><tr><td>5</td><td>7.50%</td></tr><tr><td>6</td><td>8.10%</td></tr><tr><td>7</td><td>8.70%</td></tr></table></body></html>  

6. Write a VBA program to determine the FRA rates and swap rates from the set of bond prices. below as the input and plot the yield curves along with swap curve. Comment on their characteristics.  

<html><body><table><tr><td>Time (Month)</td><td>Bond Price</td></tr><tr><td>0</td><td>100.00</td></tr><tr><td>3</td><td>99.01</td></tr><tr><td>6</td><td>97.91</td></tr><tr><td>9</td><td>96.77</td></tr><tr><td>12</td><td>95.58</td></tr><tr><td>15</td><td>94.28</td></tr><tr><td>18</td><td>92.86</td></tr><tr><td>21</td><td>91.40</td></tr><tr><td>24</td><td>89.95</td></tr><tr><td>27</td><td>88.40</td></tr></table></body></html>  

7. Write a VBA program to determine the price of an interest rate swap which makes a floating payment every 6 months at the rate equal to USD LIBOR rate against a fixed rate of $5.10\%$ for the notional amount of $\$10,000$ . Use the data given in the "Input' worksheet for carrying out the calculation.  

<html><body><table><tr><td>Time (Years)</td><td>Forward Rate</td></tr><tr><td>0.00</td><td>5.70%</td></tr><tr><td>0.50</td><td>5.18%</td></tr><tr><td>1.00</td><td>5.83%</td></tr><tr><td>1.50</td><td>5.10%</td></tr><tr><td>2.00</td><td>5.75%</td></tr><tr><td>2.50</td><td>5.74%</td></tr><tr><td>3.00</td><td>5.28%</td></tr><tr><td>3.50</td><td>5.65%</td></tr><tr><td>4.00</td><td>5.53%</td></tr></table></body></html>  

8. (Cross-Currency Swap) Write a VBA program to determine the cross-currency swap rate based on the information below. The fixed payment is made in USD in the exchange for the floating payment (in USD) rate equal to the GBP LIBOR at every 3 months. Also include the. exchange of notional amount 10,000 against payment in dollars at their corresponding exchange spot rate during initiation and maturity of the swap in the swap rate calculation.  

Notional amount $(\mathbf{GBP})=\pounds10\r,000$ , notional amount $(\mathrm{USD})=\mathbb{\mathbb{S}}20\mathrm{,000}$  

<html><body><table><tr><td>Time (Month)</td><td>Forward Rate (USD)</td><td>Exchange Rate (USD/GBP)</td><td>LIBOR Rate (GBP)</td></tr><tr><td>0</td><td>4.00%</td><td>2.0000</td><td>5.70%</td></tr><tr><td>3</td><td>4.50%</td><td>2.0225</td><td>5.18%</td></tr><tr><td>6</td><td>4.70%</td><td>2.0150</td><td>5.83%</td></tr><tr><td>9</td><td>5.00%</td><td>1.9875</td><td>5.10%</td></tr><tr><td>12</td><td>5.50%</td><td>1.9750</td><td>5.75%</td></tr><tr><td>15</td><td>6.10%</td><td>1.9685</td><td>5.74%</td></tr><tr><td>18</td><td>6.30%</td><td>1.9480</td><td>5.28%</td></tr><tr><td>21</td><td>6.36%</td><td>1.9325</td><td>5.65%</td></tr><tr><td>24</td><td>6.40%</td><td>1.9300</td><td>5.53%</td></tr></table></body></html>  

# MATLAB EXERCISE  

9. a. Write a MATLAB program to determine the bond price and swap rate from the given set of FRA rates and calculate the yield, par yield, and zero-coupon yield. The input data are to be read from the "Forward' worksheet of the "Data.xlsx"' file on the chapter webpage. Now plot all the curves simultaneously and comment on their characteristics. b. Write a MATLAB program to determine the bond price and FRA rate from the given set of forward swap rates and calculate the yield, par yield, and zero-coupon yield. The input data are to be read from the "Swap" worksheet of "Data.xlsx' file. Now plot all the curves simultaneously and comment on their characteristics. c. Write a MATLAB program to determine the FRA price and swap rate from the given set of bond prices and calculate the yield, par yield, and zero-coupon yield. The input data are to be read from the "Bond" worksheet of "Data.xlsx"' file. Now plot all the curves simultaneously and comment on their characteristics.  

This page intentionally left blank  

# TOOLS FOR VOLATILITY ENGINEERING, VOLATILITY SWAPS, AND VOLATILITY TRADING  

# 15  

# CHAPTER OUTLINe  
