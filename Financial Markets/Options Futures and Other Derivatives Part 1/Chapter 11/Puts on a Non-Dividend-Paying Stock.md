---
tags:
  - '#american_put_option'
  - '#early_exercise'
  - '#european_put_option'
  - '#interest_rate_impact'
  - '#intrinsic_value'
  - '#non_dividend_paying_stock'
  - '#option_bounds'
  - '#put_option_valuation'
  - '#stock_price_volatility'
---
# 11.6 PUTS ON A NON-DIVIDEND-PAYING STOCK  

It can be optimal to exercise an American put option on a non-dividend-paying stock. early. Indeed, at any given time during its life, the put option should always be exercised early if it is sufficiently deep in the money..  

To illustrate, consider an extreme situation. Suppose that the strike price is $\$10$ and the stock price is virtually zero. By exercising immediately, an investor makes an immediate gain of $\$10$ If the investor waits, the gain from exercise might be less than $\$10$ , but it cannot be more than $\$10$ , because negative stock prices are impossible. Furthermore, assuming the interest rate is positive, receiving $\$10$ now is preferable to receiving $\$10$ in the future. It follows that the option should be exercised immediately.  

Like a call option, a put option can be viewed as providing insurance. A put option,. when held in conjunction with the stock, insures the holder against the stock price falling below a certain level. However, a put option is different from a call option in that it may be optimal for an investor to forgo this insurance and exercise early in order to realize the strike price immediately. In general, the early exercise of a put option becomes more attractive as. $S_{0}$ decreases, as $r$ increases, and as the volatility. decreases.  

# Bounds  

From equations (11.3) and (11.5), lower and upper bounds for a European put option when there are no dividends are given by  

$$
\operatorname*{max}(K e^{-r T}-S_{0},0)\leq p\leq K e^{-r T}
$$  

For an American put option on a non-dividend-paying stock, the condition  

$$
P\ge\operatorname*{max}(K-S_{0},0)
$$  

must apply because the option can be exercised at any time. This is a stronger condition than the one for a European put option in equation (11.5). Using the result in equation (11.2), bounds for an American put option on a non-dividend-paying stock are  

$$
\operatorname*{max}(K-S_{0},0)\leq P\leq K
$$  

Figure 11.5 illustrates the bounds.  

Figure 11.6 shows the general way in which the price of an American put option varies with. $S_{0}$ . As we argued earlier, provided that $r>0$ , it is always optimal to exercise an American put immediately when the stock price is sufficiently low. When early exercise is optimal, the value of the option is $K-S_{0}$ The curve representing the value of the put therefore merges into the put's intrinsic value, $K-S_{0}$ for a sufficiently small. value of $S_{0}$ In Figure 11.6, this value of $S_{0}$ is shown as point A. The line relating the put price to the stock price moves in the direction indicated by the arrows when $r$ decreases, when the volatility increases, and when $T$ increases.  

Because there are some circumstances when it is desirable to exercise an American put option early, it follows that an American put option is always worth more than the corresponding European put option. Furthermore, because an American put is sometimes worth its intrinsic value (see Figure 11.6), it follows that a European put option must sometimes be worth less than its intrinsic value. This means that the curve representing the relationship between the put price and the stock price for a European option must be below the corresponding curve for an American option.  

Figure 11.7 shows the variation of the European put price with the stock price. Note that point B in Figure 11.7, at which the price of the option is equal to its intrinsic value, must represent a higher value of the stock price than point A in Figure 11.6. because the curve in Figure 11.7 is below that in Figure 11.6. Point E in Figure 11.7 is where $S_{0}=0$ and the European put price is $K e^{-r T}$  

![](images/860cae9ca13b1fde3606b4bb0193c31bc9b24334da43c92b64883158f66093c4.jpg)  

![](images/b47223ba3958e65a297105e944a71f2f401323f68efc8a9e1c2fafd6a4d20be4.jpg)  
Figure 11.6 Variation of price of an American put option with stock price. Curve moves in the direction of the arrows when the time to maturity or stock price volatility. increases or when the interest rate decreases..  
