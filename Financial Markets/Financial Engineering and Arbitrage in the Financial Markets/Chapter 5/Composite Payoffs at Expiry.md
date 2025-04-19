---
tags:
  - call_spread
  - option_payoffs
  - option_spreads
  - put_spread
  - straddle_strangle
aliases:
  - Composite Option Payoffs
  - Option Strategies
key_concepts:
  - Call and put spreads
  - Long and short positions
  - Long call spread
  - Straddles and strangles
  - Upfront cost and premium
---

# 5.2 COMPOSITE PAYOFFS AT EXPIRY  

Long and short positions in calls and puts can be combined to achieve narrowly tailored bets on. the range of the asset prices in the future. It is important to realize that speculators can both buy and sell (write) options. They can combine long and short positions. Here are some examples.  

# 5.2.1 Straddles and Strangles  

Suppose we believe that, between now and the expiry date, the price of ABC, currently 60, is going to jump dramatically but we do not know which way. Suppose we buy a put struck at 55 and a call struck at 65. This is called a 55-65 strangle.  

If, on the expiry date, the price is very low or very high, we get a payoff; but if the price stays between 55 and 65 we get nothing. If the price is 30 at expiry, we collect 25 on the 55 put and nothing on the 65 call. If the price is 80, we collect nothing on the 55 put and 15 on the 65 call. If the price is 62, we get nothing on both options.  

Because we bought both options, we incurred an upfront cost of the bet. Our profit is therefore reduced by the total price of the options. An option price is called a premium (as with insurance).  

Next, suppose that we believe that on the expiry date the price of ABC is going to stay around 62. To give ourselves some room for error, we sell a 60-65 strangle (60 put and 65 call) and receive premiums for both options. If we are right and the price does not go below 60 or above 65, we keep the total premium and make no payoff. If we are wrong we have to make a payout on one of the options.  

The payoffs on the long 55-65 strangle and short 60-65 strangle are shown in Figure 5.2.  

![](73ddbfa0ce621568cf1e3d553f7b0b55f22798189b837eb185bec00e353052d5.jpg)  
Figure 5.2 Strangle payoffs at expiry  

A strangle where the call strike and the put strike are the same is called a straddle. Short. straddles and strangles are bets that the price will not fluctuate much from some level. Long. strangles and straddles are bets that the price will move away from the anticipated level.  

While we are not betting on the direction of the stock price, but on whether the stock stays. in or breaks out of a narrow range, straddles and strangles, as described here, are speculative bets. It is not the direction of the position, long or short, that distinguishes the speculator from the dealer, it is the actions after the bet is arranged and paid for. The speculator statically waits for the payout; the dealer manufactures his through dynamic trading.  

# 5.2.2 Spreads and Combinations  

Another set of popular speculative strategies includes call and put spreads. These combine long and short positions in options of the same type..  

A long call spread consists of a long low strike call and a short high strike call. Suppose we believe that ABC's price will rise by expiry, but will not exceed 80. We can buy a 65 call and. sell an 80 call. Any outcome between 65 and 80 will yield an increasing payoff, but we forgo. any increase in payoff above 80. If the stock ends up at 76, we will collect 11 from the 65 call and we will pay nothing on the 80 call. If the stock ends up at 88, we will collect 23 from the. 65 call, but we will pay 8 on the 80 call, leaving us with 15. The maximum payoff from the. strategy is reached at 80. Below 65, both options are worthless..  

A long put spread consists of a long high strike put and a short low strike put. Suppose we believe that ABC's price will drop by expiry, but not below 35. We can buy a 55 put and sell a 35 put. Any outcome between 35 and 55 will yield an increasing payoff, but we forgo any increase in payoff below 35. If the stock ends up at 46, we will collect 9 from the 55 put and pay nothing on the 35 put. If the stock ends up at 28, we will collect 27 from the 55 put, but will pay 7 on the 35 put, leaving us with 20, the maximum payoff from the strategy is reached at 35. Above 55 both options are worthless.  

The payoffs on the long 65-80 call spread and long 55-35 put spread are shown in Figure 5.3.  

We can package puts and calls into other combinations. If we sell a low strike put and buy a. high strike call, we will have no payout over a wide intermediate range of prices (but perhaps a net premium received); we will benefit on the upside, and pay out on the downside. This is called a reverse collar.  

![](53e444281d61ad8942960e2fe2094368075d8618734687e45fddafeb18576e68.jpg)  
Figure 5.3 Spread payoffs at expiry  

Options can also be combined to form calendar spreads. In this case, we buy an option with one expiry date and sell an option with the same (or different) strike, but with a different expiry date. For example, if we believe that ABC's price might first go up but then come down, we can buy a call with short maturity and sell one with a longer maturity. Or if we believe that neither option will ever pay, we may want to sell the more expensive (longer) one and buy the cheaper (shorter) one to pocket the difference.  

Options can also be combined with long and short positions on the underlying asset and in leveraged proportions.  

A buy-write is a strategy where we buy the stock and sell a high strike call. As the stock. rises, we are exposed to the possibility that it will rise above the strike of the call. At that level, we will forgo any further appreciation in the stock as we will be forced to pay out on the call. If we believe that the stock will appreciate over time but not rapidly, we can opt to sell a string of calls with increasing strikes and maturities. We collect lots of premiums and hope that the. options never pay off. This strategy is popular with asset managers (e.g. insurance companies) who naturally hold long portfolios of stocks and want to gain extra income for some extra risk. The strategy is called covered call writing..  

In a leveraged buy-write, we buy the stock and sell two calls with the same strike and the same maturity. If the stock price rises above the bet level we may lose any of the prior appreciation we have gained.  

The payoffs on a long 80-strike buy-write and a 2-to-1 leveraged version of that are shown in Figure 5.4.  

We can also combine a put with a long stock position to obtain protection against the stock falling. The strategy works for holders of concentrated wealth (e.g. private stocks of wealthy families) who cannot or do not want to sell their holdings. If we are afraid that ABC's price may drop below 50, we can buy a 50 put to protect our long stock position. To reduce the cost of the protection we can sell a 40 put.  

Options can help with investment timing decisions. Suppose we researched ABC's stock and consider it to be a solid long-term investment. Based on our analysis, we would like to buy.  

![](7030cc897df1caf7c7fddbe12aff437a8d2539fa3cb871c0d7ef7a2a0e054d9d.jpg)  
Figure 5.4Buy-write payoffs at expiry (stock at 60)  

![](e7eacc546941799a707e66738274e58bbfd7c286572c14b82c8d5953a94ac498.jpg)  
Figure 5.5 Payoffs on put-protected stock at expiry (stock at 60)  

it at 56 or below, but the price has run up to 60. The stock is highly volatile in the short run. Suppose we sell (write) a 60 put for 5. If the stock continues to go up, at least we collected 5; we have to chase it up, but at least we enjoy a defrayment of cost. If the stock goes down to 57, we will be exercised against, having to pay 3. Our net profit is 2 and we can use it to buy the stock, effectively paying 55. If the stock goes down even further to 50, we pay out 10. This leaves us with a loss of 5, but we can buy the stock for 50, effectively paying 55.  

The payoffs on a 50 put-protected stock and a long 40-50 put spread protected stock are shown in Figure 5.5.  

# Binary Options  

Over the counter, one can purchase options with fixed monetary payoffs. Suppose we pay 3 to get 20 if ABC's stock goes to or above 70. Or, we pay 2 to get 20 if ABC's stock goes down to 50 but not below 40. The payoffs on these two options are shown in Figure 5.6. Binary options are more common with interest rates where a version of them is called a range.  

![](b3a544a263484b0db5e6a5f0e093bd9043664445dd9e37239b521c94740b6a79.jpg)  
Figure 5.6 Payoffs on binary options at expiry (stock at 60)  

![](9ffa686dd038a337b3ff4e15b7b00cf1076b14889e841b3768de4baa8839a8c0.jpg)  
Figure 5.7Value on a call and a put prior to expiry. $K={\mathfrak{S}}$ trike Price; $S=S$ top Price now  
