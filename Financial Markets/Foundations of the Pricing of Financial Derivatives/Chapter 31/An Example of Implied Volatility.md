# 31.2 AN EXAMPLE OF IMPLIED VOLATILITY

Table 31.1 shows the closing ask prices on September 17 of a particular year for options on the S&P 500 expiring in approximately one month, specifically October 19. These options are among the most active of all listed options, and they are European style, so we can use the Black-Scholes-Merton model to price them. These prices were closing ask quotes, meaning that they represent the prices at the close of trading at which the dealer was offering to buy the options. Hence, these are the prices at which the public would expect to buy. At that time, the S&P 500 closed at 2,904.31, so this is the price of the underlying.

To use the Black-Scholes-Merton model, we need some additional information, which was obtained from various sources. The continuously compounded risk-free rate is estimated to be $2.02\%$ , and the continuously compounded dividend yield is estimated at. $1.73\%$ . The option expires in 32 days, so the value inserted into the model for the time to expiration is $31/365=0.0849$ . The implied volatilities can be derived using a num-. ber of different search routines, including the secant method, the Brent method, and the Newton-Raphson method.2 These methods are widely available on many computer platforms. With most methods, the process is to insert the option price and all other input values except the volatility. We then make an initial guess at the volatility, whereupon the program computes the option value and compares it to the market price, continuing to guess at the volatility until the model price is within 0.001 of the quoted market price.3

TABLE 31.1 Option Quotes


<html><body><table><tr><td colspan="2">SPX (S&P 500 Index); Closing Ask Prices for September 17, 20yy; Options Expire on October 19.</td></tr><tr><td>ExercisePrice Calls</td><td>Puts</td></tr><tr><td>2880</td><td>21.0</td></tr><tr><td>50.5 2885 46.7</td><td>22.3</td></tr><tr><td>2890 43.1</td><td>23.6</td></tr><tr><td>2895 39.5</td><td>25.1</td></tr><tr><td>2900 36.1</td><td>26.6</td></tr><tr><td>2905 32.8</td><td>28.4</td></tr><tr><td>2910 29.6</td><td>30.3</td></tr><tr><td>2915 26.6</td><td>32.3</td></tr><tr><td>2920 23.8</td><td>34.5</td></tr></table></body></html>

Suppose we wished to know which of these options is the most expensive. First, let us consider the calls. We know that deeper-in-the-money calls, meaning those with the lowest exercise prices, are more expensive than calls that are less deep-in-the-money, at-the-money, or out-of-the-money. That fact is certainly natural. But after taking moneyness into account, we wish to know if some of the calls are more expensive than others. Likewise, for puts where the most expensive ones are those with high exercise prices. After taking moneyness into account, are some puts still more expensive than others?

Now, it should be the case that because all of the options are on the same underlying, the same volatility would be used by the market to price all of the options. Hence, we cannot use volatility to determine which option is more expensive. Or can we? It turns out that we can. Table 31.2 shows that indeed some options are more expensive than others, even after taking into account the logical reasons why certain ones would be more expensive. Those with higher volatilities are more expensive after accounting for other factors.

From Table 31.2, we see that the call implied volatilities range from $9.08\%$ to $10.89\%$ and the put implied volatilities range from $7.79\%$ to $9.52\%$ . The results are graphed in Figure 31.2.

TABLE 31.2 Implied Volatilities of SPX Options


<html><body><table><tr><td>Exercise Price</td><td>Calls</td><td>Puts</td></tr><tr><td>2880</td><td>0.1089</td><td>0.0952</td></tr><tr><td>2885</td><td>0.1066</td><td>0.0931</td></tr><tr><td>2890</td><td>0.1044</td><td>0.0907</td></tr><tr><td>2895</td><td>0.1018</td><td>0.0886</td></tr><tr><td>2900</td><td>0.0996</td><td>0.0862</td></tr><tr><td>2905</td><td>0.0973</td><td>0.0843</td></tr><tr><td>2910</td><td>0.0949</td><td>0.0822</td></tr><tr><td>2915</td><td>0.0928</td><td>0.0800</td></tr><tr><td>2920</td><td>0.0908</td><td>0.0779</td></tr></table></body></html>

![](images/c5fd32c49fbcc943ada1e37b429c57e549b94d28c55bde0a51142ce08dc38e47.jpg)
FIGURE 31.2 Graph of Implied Volatilities by Exercise Price

Note that we observe a pattern in which the implied volatilities monotonically decrease. with a higher exercise price. The relationship between the option exercise price and the implied volatility has been documented at the least since the time of the massive stock market crash of October 19, 1987. When first observed, the implied volatilities were. $u\cdot$ shaped giving the appearance of a smile. Hence this relationship was named the volatility smile.4 In more recent years, the smile has mostly disappeared, and the relationship has sometimes been referred to as a skew or even a smirk, reflecting the appearance of a sort of snarky half smile.5 Note also that we obtain different implied volatilities depending on whether we are looking at calls or puts. There is no a priori reason why puts and calls should have different implied volatilities but obviously they do..

We now turn to options on the ETF SPY, a very popular index option. Recall from Chapter 1, SPY is the exchange-traded fund of the S&P 500 Index.6 Options on SPY are American style; hence, early exercise must be incorporated into the option pricing model. The results reported here are based on a dividend-adjusted binomial model that captures potential early exercise.

Figure 31.3 illustrates actual SPY option prices and exercise values on the left and reported implied volatilities on the right for selected dates before and during the great financial crisis starting in 2008.7 As is common, we select the nearest option that expires at least more than one month from the observation date. The days to maturity range from 47 to 53. Recall that the SPY is an exchange-traded fund that seeks to mimic the total return of the S&P 500 index. We normalize the exercise price by dividing by the stock price to ease comparison across time. Further, we fix the axis range, improving the ability to see changes over time. Thus, the call (put) option is out-of-the-money (in-the-money) when

![](images/299875415642f4d808957ffce11c8dccbff7dd82511021fec7e42f681b176c64.jpg)
FIGURE 31.3  Selected Graphs of SPY Option Prices and Implied Volatilities by Normalized Exercise Price, 2006-2008

Panel C. March 31, 2008

![](images/069c198a9ffe14c701b99a6537f4cc68dea77a04dd865c6c18de77aebc5ed764.jpg)
Panel D. June 30, 2008

![](images/be337ba0a26d5e0cf34992e9aa4f3fb1872a561632a413cfeace9f72aa7a141c.jpg)

![](images/0159c7fcac819dbc3295eb9193578dcf5347419a07c902df5d4d15be9e6bdf0b.jpg)
Panel E. September 30, 2008

![](images/1fd27508cd963791bf662a9a2e7eb09b84d9ce5706dc207d336b397a1843c471.jpg)

![](images/4a5df563d3598e98574d71c1f021e18bc303992458e838c782b2559e4c36e423.jpg)

# Panel F. December 31, 2008

# FIGURE 31.3Continued

the exercise price divided by the stock price is high (low). Based on these graphs, the SPY options clearly reflect increasing uncertainty measured by increasing implied volatilities. Notice as we move from year-end 2006 through 2008, the option prices increase (left side) and thus so do the implied volatilities (right side). It seems likely that the unfolding of the financial crisis resulted in these increases. At times the implied volatilities for calls and puts are virtually indistinguishable. See, for example, the right-side figures on December 29, 2006, March 31, 2008, and December 31, 2008. On these dates, both puts and calls for various exercise prices resulted in nearly identical implied volatilities. Finally, note that the option prices tend toward the exercise value as we move further in- or out-of-the-money.

Notice in Figure 31.3 that on June 30, 2008, the put implied volatilities were above. those of the calls, whereas on September 30, 2008, the call volatilities were above those. of the puts. This behavior results in the intersection of calls and puts being lower. Some. market participants view this intersection point as "lean" in the options market. Thus, on September 30, 2008, the market lean was bullish, whereas on June 30, 2008, the market. lean was bearish.

Figure 31.4 illustrates the same type of input data as Figure 31.3 but in this case for. quarter-end observations in 2009. We see that as the financial crisis ended, the options market prices dropped and, hence, so did implied volatilities..

![](images/34379bea333bfa5b86bc50a3d8f4af225a721183cb252dad093b54b4837cdc6e.jpg)
FIGURE 31.4 Selected Graphs of SPY Option Prices and Implied Volatilities by Normalized Exercise Price, 2009

Panel B. June 30, 2009

![](images/5932e25fa7f28e49d9f397963b405beaa42fd4092416df25fc52916306a69816.jpg)

# Panel D. December 31, 2009

# FIGURE 31.4 Continued

Figure 31.5 illustrates the same data as Figures 31.3 and 31.4 for year-end 2017,. a relatively normal time period. We see that well after the financial crisis was over, the. options market prices dropped and, hence, so did implied volatilities. Also, notice that the put option implied volatilities are nonexistent when the put is deep-in-the-money because. the put prices are essentially at their exercise values..

The existence of multiple implied volatilities, regardless of whether they arrange themselves in a smile-like pattern, should be somewhat disconcerting. How can the market be telling us that there is more than one volatility for the S&P 500? Clearly there is something wrong with the Black-Scholes-Merton model, which is that it fails to consider all of the factors that enter into the pricing of an option. It accounts for the asset price, the exercise price, the time to expiration, the dividends, and the risk-free rate. The implied volatility is more or less a catchall term, capturing whatever variables are missing, as well as the possibility that the model is improperly specified or blatantly wrong.

What we learn, however, is what we wanted to know: Which options are the most. expensive? We see that the calls and puts with the lowest exercise price are the most expen-. sive options. But what is so puzzling is that in the Black-Scholes-Merton world, no option should be more expensive than any other option after accounting for the exercise price and.

![](images/60336e0306a67fece68fe4e00a507ef8256d180c358a703b49d99b99159f7700.jpg)
FGURE 31.5 Selected Graphs of SPY Option Prices and Implied Volatilities by Normalized Exercise Price, December 29, 2017

time to expiration. Any option should be a perfect substitute for any other option, given the ability to replicate using the concept of delta.
