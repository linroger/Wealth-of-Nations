---
tags:
  - '#call_option_value'
  - '#dividends_impact'
  - '#option_pricing_factors'
  - '#put_option_value'
  - '#risk_free_interest_rate'
  - '#stock_option_prices'
  - '#stock_price_volatility'
  - '#time_to_expiration'
---
# 11.1 FACTORS AFFECTING OPTION PRICES  

There are six factors affecting the price of a stock option:  

1. The current stock price, $S_{0}$   
2. The strike price,. $K$   
3. The time to expiration, $T$   
4. The volatility of the stock price, $\sigma$   
5. The risk-free interest rate, $r$   
6. The dividends that are expected to be paid.  

In this section, we consider what happens to option prices when there is a change to one of these factors, with all the other factors remaining fixed. The results are summarized in Table 11.1.  

Figures 11.1 and 11.2 show how European call and put prices depend on the first five factors in the situation where. $S_{0}=50,K=50,r=5\%$ per annum, $\sigma=30\%$ per annum, $T=1$ year, and there are no dividends. In this case the call price is 7.116 and the put price is 4.677.  

Table 11.1 Summary of the effect on the price of a stock option of increasing one variable while keeping all others fixed.   


<html><body><table><tr><td>Variable</td><td>European call</td><td>European put</td><td>American call</td><td>American put</td></tr><tr><td>Current stock price</td><td>十</td><td>一</td><td>+</td><td>一</td></tr><tr><td>Strike price</td><td>一</td><td>+</td><td>一</td><td>+</td></tr><tr><td>Time to expiration</td><td>？</td><td>？</td><td>+</td><td>+</td></tr><tr><td>Volatility</td><td>十</td><td>+</td><td>+</td><td>+</td></tr><tr><td>Risk-freerate</td><td>+</td><td>一</td><td>+</td><td>一</td></tr><tr><td>Amountoffuturedividends</td><td>一</td><td>+</td><td>一</td><td>+</td></tr></table></body></html>  

$^+$ indicates that an increase in the variable causes the option price to increase or stay the same;   
- indicates that an increase in the variable causes the option price to decrease or stay the same;   
? indicates that the relationship is uncertain.  

# Stock Price and Strike Price  

If a call option is exercised at some future time, the payoff will be the amount by which. the stock price exceeds the strike price. Call options therefore become more valuable as the stock price increases and less valuable as the strike price increases. For a put option, the payoff on exercise is the amount by which the strike price exceeds the stock price. Put options therefore behave in the opposite way from call options: they become less. valuable as the stock price increases and more valuable as the strike price increases.. Figure 11.1a-d illustrate the way in which put and call prices depend on the stock price. and strike price.  

# Time to Expiration  

Now consider the effect of the expiration date. Both put and call American options become more valuable (or at least do not decrease in value) as the time to expiration increases. Consider two American options that differ only as far as the expiration date is concerned. The owner of the long-life option has all the exercise opportunities open to the owner of the short-life option-and more. The long-life option must therefore always be worth at least as much as the short-life option.  

Although European put and call options usually become more valuable as the time to expiration increases (see Figure 11.1e, f), this is not always the case. Consider two European call options on a stock: one with an expiration date in 1 month, the other with an expiration date in 2 months. Suppose that a very large dividend is expected in. 6 weeks. The dividend will cause the stock price to decline, so that the short-life option. could be worth more than the long-life option.' As we explain later in the chapter, it can be optimal to exercise a deep-in-the-money American put option early. This means. that there are some situations where a short-maturity European put option is more. valuable than a similar long-maturity European put option..  

# Volatility  

The precise way in which volatility is defined is explained in Chapter 15. Roughly. speaking, the volatility of a stock price is a measure of how uncertain we are about future stock price movements. As volatility increases, the chance that the stock will do very well or very poorly increases. For the owner of a stock, these two outcomes tend to offset each other. However, this is not so for the owner of a call or put. The owner of a  

![](ad9968a1d2e81f99d1455b61c24e8bb6ecafa99704041b033c3ec253bb2ba103.jpg)  
Figure 11.1 Effect of changes in stock price, strike price, and expiration date on option prices when $S_{0}=50,K=50,r=5\%$ $\sigma=30\%$ , and $T=1$  

![](1ff2a1ed6d227507b8a86eea84c1397418898236ea5a20a1103c2f4bc0d68594.jpg)  
Figure 11.2 Effect of changes in volatility and risk-free interest rate on option prices when $S_{0}=50,K=50,r=5\%$ $\sigma=30\%$ , and $T=1$  

call benefits from price increases but has limited downside risk in the event of price.   
decreases because the most the owner can lose is the price of the option. Similarly, the.   
owner of a put benefits from price decreases, but has limited downside risk in the event of price increases. The values of both calls and puts therefore increase as volatility.   
increases (see Figure 11.2a, b).  

# Risk-Free Interest Rate  

The risk-free interest rate affects the price of an option in a less clear-cut way. As. interest rates in the economy increase, the expected return required by investors from. the stock tends to increase. In addition, the present value of any future cash flow received by the holder of the option decreases. The combined impact of these two effects is to increase the value of call options and decrease the value of put options (see Figure 11.2c, d).  

It is important to emphasize that we are assuming that interest rates change while all. other variables stay the same. In particular we are assuming in Table 11.1 that interest rates change while the stock price remains the same. In practice, when interest rates rise.  

(fall), stock prices tend to fall (rise). The combined effect of an interest rate increase and the accompanying stock price decrease can be to decrease the value of a call option and increase the value of a put option. Similarly, the combined effect of an interest rate decrease and the accompanying stock price increase can be to increase the value of a call option and decrease the value of a put option.  

# Amount of Future Dividends  

Dividends have the effect of reducing the stock price on the ex-dividend date. This is bad news for the value of call options and good news for the value of put options. Consider a dividend whose ex-dividend date is during the life of an option. The value of the option is negatively related to the size of the dividend if the option is a call and positively related to the size of the dividend if the option is a put.  
