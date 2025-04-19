---
tags:
  - '#call_option'
  - '#delta'
  - '#delta_hedging'
  - '#option_hedging'
  - '#option_pricing'
  - '#put_option'
  - '#riskless_portfolio'
  - '#stock_option'
---
# 13.6 DELTA  

At this stage, it is appropriate to introduce delta, an important parameter (sometimes referred to as a "Greek letter" or simply a "Greek") in the pricing and hedging of options.  

The delta $(\Delta)$ of a stock option is the ratio of the change in the price of the stock option to the change in the price of the underlying stock. It is the number of units of the stock we should hold for each option shorted in order to create a riskless portfolio. It is the same as the $\Delta$ introduced earlier in this chapter. The construction of a riskless portfolio is sometimes referred to as delta hedging. The delta of a call option is positive, whereas the delta of a put option is negative.  

From Figure 13.1, we can calculate the value of the delta of the call option being considered as  

$$
\frac{1-0}{22-18}=0.25
$$  

This is because when the stock price changes from $\$18$ to $\$22$ , the option price changes from $\$0$ to $\$1$ . (This is also the value of $\Delta$ calculated in Section 13.1.)  

In Figure 13.4 the delta corresponding to stock price movements over the first time step is  

$$
\frac{1.7433-0}{22-18}=0.4358
$$  

The delta for stock price movements over the second time step is  

$$
\frac{3.2-0}{24.2-19.8}=0.7273
$$  

if there is an upward movement over the first time step, and  

$$
\frac{0-0}{19.8-16.2}=0
$$  

if there is a downward movement over the first time step.  

From Figure 13.7, delta is  

$$
\frac{1.4147-9.4636}{60-40}=-0.4024
$$  

at the end of the first time step, and either  

$$
{\frac{0-4}{72-48}}=-0.1667\quad{\mathrm{or}}\quad{\frac{4-20}{48-32}}=-1.0000
$$  

at the end of the second time step.  

The two-step examples show that delta changes over time. (In Figure 13.4, delta changes from 0.4358 to either 0.7273 or 0; and, in Figure 13.7, it changes from $-0.4024$ to either $-0.1667$ or $-1.0000.$ ) Thus, in order to maintain a riskless hedge using an option and the underlying stock, we need to adjust our holdings in the stock periodically. We will return to this feature of options in Chapter 19.  
