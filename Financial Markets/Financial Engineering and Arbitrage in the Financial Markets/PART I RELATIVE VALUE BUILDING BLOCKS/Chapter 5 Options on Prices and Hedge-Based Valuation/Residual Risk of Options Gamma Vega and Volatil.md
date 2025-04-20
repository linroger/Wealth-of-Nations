---
tags:
  - delta_hedging
  - gamma_risk
  - options_pricing
  - vega_risk
  - volatility_risk
aliases:
  - Delta Hedge Risk
  - Gamma Vega Volatility
  - Residual Risk
key_concepts:
  - Binomial model
  - Delta hedging
  - Gamma risk
  - Vega risk
  - Volatility assumption
---

# 5.8 RESIDUAL RISK OF OPTIONS: GAMMA, VEGA, AND VOLATILITY  

Can anything go wrong with the delta hedge? If the dealer adheres strictly to the binomial algorithm, then as long as the stock follows one of the considered paths, the answer is no. Since the Black-Scholes model considers a continuum of paths, then also as long as the stock follows one of the considered paths, the answer is no. So, can anything go wrong? Unfortunately, yes.  

What can go wrong is that the local and total volatility of the stock is greater than that assumed in estimating the cost of the hedge. Locally, over a small interval of time, the stock can jump, rather than move in a "smooth' fashion. The delta hedger of a call will buy at a higher price, and the put hedger will short at a lower price, than that assumed by the model. This is measured by the gamma risk. Totally, the volatility over the entire life of the option may turn out to be higher than that used up front to estimate the cost of the hedge. Some local movements may be large, but may be offset by some movements that are small. Yet if overall the stock moves more than the assumed annualized volatility, then the hedge will cost more than the model predicts. This is measured by the vega risk. Gamma and vega are closely related.  

The main assumption of delta hedging is that the range of possible stock price outcomes. considered is constrained by the assumed volatility of the stock. The volatility is the square root of the variance. The variance is the expected value of the squared deviations of the stock's return from the mean return over a given period. The Black-Scholes model requires volatility as an input. It then considers all the stock price paths that are within a certain range bounded by. the volatility. That is, the stock price movements, period-to-period and overall, are restricted to be less than a certain number. This can be portrayed graphically as all the paths within. an expanding cylinder of outcomes, with the greatest density of paths close to the center (see Figure 5.26). The edges of the cylinder are not binding, but the probability of outcomes outside, or far from the center, is minuscule. That is, we assume a bell-shaped normal curve for the path of stock returns.  

![](a2dc22498ebc186dab5e20fa0c3943f6bdc2c983bb9d2c80dba622df6f4b0a80.jpg)  
Figure 5.26Stock price vs time  

![](53fa6179d817f50649aa86060e9d4bae8a1f7345219e1d163bc66c06dcf00539.jpg)  
Figure 5.27Example 2b revisited - mishedge $\boldsymbol{C}=m a x(S-55,0))$  

In the binomial set-up, the volatility translates directly to the width of the span of potential outcomes. Thus a $30\%$ annual volatility may translate into a 70-20 span as in Example 2b,. but a $40\%$ volatility may result in a wider span of 80-15 as in Example 2c..  

If a dealer underestimates the actual volatility that the stock will experience during the life of the option, then he will discover that he has sold the option too cheaply. The premium he has. charged will not cover the cost of the replicating strategy. In Black-Scholes, that means that the dealer should have used a higher volatility input. In the binomial model, the assumed span should have been wider. Note that the dealer is not asked to predict the really unpredictable,. i.e. whether the stock will go up or down, but only the slightly unpredictable, i.e. whether the. stock will fluctuate a lot between now and expiry..  

Let us see in our binomial model what happens if the seller of a 55 call underestimates volatility. Suppose he uses the model as in Example 2b, describing potential outcomes as 70 and 20. He charges $\$9–6/11$ for the call and borrows $\$5-5/11$ . With the total amount of $\$15$ he buys the prescribed 0.3000 shares at $\$50$ a share. But the stock proves more volatile, i.e. it attains either 80 or 15. The dealer will lose money whether the stock goes up or down (see Figure 5.27).  

If the stock goes up to 80, the 0.3 shares are worth $\$24$ , but the dealer owes $\$25$ to the option holder and $\$6$ on his borrowing. If the stock goes down to $\$15$ , the 0.3 shares are worth $\$4.50$ but the dealer owes $\$0$ to the option holder and $\$6$ on his borrowing.  

The primary risk of any option dealer is not the direction the underlying asset may take, but the exposure to the volatility of the underlying asset. A sold option results in a short volatility position. If the actual volatility of the underlying asset increases, the dealer loses money; if it decreases, the dealer makes money. A bought option results in a long volatility position. If the actual volatility of the underlying asset increases, the dealer makes money; if it decreases, the dealer loses money. The sensitivity of an option to the volatility input is called the vega of the option. The unit is the dollar change in the value of the option per $1\%$ change in volatility. The vega of an option depends on the maturity of the option, the strike level relative to the current underlying asset's price (in-the-moneyness), and the interest rate. In general, the longer the time to expiry, the higher the vega as there is more time to lose money on mishedging. Also, the closer to at-the-money the option is, the greater the vega. Deep in-the-money options and deep out-of-the-money options have low vegas.  

Option portfolios can also be described as long or short volatility. A long volatility portfolio may have bought and sold options, but the majority are bought. The "majority"' here means that the net vega position in terms of net dollar sensitivity of the portfolio to a $1\%$ change in the volatility (long vega options minus short vega options) is positive. A short volatility portfolio has a net negative vega. With many bought and sold options in the portfolio, the overall vega of the portfolio changes over time and as the price of the underlying asset fluctuates.  

The vega risk of an option portfolio cannot be hedged with positions in the underlying asset, but only with option positions.  

# 5.8.1 Implied Volatility  

Running an option book is a chicken-and-egg game. To price options, we need a volatil-. ity input. To get that volatility input, we need to observe the prices of options. So which comes first?  

In order to price the options we buy and sell, we need the volatility input into a pricing model (Black-Scholes, binomial, other). Different volatility assumptions will result in different hedge ratios, i.e. positions in the underlying assets. Suppose we have somehow guessed the right input, we priced all the options, computed the hedges, and bought or shorted the right net number of shares, bonds, or currency underlying the options in our portfolio. Our portfolio is now free of directional risk. Whether the underlying asset price goes up or down, we do not show any profit or loss.  

But how do we guess the volatility input? We could perform a statistical analysis of the past. movements in the asset's price and compute the standard deviation of the returns on the asset. This historical volatility could then be put into the model. However that would be tantamount to betting that the historical level of price variation will continue into the future. While we would not be betting directionally, we would be betting that the past cost of hedging would continue into the future. That is not a foolproof method..  

A better way is to try to get at the market's current consensus of the future price volatility -- not because the consensus will always be right, but because the consensus will determine the. price of completely insuring our portfolio against the changing cost of the hedge. Where can we obtain the consensus estimate? In the option prices that we and other people charge..  

Here is how this circular process works. Before we use the model to price our portfolio, we. examine currently quoted option prices. Dealers who quote these prices include their estimates of future volatility as input into the same models to calculate their manufacture costs. We can back out what those estimates are by using our model to see what volatility input yields the prices they quote. This implied volatility can then be put into our own model to price and hedge our portfolio.  

Using the implied volatility is superior to using the historical volatility as an input into. an option model, because we can actually trade options that have been priced using implied. volatilities. After all, we have obtained those implied volatilities from actual option quotes. And we can use those options to completely eliminate our vega risk. Suppose our portfolio is long volatility and market neutral. That is, we have bought more options than we sold, but we bought or shorted enough of the underlying asset to eliminate the directional risk. We compute the sensitivity of our portfolio to a $1\%$ change in the volatility input, and sell new options at the quoted prices by choosing the amount sold so that those sold options have the same sensitivity to a $1\%$ volatility change. We also neutralize the directional risk of the newly sold options through a delta hedge. Now our combined portfolio is directional risk-free and vega risk-free!  

The only way for a delta-cum-vega hedger to make money from trading options is to charge more or pay less for options than the fair value of the model. The hedger's profit comes purely from the bid-ask spread and not from speculation on any explicit directional (price, rate) or implicit second-order (volatility) variable. Those primary and secondary risks are completely "sold off' by trading in the underlying assets and offsetting options.  

Many dealers do not eliminate their vega risk completely and thus can be considered arbitrageurs/hedgers in first-order risk (directional) and speculators in second-order risk (volatil-. ity). They can, but choose not to, offset their volatility risk for two reasons. First, vega-hedging. by buying/selling offsetting options is expensive and eats into profits. Second, the dealer's primary competence as a wholesaler of options lies in knowing the changing cost of reinsurance.  

The only time one may consider using historical instead of implied volatilities as inputs into a model is the situation when there are no relevant options being quoted. By relevant options we mean options on the same underlying asset, with similar strike levels and for expiries similar to the options in our portfolio. This is typical for very long-term options. The reason for matching strikes and expiries is discussed below.  

# 5.8.2 Volatility Smiles and Skews  

An option valuation model is never perfect. It is a simplification of the potential price or rate. movements. The total scope of those movements is constrained in a probability sense by the volatility input. The paths close to the mean are more likely than those away from the mean. The paths are continuous, i.e. prices do not jump discretely. Volatility is assumed constant in returns for the entire period, for sub-periods, and across price levels. In Black-Scholes, the. price movements are log-normal. This means that as the price rises, the percentage changes. remain on average the same, but absolute movements are assumed to grow. In currency option. models, the FX rate may be assumed to fluctuate, but the interest rates are not. In interest rate option models, all rates may be assumed to move in parallel, or close to that. These are all assumptions necessary to make the math of the model tractable, but they may not all be realistic.  

For these and perhaps many other reasons, it is well known that options on the same underlying asset require different volatility inputs for different strikes and expiries..  

First consider the implied volatilities as published October 17, 2003 by the Federal Reserve for at-the-money currency options as of the end of the previous month (Table 5.1)..  

In Table 5.1, we are not shown strike levels, but for each currency the implied volatilities. change with the expiry date. They tend to decrease as the time to expiry increases. This phenomenon has been alleged to have to do with the distinction between the realized or \*This release provides survey ranges of implied volatility mid rates for at the money options as of 11:00 am. The quotes are for contracts of at least $\$10$ million with a prime counterparty.  

Table 5.1 Implied volatility rates for foreign currency options\* 9/30/2003   


<html><body><table><tr><td></td><td>1week</td><td>1month</td><td>2months</td><td>3months</td><td>6months</td><td>12months</td><td>2 years</td><td>3 years</td></tr><tr><td>EUR</td><td>12.6</td><td>11.8</td><td>11.6</td><td>11.4</td><td>11.4</td><td>11.3</td><td>11.2</td><td>11.2</td></tr><tr><td>JPY</td><td>14.3</td><td>12.5</td><td>11.6</td><td>10.8</td><td>10.3</td><td>10.1</td><td>10.0</td><td>9.9</td></tr><tr><td>CHF</td><td>12.7</td><td>11.9</td><td>11.7</td><td>11.5</td><td>11.5</td><td>11.5</td><td>11.5</td><td>11.4</td></tr><tr><td>GBP</td><td>10.3</td><td>9.8</td><td>9.6</td><td>9.4</td><td>9.3</td><td>9.3</td><td>9.4</td><td>9.4</td></tr><tr><td>CAD</td><td>10.1</td><td>9.7</td><td>9.5</td><td>9.4</td><td>9.1</td><td>8.9</td><td>8.9</td><td>8.8</td></tr><tr><td>AUD</td><td>13.2</td><td>12.3</td><td>11.9</td><td>11.4</td><td>11.1</td><td>11.0</td><td>10.9</td><td>10.8</td></tr><tr><td>GBP/EUR</td><td>8.3</td><td>7.8</td><td>7.7</td><td>7.6</td><td>7.6</td><td>7.5</td><td>7.5</td><td>7.3</td></tr><tr><td>EUR/JPY</td><td>12.8</td><td>11.6</td><td>11.11</td><td>0.7</td><td>10.5</td><td>10.3</td><td>11.6</td><td>10.3</td></tr></table></body></html>  

This information is based on data collected by the Federal Reserve Bank of New York from a sample of market participants and is intended only for informational purposes. The data was obtained from sources believed to be reliable but this bank does not guarantee its accuracy, completeness, or correctness. For background information on the release, see: Page VBGROUND.FRB http://www.ny.frb.org/markets/implied.txt  

Table 5.2December: S&P 500   


<html><body><table><tr><td></td><td colspan="2">Impliedvolatility</td><td colspan="2">Implieddelta</td><td></td></tr><tr><td>Strike</td><td>Call</td><td>Put</td><td>Call</td><td>Put</td><td>Vega (ticks)</td></tr><tr><td>975</td><td>20.81</td><td>20.49</td><td>0.79</td><td>-0.2</td><td>1.24</td></tr><tr><td>980</td><td>20.48</td><td>20.21</td><td>0.78</td><td>-0.21</td><td>1.29</td></tr><tr><td>985</td><td>20.18</td><td>19.95</td><td>0.76</td><td>-0.23</td><td>1.34</td></tr><tr><td>990</td><td>19.91</td><td>19.72</td><td>0.75</td><td>-0.25</td><td>1.39</td></tr><tr><td>995</td><td>19.59</td><td>19.43</td><td>0.73</td><td>-0.26</td><td>1.44</td></tr><tr><td>1,000</td><td>19.36</td><td>19.16</td><td>0.71</td><td>-0.28</td><td>1.49</td></tr><tr><td>1,005</td><td>19.07</td><td>18.91</td><td>0.69</td><td>-0.3</td><td>1.53</td></tr><tr><td>1,010</td><td>18.79</td><td>18.66</td><td>0.67</td><td>-0.32</td><td>1.57</td></tr><tr><td>1,015</td><td>18.52</td><td>18.42</td><td>0.65</td><td>-0.34</td><td>1.61</td></tr><tr><td>1,020</td><td>18.19</td><td>18.12</td><td>0.63</td><td>-0.36</td><td>1.65</td></tr><tr><td>1,025</td><td>17.92</td><td>17.87</td><td>0.61</td><td>-0.38</td><td>1.68</td></tr><tr><td>1,030</td><td>17.76</td><td>17.68</td><td>0.58</td><td>-0.41</td><td>1.71</td></tr><tr><td>1,035</td><td>17.53</td><td>17.48</td><td>0.56</td><td>-0.43</td><td>1.73</td></tr><tr><td>1,040</td><td>17.29</td><td>17.27</td><td>0.53</td><td>-0.46</td><td>1.74</td></tr><tr><td>1,045*</td><td>17.04</td><td>17.04</td><td>0.51</td><td>-0.48</td><td>1.75</td></tr><tr><td>1,050</td><td>16.88</td><td>16.91</td><td>0.48</td><td>-0.51</td><td>1.75</td></tr><tr><td>1,055</td><td>16.65</td><td>一</td><td>0.45</td><td>*-0.54</td><td>1.74</td></tr><tr><td>1,060</td><td>16.46</td><td>16.54</td><td>0.43</td><td>-0.56</td><td>1.73</td></tr><tr><td>1,065</td><td>16.3</td><td>一</td><td>0.4</td><td>*-0.59</td><td>1.7</td></tr><tr><td>1,070</td><td>16.12</td><td>16.19</td><td>0.37</td><td>-0.62</td><td>1.67</td></tr><tr><td>1,075</td><td>15.91</td><td>16.02</td><td>0.34</td><td>-0.65</td><td>1.62</td></tr><tr><td>1,080</td><td>15.81</td><td>一</td><td>0.32</td><td>*-0.67</td><td>1.57</td></tr><tr><td>1,085</td><td>15.75</td><td>一</td><td>0.29</td><td>*-0.70</td><td>1.52</td></tr><tr><td>1,090</td><td>15.62</td><td>一</td><td>0.27</td><td>*-0.72</td><td>1.45</td></tr><tr><td>1,095</td><td>15.53</td><td>一</td><td>0.24</td><td>*-0.75</td><td>1.39</td></tr><tr><td>11,00</td><td>15.43</td><td>15.64</td><td>0.22</td><td>-0.77</td><td>1.32</td></tr><tr><td colspan="7">Dec Fut = 1,044.50 days = 47 atmVol = 17.06% IntRate = 6.50%</td></tr></table></body></html>

The asterisk (\*) indicates the closest strike to the forward (or the middle of the distribution) or at the money. Source: http://www.pmpublishing.com/volatility/sp.html#StandardDeviations  

actual volatility and "mean reversion.' Short-term at-the-money options will require constant. rebalancing as the hedge ratio computed between now and expiry will fluctuate. For longerterm options, the hedge ratio day-to-day is going to change much less, therefore while the actual volatility of the FX rate per day may be the same over a short period as over the long period, the dealer's "realized' volatility will be lower. The dealer will perform the buy-high/sell-low. unprofitable trades less frequently. Therefore his cost of manufacture or the premium will be lower. This will result in a lower computed implied volatility. "Mean reversion' refers to the. possibility that while the FX rates fluctuate unpredictably in the short run, they tend to oscillate around long-term trend lines, and the further they deviate from the trend lines the more they. are pulled toward them. As option models cannot take all of these possibilities into account, they can be adjusted for them by lowering the long-term implied volatility to reflect the lower cost of manufacture.  

Consider another example of the computation of implied volatilities, as of October 15, 2003, this time for options all on the same underlying asset and all with the same expiry date.. Table 5.2 shows the implied volatilities on options on the S&P 500 index futures expiring.  

![](1ad0cd23267f972c36e70240dd57fcf53ef48e408b5956ad99fe40ebc3cae288.jpg)  
Figure 5.28 S&P 500 implied volatility skew, December 18, 2003 Puts with strikes below 1,045; Calls with strikes above 1,045 Source: http://www.pmpublishing.com/volatility/sp.html#StandardDeviations  

December 18, 2003. The table also shows the delta for each option sold, in units of futures contracts to be bought/shorted per one option, as well as its vega, in ticks (index points) per $1\%$ volatility change.  

The at-the-money level is 1,044.50. Calls/puts with strikes higher/lower than that level are. out-of-the-money, and with strikes lower/higher than that level are in-the-money. The table. shows the implied volatilities for different strike levels. As a general rule they decrease as the strike level increases in a half-smile fashion as shown on the graph in Figure 5.28 (for very. high strikes they start increasing again slightly).  

This relationship of implied volatilities to strikes is generally referred to as a volatility smile or volatility skew. It probably reflects the fact that as prices drop, they tend to drop and fluctuate by more than assumed by the standard log-normal model, and as prices increase, they tend to increase more gradually without big jumps. There are models of the volatility skew itself that allow dealers to minimize the tertiary risk to relative volatility changes across strikes. This involves relating the different volatilities through a postulated mathematical function which is assumed not to change over time.  

The significance of the volatility skew to the hedger lies in the basis risk of hedging options with one strike with options with a different strike. Even adjusting the input volatilities to compute the correct vega of the hedging instruments does not completely eliminate the risk that the skew itself may change over time. Similarly, hedging with options expiring on a different date may result in a tertiary calendar basis risk.  
