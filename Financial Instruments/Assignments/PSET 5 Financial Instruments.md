---
linter-yaml-title-alias: WINTER 2024 JOHN HEATON
title: WINTER 2024 JOHN HEATON
tags:
  - binomial_tree
  - european_call_option
  - hedging_risk
  - option_pricing
  - stock_price
aliases:
  - Homework 5
  - John Heaton
  - Multiperiod Binomial Tree
  - Suna Bai
key_concepts:
  - Black Scholes price
  - binomial tree converges
  - hedge call option risk
  - stock price decrease
  - synthetic call option
---

[Option Pricing With Multiperiod Binomial Tree](Option%20Pricing%20With%20Multiperiod%20Binomial%20Tree.md)
[Teaching Note 4-Multiperiod Binomial Trees](Teaching%20Note%204-Multiperiod%20Binomial%20Trees.md)
# WINTER 2024 JOHN HEATON
Homework 5 Due at the beginning of class 6
Suna Bai
Roger Lin
## 1 MULTIPERIOD BINOMIAL TREE
![[IMG-20240913171226906.svg]]
![[IMG-20240913171231770.svg]]
In each of the next two periods ($i = 1$and$i = 2$),  a stock whose value in period$i = 0$is$S_0 = 100$,  can either rise or fall by 10% (using the notation of the teaching notes, $u = 1.1$ and$d = \frac{1}{u}$). Suppose the per-period risk-free rate is${} r = 5\%$. A financial intermediary sold a European call option on the stock,  with exercise price equal to$K = 100$.
1. What actions would the firm need to take in order to hedge its risk from writing the call? (Tip: describe how you would set up a portfolio that the intermediary can use to mirror the payoffs of the option. Note: answering that the firm can buy the same call will not get full credit!) 
	1. To hedge the risk from writing the call,  the firm should create a synthetic call option which replicates the payoff of the actual call option.
	2. At time$t = 0$(Initial):
		1. - Establish a long position in$0.77324$shares of the stock funded by a short bond,  or borrowing position of$67.39 in risk-free bonds.
	3. At time$t = 1$:
		1. If the stock price increases ($S_u$),  the firm should increase its long stock position by purchasing an additional 0.22676 shares for a total of 1 share.
		2. It should increase its short position in bonds by borrowing an additional$28.2904 for a total short bond position of -95.2375
		3. If the stock price decreases ($S_d$),  the firm's position should liquidate its long stock position by selling its entire 0.77324 stock position and lending,  or establishing a long position in$0.77324 \times 90.909= \$70.2945$bonds,  since it is apparent that the counterparty will not exercise the call option,  since even if the stock goes up in period 2 from its$t=1$price of 90.909,  the stock price will at best only match the strike price.
	5. (a) Using a two-period binomial tree,  construct the replicating portfolio at each node. How much would you charge for the call option at period$i = 0$? What is the "delta" (the number of shares bought or sold in the replicating portfolio) and how much borrowing or lending is required at each node?
			1.$S_0 = 100$,
			2.$u = 1.1$,
			3.$d=\frac{1}{1.1}=0.90909$
			4.${}$r = 5\%.
		1. Stock Price can move to:
			1. Up:$S_u = S_0 \times u = 100 \times 1.1$,
			2. Down:$S_d = S_0 \times d = 100 \times \frac{1}{1.1}$
		2. 1. If Stock price at$t=1$is$S_u$
			1. $\Delta_{u}-\Delta_{0}=1-0.77324=0.22676$
				1. Increase position in stock by purchasing 0.22676 additional shares
			2. $B_{u}-B_{0}= |-95.2375-(-66.9471)|= 28.2904$
				1. Borrow 28.2904 to fund increased long position in stock
		2. 1. If Stock price at$t=1$is$S_d$
			1. $\Delta_{d}-\Delta_{0}= 0-0.77324 = -0.77324$
				1. Liquidate stock position by selling 0.77324 shares
			2. $B_{u}-B_{0}= |0-(-66.9471)|= 66.9471$
				1. Increase position in bonds by lending 66.9471
		3. The price of the call option should be equal to the value of a replicating portfolio of a long 0.77324 stocks and short$66.9471 bond position. The call option premium is thus$10.37688
 ![500](IMG-20240913171238611.png)
	1. (b) Let's see what happens if we change the initial stock price$S_{0}$by a little. In particular I would like you to figure out how the value of the replicating portfolio changes when you change$S_{0}$. To do this compute the value of the replicated portfolio, $V^{RP}$when the initial stock price is equal to$S_{0}+ △S$ with$∆S = 1,  2_,  …,  10$When doing this remember that future stock prices are also changed under the assumption that the stock price rises or falls by 10% going forward. 
		1. i. Is the change in value of the portfolio linear in ∆S? (Tip: the change in value is linear in ∆S if$V^{RP}$($k △S) = k · V^{RP} (△S)$). Show your calculations. 
- These are the different values of the replicating portfolio for each given initial stock price. The value of the replicating portfolio does not increase perfectly linearly with the stock price.,  as the increase from 101 to 102 for the stock price had a different increase in$V$than all the other 1 unit increases in stock prices after 102. This suggests that as the stock price increasingly grows away from the strike price,  the increase in the value of the portfolio does not keep pace,  but appears to slow.
|  |  |  |  |
| ---- | ---- | ---- | ---- |
| $S_{0} +\Delta S$ | $V^{RP}$ | $V^{RP}_{t}-V^{RP}_{t-1}$ | $\frac{V^{RP}_{t}-V^{RP}_{t-1}}{V^{RP}_{t-1}}$ |
| 100 | 10.37688 |  |  |
| 101 | 11.32543 | 0.948547 | 0.09141 |
| 102 | 12.27401 | 0.948582 | 0.083757 |
| 103 | 13.22259 | 0.948582 | 0.077284 |
| 104 | 14.17118 | 0.948582 | 0.071739 |
| 105 | 15.11976 | 0.948582 | 0.066937 |
| 106 | 16.06834 | 0.948582 | 0.062738 |
| 107 | 17.01692 | 0.948582 | 0.059034 |
| 108 | 17.9655 | 0.948582 | 0.055743 |
| 109 | 18.91408 | 0.948582 | 0.0528 |
| 110 | 19.86267 | 0.948582 | 0.050152 |
			ii. If your answer in the previous point was "No",  would you describe the relationship between $V^{RP}$ and S as concave or convex? What would be the sign of the second derivative of a function $V^{RP}$ (S)? 
			The effect is convex. As the stock price moves further from the strike,  the value of the portfolio would tend to increase at a growing rate. The sign of the second derivative of $V$ with respect to $S$ is positive.
	1. (c) Use the initial assumption for $S_{0}$ for this and the remaining questions. Is the portfolio "self-financing"? (Tip: The portfolio is self-financing if you do NOT need any additional capital infusion between period $i = 0$ and the period of the final payoff T = 0 )

		3. Value at  $t=1$  of inherited portfolio set up at  $t=0$
			1. $110\times 0.77324-66.9471\left(1.05\right)= 14.7619451$
		4. Value at  $t=1$  of future portfolio at t=2
			1. $110\left(1\right)-95.2375= 14.7625$
			2.
		5. The portfolio is self financing,  as no additional cash injection is needed after the initial period,  since the value of the portfolio created at  $t=0$  is enough to cover any addiitonal investments or obligations incurred through borrowing.
	2. (d) What is the profit/loss on the replicating portfolio? 
		1. The payoff of the replicating portfolio is the same as the payoff for the call option
		2.

|  | Stock Price in 1 Year |  |  |
| ---- | ---- | ---- | ---- |
|  | 121 | 100 | 82.6446 |
| Number of Shares | 1 | 1 | 0 |
| Value of Shares | 121 | 100 | 0 |
| Bond Position | -95.2375 | -95.2375 | 0 |
| Loan Repayment | -99.9994 | -99.9994 | 0 |
| Payoff | 21.00063 | 0.000625 | 0 |
1. (e) What is the price of the call option if the stock pays a 5% dividend yield in period$i = 1$? Show the resulting trees for the stock price and for the option as well as your computations. (Hint: when the dividend is paid the stock price must decline in response. In the "up" state in period 1 before the dividend is paid,  the stock prices is$S_{0} × u$. If y is the dividend yield,  the stock price next period in the "up" state _after the payment of the dividend_ is $S_{0} × u × (1 − y)$. A similar adjustment must be made to the stock price in the "down" state after the dividend is paid.)
		1. 1. The price of the call option is$\$10.28458$
 ![500](IMG-20240913171242399.png)
1. (f) What is the price of the call option if the stock pays a$5 dividend in period $i = 1$? In this case the dividend is a fixed dollar amount that is independent of the stock price. Show the resulting trees for the stock price and for the option as well as your computations. Comment on the difference with part (e).
	1. The price of the call option is$\$10.45657$. The option price for the stock paying a fixed dividend is higher than the option price for the stock paying a dividend yield. This may be because the payoffs to the call option are higher under the up-up case,  and the same for the other two scenarios.
 ![500](IMG-20240913171245806.png)
## 3 BIG BINOMIAL TREE
Use the file BinomialTree.xls available on chalk to confirm that as you increase the number of steps,  the option price and delta from the Tree converges to the Black and Scholes ones. Report the prices and deltas in a table for $n = 2,  5,  10,  25,  50,  125,  250$ tree steps.
- As the binomial tree increases in steps,  it converges to the Black Scholes price for an option.
|   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|
||2|5|10|25|50|125|250|
|Price Binomial|3.450|4.072|3.787|3.918132|3.861387|3.88779|3.876|
|Delta Binomial|0.524|0.527|0.527|0.527247|0.527177|0.5273|0.527|
|Price Black Scholes|3.880|3.880|3.880|3.88024|3.88024|3.88024|3.880|
|Delta Black Scholes|0.527|0.527|0.527|0.527313|0.527313|0.527313|0.527|
## 2 BLACK AND SCHOLES (AND MERTON) FORMULA
Today is January 4,  2022. The stock price of Verotende Inc. (a well known publicly traded investment bank in early 2022) is trading at at USD 42. In addition the annualized stock return volatitiy is 20% and the annualized continuously compounded yield on 6 months T-bills is 10%.
1. Using the Black-Scholes formula,  compute the price of a European call and a European put option,  with identical exercise price$K_c = K_p = 40$dollars,  and six months to maturity. Show your calculations.
$$\begin{aligned}
&d_{1}=\frac{\ln\left(\frac{S_{0}}{k}\right)+\left(r-q+\frac{\sigma^{2}}{2}\right)T}{\sigma\sqrt{T}}=0.7693  \\
&d_2=d_1-\sigma\sqrt{T}=0.6278 \\
&\text{With K=40} \\
&\mathbf{r=0.10} \\
&\sigma=0.20 \\
&T=0.5 \\
&P=K\times e^{-r T}\times N(-d_{2, 0})-S_{0}\times N(-d_{1, 0})=0.81 \\
&C=S_{0}e^{-r T}N(-d_{1, 0})-K\times e^{-r T}\times N(-d_{2, 0})=4.76
\end{aligned}$$
2. Compute the price of the call and put options using several initial stock prices values,  from 10% in the money to 10% out of the money. Plot the price of the the two options as a function of the stock price in a chart. Would you describe the relationship between the two option prices and S as concave or convex?
	1. 10% in the money: S = (1+10%)*42 = 46.2
	2. 10% out of the money: : S = (1-10%)**42 = 37.8
	3.  ![500](IMG-20240913171249774.png)
4. Consider changing the inputs: compute the price of the call and of the put using different values for the parameters listed in the first column of Table (1). Report your findings on the relationship between options prices and inputs,  by filling the white spaces in Table (1) (simply write: "increase",  "decrease" or "uncertain" in each white space). Provide some intuition for your findings
 ![500](IMG-20240913171255268.png)
_Table 1: Sensitivity of Black and Scholes option prices to inputs_
Interpretation:
For stock price: when the stock prices increase,  the value of a call option increases because the call option will probably end in the money. On the other hand,  the value of the put option’s value will decrease as the option end up in the money.
For strike price: when the strike price increases,  the value of a call option decreases because the option becomes less likely to end up in the money,  which makes the put price increase.
For volatility: higher volatility will lead to the stock price increasement,  and it will be above the strike price. Thus,  the call price increases. The same logic happens to put price too.
For maturity: stock could rise above the strike price as the maturity becomes longer,  which increases the call prices. Similar idea,  longer maturity makes the stock fall more below the strike price,  the put price also increases.
For risk-free rate: risk-free rate increases,  PV decreases,  makes the call price increase and put price decrease.
4. If you sell an at-the-money put option on Verotende Inc. To a counterparty,  and you want to hedge the short put using a position in stocks and bonds,  what is going to be your position in stocks and bonds?
4) Stock
 $\Delta_{put}=N(d_1)-1\approx-0.5$,  which means for every put option we sell,  we need to buy 0.5 share of stock to hedge.
 Bond
$PV(K)=K\times e^{-rT}$ net borrowing or lending amount $=PV(K)-C_{put}$
Given the risk-free = 10%,  T = 0.5,  PV(K) = $38.05.. The bond position would be a long position in risk-free bonds with PV of 38.05.
## 3 BIG BINOMIAL TREE
Use the file BinomialTree.xls available on chalk to confirm that as you increase the number of steps,  the option price and delta from the Tree converges to the Black and Scholes ones. Report the prices and deltas in a table for $n = 2,  5,  10,  25,  50,  125,  250$ tree steps.
|   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|
||2|5|10|25|50|125|250|
|Price Binomial|3.450|4.072|3.787|3.918132|3.861387|3.88779|3.876|
|Delta Binomial|0.524|0.527|0.527|0.527247|0.527177|0.5273|0.527|
|Price Black Scholes|3.880|3.880|3.880|3.88024|3.88024|3.88024|3.880|
|Delta Black Scholes|0.527|0.527|0.527|0.527313|0.527313|0.527313|0.527|