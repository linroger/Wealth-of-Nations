# 19.4 DELTA HEDGING  

The delta $(\Delta)$ of an option was introduced in Chapter 13. It is defined as the rate of change of the option price with respect to the price of the underlying asset. It is the. slope of the curve that relates the option price to the underlying asset price. Suppose. that the delta of a call option on a stock is 0.6. This means that when the stock price changes by a small amount, the option price changes by about $60\%$ of that amount. Figure 19.2 shows the relationship between a call price and the underlying stock price.. When the stock price corresponds to point A, the option price corresponds to point B,. and $\Delta$ is the slope of the line indicated. In general,  

$$
\Delta=\frac{\partial c}{\partial S}
$$  

where $c$ is the price of the call option and $S$ is the stock price.  

Suppose that, in Figure 19.2, the stock price is $\$100$ and the option price is. $\$10$ Imagine an investor who has sold call options to buy 2,000 shares of a stock. The investor's position could be hedged by buying $0.6\times2{,}000=1{,}200$ shares. The gain (loss) on the stock position would then tend to offset the loss (gain) on the option position. For example, if the stock price goes up by $\$1$ (producing a gain of $\$1,200$ on the shares purchased), the option price will tend to go up by $0.6\times\$1=\$0.60$ (producing a loss of $\$1,200$ on the options written); if the stock price goes down by $\$1$ (producing a loss of $\$1,200$ on the shares purchased), the option price will tend to go down by. $\$0.60$ (producing a gain of $\$1,200$ on the options written)..  

In this example, the delta of the trader's short position in 2,000 options is  

$$
0.6\times(-2,000)=-1,200
$$  

This means that the trader loses $1{,}200\Delta S$ on the option position when the stock price increases by $\Delta S$ The delta of one share of the stock is 1.0, so that the long position in. 1,200 shares has a delta of $+1{\,}200$ . The delta of the trader's overall position in our. example is, therefore, zero. The delta of the stock position offsets the delta of the option position. A position with a delta of zero is referred to as delta neutral..  

![](722afc9f9634048f0509a0966fbf781fedbbad951b62fe8c314f5f21450c6ef5.jpg)  
Figure 19.2 Calculation of delta.  

It is important to realize that, since the delta of an option does not remain constant, the trader's position remains delta hedged (or delta neutral) for only a relatively short period of time. The hedge has to be adjusted periodically. This is known as rebalancing. In our example, by the end of 1 day the stock price might have increased to $\$110$ . As indicated by Figure 19.2, an increase in the stock price leads to an increase in delta. Suppose that delta rises from 0.60 to 0.65. An extra $0.05\times2{,}000=100$ shares would then have to be purchased to maintain the hedge. A procedure such as this, where the hedge is adjusted on a regular basis, is referred to as dynamic hedging. It can be. contrasted with static hedging, where a hedge is set up initially and never adjusted. Static hedging is sometimes also referred to as "hedge-and-forget."  

Delta is closely related to the Black-Scholes-Merton analysis. As explained in Chapter 15, the Black-Scholes-Merton differential equation can be derived by setting. up a riskless portfolio consisting of a position in an option on a stock and a position in. the stock. Expressed in terms of $\Delta$ , the portfolio is  

$-1$ : option $+\Delta$ : shares of the stock.  

Using our new terminology, we can say that options can be valued by setting up a deltaneutral position and arguing that the return on the position should (instantaneously) be the risk-free interest rate.  

# Delta of European Stock Options  

For a European call option on a non-dividend-paying stock, it can be shown (see Problem 15.25) that the Black-Scholes-Merton model gives.  

$$
\Delta(\mathrm{call})=N(d_{1})
$$  

![](872a68ff35e74fc2bce6c98abf93743a6a084dbcd1ff5bdb26978d82ba0e2655.jpg)  
Figure 19.3 Variation of delta with stock price for (a) a call option and (b) a pu1 option on a non-dividend-paying stock (. $\kappa=50,r=0$ $\sigma=25\%$ $T=2$  

![](e5742019445b64a0696aa8deb7cd8d38ce77948b495951061ace73293e223cf7.jpg)  
Figure 19.4 Typical patterns for variation of delta with time to maturity for a call option $(S_{0}=50,r=0,\sigma=25\%)$  

where $d_{1}$ is defined as in equation (15.20) and. $N(x)$ is the cumulative distribution function for a standard normal distribution. The formula gives the delta of a long position in one call option. The delta of a short position in one call option is. $-N(d_{1})$ Using delta hedging for a short position in a European call option involves maintaining. a long position of. $N(d_{1})$ for each option sold. Similarly, using delta hedging for a long. position in a European call option involves maintaining a short position of. $N(d_{1})$ shares for each option purchased..  

For a European put option on a non-dividend-paying stock, delta is given by  

$$
\Delta(\mathrm{put})=N(d_{1})-1
$$  

Delta is negative, which means that a long position in a put option should be hedged with a long position in the underlying stock, and a short position in a put option should be hedged with a short position in the underlying stock. Figure 19.3 shows the variation of the delta of a call option and a put option with the stock price. Figure 19.4 shows the variation of delta with the time to maturity for in-the-money, at-the-money, and out-of-the-money call options.  

# Example 19.1  

Consider again the call option on a non-dividend-paying stock in Section 19.1 where the stock price is $\$49$ , the strike price is $\$50$ , the risk-free rate is $5\%$ , the time to maturity is 20 weeks $(=0.3846$ years), and the volatility is $20\%$ . In this case,  

$$
d_{1}={\frac{\ln(49/50)+(0.05+0.2^{2}/2)\times0.3846}{0.2\times{\sqrt{0.3846}}}}=0.0542
$$  

Delta is $N(d_{1})$ , or 0.522. When the stock price changes by $\Delta S$ , the option price changes by $0.522\Delta S$  

# Dynamic Aspects of Delta Hedging  

Tables 19.2 and 19.3 provide two examples of the operation of delta hedging for the example in Section 19.1, where 100,000 call options are sold. The hedge is assumed to be adjusted or rebalanced weekly and the assumptions underlying the Black-Scholes-- Merton model are assumed to hold with the volatility staying constant at $20\%$ . The initial value of delta for a single option is calculated in Example 19.1 as 0.522. This means that the delta of the option position is initially. $-100{,}000\times0{.}522$ , or $-52{,}200$ As soon as the option is written,. $\$2,557,800$ must be borrowed to buy 52,200 shares at a. price of $\$49$ to create a delta-neutral position. The rate of interest is. $5\%$ . An interest cost of approximately $\$2,500$ is therefore incurred in the first week..  

In Table 19.2, the stock price falls by the end of the first week to. $\$48.12$ . The delta of. the option declines to 0.458, so that the new delta of the option position is. $-45{,}800,$ This means that 6,400 of the shares initially purchased are sold to maintain the delta-neutral hedge. The strategy realizes $\$308,000$ in cash, and the cumulative borrowings at the end of Week 1 are reduced to. $\$2,252,300$ During the second week, the stock price reduces to $\$47.37$ , delta declines again, and so on. Toward the end of the life of the option, it. becomes apparent that the option will be exercised and the delta of the option. approaches 1.0. By Week 20, therefore, the hedger has a fully covered position. The.  

Table 19.2 Simulation of delta hedging. Option closes in the money and cost of hedging is $\$263,300$   


<html><body><table><tr><td>Week</td><td>Stock price</td><td>Delta</td><td>Shares purchased</td><td>Cost of shares purchased ($000)</td><td>Cumulativecost includinginterest ($000)</td><td>Interest cost ($000)</td></tr><tr><td>0</td><td>49.00</td><td>0.522</td><td>52,200</td><td>2,557.8</td><td>2,557.8</td><td>2.5</td></tr><tr><td>1</td><td>48.12</td><td>0.458</td><td>(6,400)</td><td>(308.0)</td><td>2,252.3</td><td>2.2</td></tr><tr><td>2</td><td>47.37</td><td>0.400</td><td>(5,800)</td><td>(274.7)</td><td>1,979.8</td><td>1.9</td></tr><tr><td>3</td><td>50.25</td><td>0.596</td><td>19,600</td><td>984.9</td><td>2,966.6</td><td>2.9</td></tr><tr><td>4</td><td>51.75</td><td>0.693</td><td>9,700</td><td>502.0</td><td>3,471.5</td><td>3.3</td></tr><tr><td>5</td><td>53.12</td><td>0.774</td><td>8,100</td><td>430.3</td><td>3,905.1</td><td>3.8</td></tr><tr><td>6</td><td>53.00</td><td>0.771</td><td>(300)</td><td>(15.9)</td><td>3,893.0</td><td>3.7</td></tr><tr><td>7</td><td>51.87</td><td>0.706</td><td>(6,500)</td><td>(337.2)</td><td>3,559.5</td><td>3.4</td></tr><tr><td>8</td><td>51.38</td><td>0.674</td><td>(3,200)</td><td>(164.4)</td><td>3,398.5</td><td>3.3</td></tr><tr><td>9</td><td>53.00</td><td>0.787</td><td>11,300</td><td>598.9</td><td>4,000.7</td><td>3.8</td></tr><tr><td>10</td><td>49.88</td><td>0.550</td><td>(23,700)</td><td>(1,182.2)</td><td>2,822.3</td><td>2.7</td></tr><tr><td>11</td><td>48.50</td><td>0.413</td><td>(13,700)</td><td>(664.4)</td><td>2,160.6</td><td>2.1</td></tr><tr><td>12</td><td>49.88</td><td>0.542</td><td>12,900</td><td>643.5</td><td>2,806.2</td><td>2.7</td></tr><tr><td>13</td><td>50.37</td><td>0.591</td><td>4,900</td><td>246.8</td><td>3,055.7</td><td>2.9</td></tr><tr><td>14</td><td>52.13</td><td>0.768</td><td>17,700</td><td>922.7</td><td>3,981.3</td><td>3.8</td></tr><tr><td>15</td><td>51.88</td><td>0.759</td><td>(900)</td><td>(46.7)</td><td>3,938.4</td><td>3.8</td></tr><tr><td>16</td><td>52.87</td><td>0.865</td><td>10,600</td><td>560.4</td><td>4,502.6</td><td>4.3</td></tr><tr><td>17</td><td>54.87</td><td>0.978</td><td>11,300</td><td>620.0</td><td>5,126.9</td><td>4.9</td></tr><tr><td>18</td><td>54.62</td><td>0.990</td><td>1,200</td><td>65.5</td><td>5,197.3</td><td>5.0</td></tr><tr><td>19</td><td>55.87</td><td>1.000</td><td>1,000</td><td>55.9</td><td>5,258.2</td><td>5.1</td></tr><tr><td>20</td><td>57.25</td><td>1.000</td><td>0</td><td>0.0</td><td>5,263.3</td><td></td></tr></table></body></html>  

Table 19.3 Simulation of delta hedging. Option closes out of the money and cost of hedging is $\$236,400$   


<html><body><table><tr><td>Week</td><td>Stock price</td><td>Delta</td><td>Shares purchased</td><td>Cost of shares purchased ($000)</td><td>Cumulativecost includinginterest ($000)</td><td>Interest cost ($000)</td></tr><tr><td>0</td><td>49.00</td><td>0.522</td><td>52,200</td><td>2,557.8</td><td>2,557.8</td><td>2.5</td></tr><tr><td>1</td><td>49.75</td><td>0.568</td><td>4,600</td><td>228.9</td><td>2,789.2</td><td>2.7</td></tr><tr><td>2</td><td>52.00</td><td>0.705</td><td>13,700</td><td>712.4</td><td>3,504.3</td><td>3.4</td></tr><tr><td>3</td><td>50.00</td><td>0.579</td><td>(12,600)</td><td>(630.0)</td><td>2,877.7</td><td>2.8</td></tr><tr><td>4</td><td>48.38</td><td>0.459</td><td>(12,000)</td><td>(580.6)</td><td>2,299.9</td><td>2.2</td></tr><tr><td>5</td><td>48.25</td><td>0.443</td><td>(1,600)</td><td>(77.2)</td><td>2,224.9</td><td>2.1</td></tr><tr><td>6</td><td>48.75</td><td>0.475</td><td>3,200</td><td>156.0</td><td>2,383.0</td><td>2.3</td></tr><tr><td>7</td><td>49.63</td><td>0.540</td><td>6,500</td><td>322.6</td><td>2,707.9</td><td>2.6</td></tr><tr><td>8</td><td>48.25</td><td>0.420</td><td>(12,000)</td><td>(579.0)</td><td>2,131.5</td><td>2.1</td></tr><tr><td>9</td><td>48.25</td><td>0.410</td><td>(1,000)</td><td>(48.2)</td><td>2,085.4</td><td>2.0</td></tr><tr><td>10</td><td>51.12</td><td>0.658</td><td>24,800</td><td>1,267.8</td><td>3,355.2</td><td>3.2</td></tr><tr><td>11</td><td>51.50</td><td>0.692</td><td>3,400</td><td>175.1</td><td>3,533.5</td><td>3.4</td></tr><tr><td>12</td><td>49.88</td><td>0.542</td><td>(15,000)</td><td>(748.2)</td><td>2,788.7</td><td>2.7</td></tr><tr><td>13</td><td>49.88</td><td>0.538</td><td>(400)</td><td>(20.0)</td><td>2,771.4</td><td>2.7</td></tr><tr><td>14</td><td>48.75</td><td>0.400</td><td>(13,800)</td><td>(672.7)</td><td>2,101.4</td><td>2.0</td></tr><tr><td>15</td><td>47.50</td><td>0.236</td><td>(16,400)</td><td>(779.0)</td><td>1,324.4</td><td>1.3</td></tr><tr><td>16</td><td>48.00</td><td>0.261</td><td>2,500</td><td>120.0</td><td>1,445.7</td><td>1.4</td></tr><tr><td>17</td><td>46.25</td><td>0.062</td><td>(19,900)</td><td>(920.4)</td><td>526.7</td><td>0.5</td></tr><tr><td>18</td><td>48.13</td><td>0.183</td><td>12,100</td><td>582.4</td><td>1,109.6</td><td>1.1</td></tr><tr><td>19</td><td>46.63</td><td>0.007</td><td>(17,600)</td><td>(820.7)</td><td>290.0</td><td>0.3</td></tr><tr><td>20</td><td>48.12</td><td>0.000</td><td>(700)</td><td>(33.7)</td><td>256.6</td><td></td></tr></table></body></html>  

hedger receives $\$5$ million for the stock held, so that the total cost of writing the option and hedging it is $\$263,300$  

Table 19.3 illustrates an alternative sequence of events such that the option closes out of the money. As it becomes clear that the option will not be exercised, delta approaches. zero. By Week 20 the hedger has a naked position and has incurred costs totaling $\$236,600$  

In Tables 19.2 and 19.3, the costs of hedging the option, when discounted to the. beginning of the period, are close to but not exactly the same as the Black-Scholes-- Merton price of $\$240,000$ . If the hedging worked perfectly, the cost of hedging would,. after discounting, be exactly equal to the Black-Scholes-Merton price for every simulated stock price path. The reason for the variation in the hedging cost is that the hedge is rebalanced only once a week. As rebalancing takes place more frequently, the variation in the hedging cost is reduced. Of course, the examples in Tables 19.2 and 19.3 are idealized in that they assume that the volatility is constant and there are no transaction costs..  

Table 19.4 shows statistics on the performance of delta hedging obtained from one. million random stock price paths in our example. The performance measure is calculated, similarly to Table 19.1, as the ratio of the standard deviation of the cost of hedging the option to the Black-Scholes-Merton price of the option. It is clear that delta hedging is a great improvement over a stop-loss strategy. Unlike a stop-loss strategy, the performance of delta-hedging gets steadily better as the hedge is monitored more frequently.  

Table 19.4 Performance of delta hedging. The performance measure is the ratio of the standard deviation of the cost of writing the option and hedging it to the theoretical price of the option.   
Time between hedge   


<html><body><table><tr><td>rebalancing (weeks):</td><td>5</td><td>4</td><td>2</td><td>1</td><td>0.5</td><td>0.25</td></tr><tr><td>Performance measure:</td><td>0.42</td><td>0.38</td><td>0.28</td><td>0.21</td><td>0.16</td><td>0.13</td></tr></table></body></html>  

Delta hedging aims to keep the value of the financial institution's position as close to unchanged as possible. Initially, the value of the written option is $\$240,000$ . In the situation depicted in Table 19.2, the value of the option can be calculated as $\$414,500$ in Week 9. (This value is obtained from the Black-Scholes-Merton model by setting the stock price equal to $\$53$ and the time to maturity equal to 11 weeks.) Thus, the financial institution has lost $\$12300$ on its short option position. Its cash position, as measured by the cumulative cost, is $\$1,442,900$ worse in Week 9 than in Week 0. The value of the shares held has increased from $\$2,557,800$ to $\$4,171,100$ The net effect of all this is that the value of the financial institution's position has changed by only $\$4,100$ between Week 0 and Week 9.  

# Where the Cost Comes From  

The delta-hedging procedure in Tables 19.2 and 19.3 creates the equivalent of a long position in the option. This neutralizes the short position the financial institution created by writing the option. As the tables illustrate, delta hedging a short position generally involves selling stock just after the price has gone down and buying stock just after the price has gone up. It might be termed a buy-high, sell-low trading strategy! The average cost of $\$240,000$ comes from the present value of the difference between the price at which stock is purchased and the price at which it is sold.  

# Delta of a Portfolio  

The delta of a portfolio of options or other derivatives dependent on a single asset whose price is $S$ is  

$$
\frac{\partial\Pi}{\partial S}
$$  

where $\Pi$ is the value of the portfolio.  

The delta of the portfolio can be calculated from the deltas of the individual options in the portfolio. If a portfolio consists of a quantity. $w_{i}$ of option $i$ $(1\leq i\leq n$ ), the delta of the portfolio is given by.  

$$
\Delta=\sum_{i=1}^{n}w_{i}\Delta_{i}
$$  

where $\Delta_{i}$ is the delta of the ith option. The formula can be used to calculate the. position in the underlying asset necessary to make the delta of the portfolio zero. When this position has been taken, the portfolio is delta neutral..  

Suppose a financial institution has the following three positions in options on a stock:  

1. A long position in 100,000 call options with strike price $\$55$ and an expiration date in 3 months. The delta of each option is 0.533.   
2. A short position in 200,000 call options with strike price $\$56$ and an expiration date in 5 months. The delta of each option is 0.468.   
3. A short position in 50,000 put options with strike price $\$56$ and an expiration date in 2 months. The delta of each option is. $-0.508$  

The delta of the whole portfolio is  

$$
100,000\times0.533-200,000\times0.468-50,000\times(-0.508)=-14,900
$$  

This means that the portfolio can be made delta neutral by buying 14,900 shares.  

# Transaction Costs  

Derivatives dealers usually rebalance their positions once a day to maintain delta neutrality. When the dealer has a small number of options on a particular asset, this is liable to be prohibitively expensive because of the bid-ask spreads the dealer is subject to on trades. For a large portfolio of options, it is more feasible. Only one trade in the underlying asset is necessary to zero out delta for the whole portfolio. The bid-ask spread transaction costs are absorbed by the profits on many different trades.  
