# 20.5 THE VOLATILITY TERM STRUCTURE AND VOLATILITY SURFACES  

Traders allow the implied volatility to depend on time to maturity as well as strike price. Implied volatility tends to be an increasing function of maturity when short-dated volatilities are historically low. This is because there is then an expectation that volatilities will increase. Similarly, volatility tends to be a decreasing function of maturity when short-dated volatilities are historically high. This is because there is then an expectation that volatilities will decrease.  

Table 20.2 Volatility surface.   


<html><body><table><tr><td></td><td colspan="4">K/So</td></tr><tr><td></td><td>0.90 0.95</td><td>1.00</td><td>1.05</td><td>1.10</td></tr><tr><td>1 month</td><td>14.2</td><td>13.0 12.0</td><td>13.1</td><td>14.5</td></tr><tr><td>3 month</td><td>14.0</td><td>13.0</td><td>12.0 13.1</td><td>14.2</td></tr><tr><td>6 month</td><td>14.1</td><td>13.3</td><td>12.5 13.4</td><td>14.3</td></tr><tr><td>1 year</td><td>14.7</td><td>14.0</td><td>13.5 14.0</td><td>14.8</td></tr><tr><td>2 year</td><td>15.0</td><td>14.4</td><td>14.0 14.5</td><td>15.1</td></tr><tr><td>5 year</td><td>14.8</td><td>14.6</td><td>14.4 14.7</td><td>15.0</td></tr></table></body></html>  

Volatility surfaces combine volatility smiles with the volatility term structure to. tabulate the volatilities appropriate for pricing an option with any strike price and. any maturity. An example of a volatility surface that might be used for foreign currency options is given in Table 20.2..  

One dimension of Table 20.2 is $K/S_{0}$ ; the other is time to maturity. The main body of the table shows implied volatilities calculated from the Black-Scholes-Merton model. At any given time, some of the entries in the table are likely to correspond to options for which reliable market data are available. The implied volatilities for these options are calculated directly from their market prices and entered into the table. The rest of the table is typically determined using interpolation. The table shows that the volatility smile. becomes less pronounced as the option maturity increases. As mentioned earlier, this is what is observed for currency options. (It is also what is observed for options on most other assets.)  

When a new option has to be valued, financial engineers look up the appropriate. volatility in the table. For example, when valuing a 9-month option with a $K/S_{0}$ ratio of 1.05, a financial engineer would interpolate between 13.4 and 14.0 in Table 20.2 to obtain a volatility of $13.7\%$ . This is the volatility that would be used in the Black-ScholesMerton formula or a binomial tree. When valuing a 1.5-year option with a. $K/S_{0}$ ratio of 0.925, a two-dimensional (bilinear) interpolation would be used to give an implied volatility of $14.525\%$  

The shape of the volatility smile depends on the option maturity. As illustrated in. Table 20.2, the smile tends to become less pronounced as the option maturity increases. Define $T$ as the time to maturity and $F_{0}$ as the forward price of the asset for a contract. maturing at the same time as the option. Some financial engineers choose to define the volatility smile as the relationship between implied volatility and.  

$$
{\frac{1}{\sqrt{T}}}\ln\left({\frac{K}{F_{0}}}\right)
$$  

rather than as the relationship between the implied volatility and $K$ . The smile is then usually much less dependent on the time to maturity.  
