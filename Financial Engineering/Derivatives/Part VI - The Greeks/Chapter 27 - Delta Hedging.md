---
tags:
  - delta_hedging
  - dynamic_hedging
  - european_call
  - greeks
  - options_portfolio
  - stock_price
aliases:
  - Call Option Delta
  - Delta Hedging
  - Delta Neutral
key_concepts:
  - Call option premium
  - Delta hedging
  - Dynamic delta hedging
  - Hedge ratio
  - Rebalancing stock-call portfolio
---
# THE GREEKS  

# Delta Hedging  

# Aims  

• To demonstrate simple delta hedging of calls and puts and the need for rebalancing.   
• To show how dynamic delta hedging is used to protect the value of an options portfolio from (small) changes in the price of the underlying asset.   
• To show that after dynamic delta hedging, you can close out your positions at any time and you will have neither gained nor lost money.  

# 27.1 DELTA  

A portfolio can be constructed so that any gain or loss from a small change in the option price (over a short interval of time) is ofset by changes in the price of the underlying asset – this is delta hedging. Delta hedging applies to all kinds of options, where the underlying $s$ can be a stock price, stock index, commodity price, exchange rate, futures price, or an interest rate. The delta of a long call (which is written on one stock) is defned as:  

$$
\Delta_{c}={\frac{A p p r o x i m a t e c h a n g e i n o p t i o n^{\prime}s p r i c e}}{S m a l l c h a n g e i n s t o c k p r i c e}}={\frac{\partial C}{\partial S}}
$$  

Hence:  

Approximate change in call premium $d C=\Delta_{c}\times$ Small change in stock price  

Derivatives:TheoryandPractice, First Edition. Keith Cuthbertson, Dirk Nitzsche and Niall O’Sullivan. $\circledcirc$ 2020 John Wiley & Sons Ltd. Published 2020 by John Wiley & Sons, Ltd.  

![](2e5ee0919106d4f9b39148c0d1097074665b5663495e27cd6272e54c5c77050a.jpg)  
FIGURE 27.1 Delta of a long call  

The delta of a long call $\Delta_{c}\equiv\partial C/\partial S$ is positive because a rise in the stock price leads to a rise in the call premium (Figure 27.1). Consider delta hedging a position in European call options. The value $V$ of a portfolio consisting of $N_{s}$ stocks and $N_{c}$ calls is:  

$$
V=N_{s}S+N_{c}C=N_{c}(h S+C)
$$  

where $h\equiv N_{s}/N_{c}$ and is known as the hedge ratio. The convention is that $N_{s}$ or $N_{c}>0$ if the stock or option is held long (i.e. ‘buy’) and $N_{s}$ or $N_{c}<0$ if either is held short (i.e. the stock is short-sold or the option is sold). To hedge we set $\partial V/\partial S=0$ :  

$$
\begin{array}{l}{\displaystyle\frac{\partial V}{\partial S}=h+\frac{\partial C}{\partial S}=0}\\ {\displaystyle h\equiv N_{s}/N_{c}=-\partial C/\partial S\equiv-\Delta_{c}}\\ {\displaystyle N_{s}=-N_{c}\Delta_{c}}\end{array}
$$  

The ‘minus sign’ indicates that if you are long one call option $\left(N_{c}=+1\right)$ , then to hedge you must short-sell $\Delta_{c}$ stocks $(N_{s}=-N_{c}\Delta_{c}=-\Delta_{c})$ . If you have sold (written) one call option $(N_{c}=-1)$ , then to delta hedge you must go long (buy) $\Delta_{c}$ stocks $(N_{s}=-N_{c}\Delta_{c}=\Delta_{c})$ .  

# 27.1.1 Delta of a Call  

To maintain a delta-neutral position requires continuous rebalancing of the stock-call portfolio since $\Delta_{c}$ changes as the stock price changes. At a stock price of $\$100$ , the call has a delta of $\Delta_{c}=0.4$ (see Figure 27.1, point A). Given the curvature of the relationship between $c$ and $s$ , if the stock price on day-2 is $\$110$ then the value of $\Delta_{c}=0.5$ (Figure 27.1, point B). Assume for each call the underlying asset is for delivery of 1 stock.  

If, for example, the initial position on day-1 consists of 100 written calls then to delta hedge over one day requires buying (go long) 40 stocks $(=100\times0.4)$ at a cost of $\$4,000$ $(40\times\$100)$ . On day-2, $\Delta_{c}=0.5$ so the 100 written calls can be hedged over the next day by holding 50 stocks 1 $(100\times0.5)$ – that is on day-2 you need to purchase an extra 10 stocks at an additional cost of $\$1,100$ $(=10\times\$110)$ to maintain a delta hedge position (between day-2 and day-3). This is dynamic delta hedging.  

When hedging our 100 written calls, if the stock price falls from $\$110$ on day-2 to $\$100$ say on day-3 then $\Delta_{c}$ falls, from 0.5 to 0.4. Hence, on day-3 to delta hedge over the next day we need to hold 40 stocks and at the beginning of day-3 we sell 10 $(=50-40)$ stocks $(@\$100)$ to maintain our delta-hedged position (and we receive $\$1,000$ ).  

Delta hedging, therefore involves selling stocks just after a price fall and buying stocks just after a price rise. It could be termed (somewhat paradoxically) a ‘buy high, sell low’ strategy, and this rebalancing is part of the cost of dynamic hedging.  

Delta hedging only provides a hedge against small changes in the stock price. To hedge an options position against large changes in the stock price or changes in the volatility of stock returns or changes in the risk free rate, requires additional hedging strategies, which comes under the heading of ‘the Greeks’ (see Chapter 28).  

When the current stock price is very low (i.e. well below the strike price $\boldsymbol{K}$ ), the call is well out-of-the-money (OTM) and $\Delta_{c}=0$ (see Figure 27.1, point C). Hence to delta hedge (over the next day) requires no stocks to be held, since over a short interval of time, the change in value of ‘zero holdings’ of stocks is zero and the change in the call premium is also (approximately) zero $(d C=\Delta_{c}\times d S)$ . When the stock price is very high (i.e. well above the strike price $\boldsymbol{K}$ ), the call is well in-the-money, ITM and $\Delta_{c}=+1$ (see Figure 27.1, point D). Hence to delta hedge 100 written calls you must hold 100 stocks. If the stock price changes by $\$1$ (over the next day) the value of your stocks changes by $\$100$ , but the value of the written calls also changes by $\$100$ , and you are hedged.  

# 27.1.2 Delta of a Put  

The delta of a long put $\Delta_{p}\equiv\partial P/\partial S$ is negative because a rise in the stock price leads to a fall in the put premium (Figure 27.2). Using the Black–Scholes formula it can be shown that $\Delta_{p}=N(d_{1})-1$ . Alternatively the put-delta can be obtained from the call delta (for a call with the same underlying asset, time to maturity, and strike price) by diferentiating the put–call parity relationship:  

$$
P+S=C+K e^{-r T}\Rightarrow\Delta_{p}=\Delta_{c}-1
$$  

When $s$ is very low (much lower than $K_{\cdot}$ ), the put is ‘well ITM’ and a dollar fall in the stock price gives a dollar rise in the put premium, hence $\Delta_{p}=-1$ (Figure 27.2, point D). When $s$ is  

![](7ab38d12e95c5a99d99cf65978bd57c5aff6504aa5b4e9727cd380b453afc616.jpg)  
FIGURE 27.2 Delta of a long put  

very high (much higher than $K_{\iota}$ , the put is ‘well OTM’ and a dollar fall in the stock price has virtually zero efect on the put premium and hence $\Delta_{p}=0$ (Figure 27.2, point C).  

# 27.1.3 Summary  

From the Black–Scholes formula for European calls and puts (on stocks that pay no dividends) it can be shown that:  

$$
\begin{array}{r c l l}{{\Delta_{c}}}&{{=}}&{{\partial C/\partial S=N(d_{1})}}&{{\quad\mathrm{~and~}0\leq\Delta_{c}\leq1}}\\ {{\Delta_{p}}}&{{=}}&{{\partial P/\partial S=N(d_{1})-1}}&{{\quad\mathrm{~and~}0-1\leq\Delta_{p}\leq0}}\end{array}
$$  

Since $d_{1}$ depends on $s$ then delta changes as $s$ changes. The hedge ratio for a position in calls is $h\equiv N_{s}/N_{c}=-\Delta_{c}$ . Hence, a delta neutral position for European calls involves a ‘long-short’ position:  

# Delta-neutral positions with calls (hedge portfolio $\mathbf{\tau}=$ ‘long-short position’)  

Portfolio-A: Short 1 call and long $\Delta_{c}$ stocks Portfolio-B: Long 1 call and short-sell $\Delta_{c}$ stocks  

Delta hedging with puts gives:  

$$
\begin{array}{l}{{V=N_{s}S+N_{p}P=N_{p}(h_{p}S+P)}}\\ {{h_{p}=N_{s}/N_{p}=-\Delta_{p}=|\Delta_{p}|}}\end{array}
$$  

For a long put $\Delta_{p}$ is negative, hence if you are long puts $(N_{p}>0)$ then to hedge you go long stocks $(N_{s}>0)$ . Similarly, if you are short (i.e. you have sold/written) a put $(N_{p}<0)$ , a delta-neutral hedge involves short-selling stocks $N_{s}<0$ .  

# Delta-neutral positions with puts  

Portfolio-A: Long 1 put option and long $|\Delta_{p}|$ stocks Portfolio-B: Short 1 put option and short-sell $|\Delta_{p}|$ stocks  

In practice there are some risks and costs attached to dynamic delta hedging since:  

• when rebalancing you incur transaction costs (bid–ask spreads, commissions, price impact).   
• delta hedging is only efective for small changes in stock prices.   
• the volatility of the stock or the risk-free rate may change and hence the actual change in the option’s value will not equal that given by the option’s delta.   
• diferent European options have diferent deltas – so you must choose the correct ‘delta’.1  

# 27.2 DYNAMIC DELTA HEDGING  

The Black–Scholes formula (on a non-dividend paying stock) shows that the option premium varies with $S,r,\sigma,T$ , all of which may change minute-by-minute, over the life of the option. The purpose of this section is to show how delta hedging an options position implies that you neither gain nor lose money, regardless of what point in time you choose to close out your hedged position (either before maturity or on the maturity date itself) and regardless of what has happened to the stock price over time. The only requirement is that you rebalance your hedged portfolio frequently (or, in the limit ‘continuously’).  

The current stock price $S_{0}=100$ . Suppose you are a derivatives dealer for Morgan Stanley (Ms Short) and you have just sold (i.e. written) one at-the-money (ATM) call option $\mathrm{\mathit{S}}_{0}=K=100\mathrm{\mathit{)}}$ to a hedge fund client (‘GoldFinger’).2 The call premium is $C_{0}=10.45$ and $\Delta_{0}=0.6368$ with $K=100$ , $\sigma=20\%$ $r=5\%$ , $T=1$ year . Assume each call option delivers one stock at maturity. At $t=0$ to delta hedge the call, Ms Short borrows money to buy $\Delta_{0}$ stocks (Figure 27.3)3:  

![](cc2bff4ee395a2b87eb4bd0e803fffdeca7de474a657519c889cd21026d97d85.jpg)  
FIGURE 27.3 Delta hedging: rebalancing  

Buy $\Delta_{0}=0.6368$ stocks $@S_{0}=100$ using borrowed funds (e.g. bank loan) of $\$63.68$  

Initial debt: $D_{0}=\Delta_{0}S_{0}=\S63.68$  

When the stock price changes from day-to-day over the life of the option, Ms Short has to continually rebalance her hedge portfolio by buying and selling stocks to preserve delta neutrality. However, as we shall see, the average (percentage) cost of the hedge is equal to the risk-free rate (if we ignore transactions costs of buying and selling stocks). We can view the outcome of the delta hedge at two diferent times – at maturity and before maturity:  

1. If Ms Short continues to delta hedge to the maturity date of the option contract then when the option matures she should have neither lost nor gained. More precisely, since Ms Short’s hedge is risk free, the cost of the hedge should equal the risk-free rate.   
2. Any change in the value of Ms Short’s hedge portfolio over a small interval of time should be approximately zero. Also, if Ms Short closes out all her hedge positions at any time before maturity then she should have neither lost nor gained. After closing out, the value of her hedge portfolio should be close to zero.  

Consider two possible cases. First, where the stock price rises and the call eventually ends up well in-the-money $(S_{T}\gg K)$ and second, where the stock price falls and the call ends up well out-of-the-money $(S_{T}\ll K)$ .  

# 27.2.1 Option Ends in-the-Money (ITM)  

# 27.2.1.1 Ms Short’s Position at Maturity  

Our simulations show that the outcome of the hedge at maturity of the option (after 1 year) is a net debt of $N D_{T}=\mathfrak{F}11.29$ for Ms Short (Morgan Stanley) who initially sold the option at $C_{0}=\$10.45$ (Figure 27.3).  

We can interpret this result as follows:  

• The receipt of $\$10.45$ from the sale of the option could be placed in a (risk-free) bank deposit at $5\%$ interest and would be worth $\$10.98\left[=10.45\exp(\mathrm{{rT})\right]}$ after one year. Hence, in 1 year’s time the net debt of Ms Short is small $\mathfrak{H}0.31\left(=\mathfrak{H}11.29-\mathfrak{H}10.98\right)$ . This is about $3\%(=\mathfrak{H}0.31/\mathfrak{H}10.45)$ of the initial receipt of the call premium of $\$10.45$ and approximately equal to the risk-free rate of $5\%$ .  

# 27.2.1.2 Ms Short’s Net Position at t  

Suppose instead, Ms Short closes out her hedged position after $t=0.2$ years (chosen arbitrarily). At this point, our simulations show that the stock price, call premium, number of stocks held and the debt level have all increased to (see Table 27.1):  

$$
N_{s}=\Delta_{c}=0.8052\mathrm{\stoc{k}{s}},\qquadS=110.2871,\qquadD=83.14
$$  

Hence, when Ms Short closes out all her positions in the hedge at $t=0.2$ years, we fnd:  

• Value of stocks $\mathrm{sold}=88.8032(=0.8052\times\S110.2871)$ • Less debt at $t=0.2=-83.1478$ (buying on rising market and interest paid) • Ms Short’s loss on the cal $=-6.0817$ $\stackrel{\prime}{=}10.45-16.5317$ , closes out the option) • Net position at $t=0.2=-0.4265$ (small loss on the hedge)  

Hence, Ms Short again neither gains nor loses (much) and the value of her hedge position is close to zero.  

# 27.2.1.3 Ms Short’s Dynamic Delta Hedge  

Let us now see how the above results come about by examining Ms Short’s dynamic delta hedging strategy in more detail. If $s$ increases then $\Delta_{c}$ increases and Ms Short has to borrow more money to purchase more stocks to maintain the delta hedge – this is the ‘hidden’ cost of  

hedging, since Ms Short buys stocks on a rising market. The additional borrowing increases the level of debt, as does the interest cost on the existing debt.  

Suppose at $t=1$ the stock price rises to $S_{1}=\$100.1$ with $\Delta_{1}=0.6381$ . Then to delta hedge over the next day, Ms Short buys $\Delta_{1}-\Delta_{0}=0.001226$ additional stocks at $\mathbf{S}_{1}$ costing an additional $\$0.1227$ . Ms Short’s new debt position is:  

debt Initial debt interest cost $+$ cost of buying stocks  

$$
\$63.84=863.68~e^{0.05(0.01)}+\S0.1301
$$  

$$
D_{1}=D_{o}e^{r\Delta t}+(\Delta_{1}-\Delta_{0})S_{1}
$$  

At $t=0.2$ , the stock price has increased, so Ms Short buys extra stocks for the delta hedge, giving a debt level of $\$83.1478$ at $t=0.2,S$ increases over time and just before expiration of the option, $S\gg K$ so the delta of the (long) call has increased to $\Delta_{c}=1$ (see Table 27.1). Hence at maturity $T$ , the dynamic delta hedge results in Ms Short holding 1-stock to deliver against the written call – so there is no uncertainty about having a stock to deliver. At $T_{:}$ , Ms Short delivers the stock to GoldFinger (assuming the hedge fund has held the long call to maturity)  

TABLE 27.1 Delta hedge a written call   


<html><body><table><tr><td>Time, t </td><td>Time left, T-t</td><td>Asset price, S</td><td>d1</td><td>d2</td><td>Delta</td><td>Cash inflow (minus = outflow)</td><td>Interest on debt</td><td>Stock of debt</td><td>Change in value of hedge</td><td>Call option premium</td></tr><tr><td>0</td><td>1</td><td>100</td><td>0.3500</td><td>0.1500</td><td>0.6368</td><td></td><td></td><td>63.6831</td><td>0</td><td>10.4506</td></tr><tr><td>0.01</td><td>0.99</td><td>100.1</td><td>0.3533</td><td>0.1543</td><td></td><td>0.6381 -0.1227</td><td>0.0318</td><td>63.8376</td><td>0.0313</td><td>10.4500</td></tr><tr><td>0.02</td><td>0.98</td><td>104.364</td><td>0.5622</td><td>0.3642</td><td></td><td>0.7130 -7.8232</td><td>0.0319</td><td>71.6928</td><td>5.5070</td><td>13.2683</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.17</td><td>0.83</td><td>108.2762</td><td>0.7553</td><td>0.5731</td><td>0.7750</td><td>-6.0212</td><td>0.0368</td><td>79.6779</td><td>4.8706</td><td>15.1530</td></tr><tr><td>0.18</td><td>0.82</td><td>107.3599</td><td>0.7091</td><td>0.5280</td><td>0.7609</td><td>1.5135</td><td>0.0398</td><td>78.2042</td><td>-1.5239</td><td>14.3790</td></tr><tr><td>0.19</td><td>0.81</td><td>109.3247</td><td>0.8103</td><td>0.6303</td><td>0.7911</td><td>-3.3077</td><td>0.0391</td><td>81.5510</td><td>2.9105</td><td>15.8337</td></tr><tr><td>0.2</td><td>0.8</td><td>110.2871</td><td>0.8604</td><td>0.6815</td><td>0.8052</td><td>-1.5560</td><td>0.0408</td><td>83.1478</td><td>1.4187</td><td>16.5317</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>0.95</td><td>0.05</td><td>154.3975</td><td>9.7909</td><td>9.7461</td><td>1.0000</td><td>0</td><td>0.0555</td><td>111.0204</td><td>-5.5528</td><td>54.6472</td></tr><tr><td>0.96</td><td>0.04</td><td>157.2825</td><td>11.3918</td><td>11.3518</td><td>1.0000</td><td>0</td><td>0.0555</td><td>111.0759</td><td>5.6645</td><td>57.4823</td></tr><tr><td>0.97</td><td>0.03</td><td>154.1949</td><td>12.5616</td><td>12.5270</td><td>1.0000</td><td>0</td><td>0.0556</td><td>111.1314</td><td>-6.2806</td><td>54.3448</td></tr><tr><td>0.98</td><td>0.02</td><td>157.3344</td><td>16.0727</td><td>16.0444</td><td>1.0000</td><td>0</td><td>0.0556</td><td>111.1870</td><td>6.1735</td><td>57.4344</td></tr><tr><td>0.99</td><td>0.01</td><td>160.6512</td><td>23.7383</td><td>23.7183</td><td>1.0000</td><td>0</td><td>0.0556</td><td>111.2426</td><td>6.5280</td><td>60.7012</td></tr><tr><td>1</td><td>0.0001</td><td>163.3499</td><td>245.3658</td><td>245.3638</td><td>1.0000</td><td>0</td><td>0.0556</td><td>111.2983</td><td>5.2923</td><td>63.3504</td></tr></table></body></html>  

and receives $K.$ . Ms Short has outstanding debt of $D_{T}=111.29$ from the funds borrowed to purchase the additional stocks in the delta hedge and from interest on her bank loan. Hence:  

The cost of the hedge as a proportion of Ms Short’s initial receipts from the sale of the call is:  

$$
\%{\mathrm{~Cost~of~hedge}}={\frac{N D_{T}-C_{0}}{C_{0}}}=({\S11.29}-{\S10.45})/{\S10.45}=8\%
$$  

For our simulation (Table 27.1), the cost of the hedge is ‘in the ball-park’ of the risk-free rate of $5\%$ . If the hedge is repeated a large number of times (which in practice will happen to Ms Short as she is an options trader for Morgan Stanley), then on average, the percentage cost of all her hedges will be close to the risk-free rate of $5\%$ , if she rebalances frequently (and for the moment we ignore transactions costs). The hedging error in our single simulation does not produce this ‘average result’ because our simulation contains some large changes in the stock price so the delta hedge is not perfect.  

# 27.2.2 Option Ends Out-of-the-Money  

Let us now consider delta hedging Ms Short’s written call when the stock price falls over time and the option ends up well OTM at maturity, $T.$ . Her initial level of debt is $D_{0}=\$63.68$ . As the stock price falls the delta of the option falls. To maintain the hedge, Ms Short (at Morgan Stanley) therefore sells some of her original $\Delta_{0}=0.6368$ stocks and uses this cash infow to reduce her bank debt. If the stock price falls monotonically then Ms Short will always be selling of some of her stocks but at lower prices – hence she would end up with positive debt at maturity of the call – some of which is also due to interest payments.  

In our simulation where the stock price falls, the fnal debt level at maturity of the option is $D_{T}=\$10.19$ . Since $S_{T}\ll K$ , the call delta has fallen to $\Delta_{T}=0$ and hence at $T$ , Ms Short holds no stocks and the call expires out-of-the-money (and is not exercised by GoldFinger). The percentage net cost of the hedge portfolio turns out to be:  

$$
\%\mathrm{Cost0fhedge}=|D_{T}-C_{0}|/C_{0}=2.49\%
$$  

Now let us examine the change in value of Ms Short’s hedge portfolio over a small interval of time, using some algebra:  

$$
\begin{array}{c}{d V_{t+1}=N_{s t}d S_{t+1}+D_{t}(r d t)-d C_{t+1}}\\ {\approx\Delta_{t}d S_{t+1}+D_{t}(r d t)-(\Delta_{t}d S_{t+1})=D_{t}(r d t)}\end{array}
$$  

where $d S_{t+1}=S_{t+1}-S_{t}$ etc., $N_{t}=\Delta_{t}$ is the number of stocks held at time $t$ , $d C_{t+1}\approx\Delta_{t}d S_{t+1}$ is the (approximate) change in the call premium, $r$ is the annual interest rate, $d t$ is a small interval of time. From Equation (27.6) we see that $d C_{t+1}\approx\Delta_{t}d S_{t+1}$ is a good approximation for the change in the call premium, then $d V_{t+1}=D_{t}(r d t)$ and the cost of the hedge over a small interval of time, equals the risk-free rate.  

Perhaps the most intuitive way of looking at the hedge is to assume that Ms Short who initially sold the call for $C_{0}=\$10.45$ at $t=0$ , places this cash in a risk-free deposit account and she ends up at $T$ , with cash of $C_{0}e^{r T}$ . But she also has an outstanding bank loan of $N D_{T}$ . If she repeats the hedge a large number of times, the diference $N D_{T}-C_{0}e^{r T}$ should be small and on average should be close to zero.4 A measure of the (percentage) e\$ciency of the hedge (over a large number of delta hedges) is:  

Hedge error:  

$$
\%H E=\frac{s t d\nu[N D_{T}-C_{0}e^{r T}]}{C_{0}}
$$  

The more frequently Ms Short rebalances the hedge, the closer to zero we expect the hedging error to be. If we hold the volatility $\sigma$ of the underlying stock constant and generate repeated ‘runs’ of the delta-hedge scenario we can obtain measures of $\%H E$ for diferent rebalancing periods. As we rebalance over $\{25,5,1,1/2\}$ days the $\%H E$ improves (ignoring transactions costs) from an average of about $0.5\%$ to $0.25\%$ to $0.15\%$ to $0.1\%$ , respectively (Kurpiel and Roncalli 2009). However, in practice there is a trade-of here because the hedging error may be larger when we rebalance more frequently because of higher trading costs.  

The option’s delta only provides a frst order approximation to the change in the price of the call, which in practice could change due to changes in other factors (e.g. interest rates or volatility). In practice, the change in value of the delta-hedged portfolio will not exactly match the actual change in value of the written call. Also, when the volatility of the underlying asset $\sigma$ , is allowed to vary (i.e. in a stochastic volatility world) then the $\%H E$ will be worse than the fgures given above. Kurpiel and Roncalli (2009) report a worsening of $\%H E$ for delta hedging, with 1-day rebalancing from $0.15\%$ when $\sigma$ is constant (i.e. a Black–Scholes environment) to around $0.2\substack{-0.25\%}$ in a stochastic volatility world.  

Note that in our examples of delta hedging we have ignored rebalancing costs (i.e. bid–ask spreads on stocks, commissions, brokerage fees, stamp duty etc.) but in a ‘real world’ hedge these must be factored in to the cost of the hedge. Normally this would be done by Ms Short, the options trader at Morgan Stanley, initially selling the option above its Black–Scholes price of $C_{0}=\$10.45$ . How much she can sell the option at a price in excess of $\$10.45$ , depends on the degree of competition between options dealers, the market awareness of the hedge fund Goldfnger buying the option, and the transparency of prices quotes (and other fees) in the market place.  

# 27.2.3 Using Futures  

In practice, delta hedging an options position is usually undertaken with futures contracts on the underlying asset, rather than using the underlying asset itself, because transactions costs are lower in futures markets than in the cash markets. The futures price on a stock (index) paying a continuous dividend at a rate $\delta$ or a currency futures (where $\delta=r_{f}.$ ) we have:  

$$
F=S e^{(r-\delta)T^{*}}\qquad{\mathrm{hence}}\partial F/\partial S=e^{(r-\delta)T^{*}}
$$  

where $T^{*}$ is the maturity of the futures contract (which need not equal the maturity of the options being hedged). The delta of a futures contract is $e^{(r-\delta)T^{*}}$ . If the stock price $s$ changes by 1 unit then (27.8) shows that $F$ changes by $e^{(r-\delta)T^{*}}$ units. Hence $e^{-(r-\delta)T^{*}}$ futures contracts have the same sensitivity to changes in the stock prices as does one stock. Hence, if $\mathbf{\ddot{\it{N}}}_{S}$ is the required position in the underlying asset (e.g. stocks) for delta hedging the options position, then the number of futures contracts needed to delta hedge the options position is $N_{F}=N_{S}e^{-(r-\delta)T^{*}}$ contracts.5  

Note that the delta of a forward contract may difer from that for a futures contract. The value of a forward contract on a dividend paying stock at time $t$ is $V_{f w d}=$ $(F_{t}-F_{0})e^{-r T}=S_{t}e^{-\delta T}-F_{0}e^{-r T}$ where $F_{0}=S_{0}e^{(r-\delta)T}$ is the price agreed when the for푓w푤%ard contract was initiated (at $t=0$ ). Hence $\partial V_{f w d}/\partial S=e^{-\delta T}$ is the delta of a forward contract (on a dividend paying stock) and, the number of forward contracts to delta hedge the options position is $N_{F}=N_{S}e^{-\delta T}$ . If the forward contract is on a non-dividend paying stock then $N_{F}=N_{S}$ .  

# EXAMPLE 27.1  

# Delta Hedging Using Futures Contracts  

A portfolio of options on stock-A has $\Delta_{0}=-2{,}000$ . To simplify, assume dividends on stock-A are paid continuously (over the life of the option). Domestic interest rates are $4\%$ p.a. A futures contract on stock-A with a maturity of 9 months, which pays dividends at $\delta=2\%$ is available.  

The portfolio of options on stock-A can be delta hedged with a long position in 2,000 stocks-A. Alternatively, the portfolio of stock options can be hedged by buying $H_{F}=2{,}000\ e^{-(0.04-0.02)(9/12)}=1{,}970$ futures contracts on stock-A.  

# 27.2.4 Delta Hedging Under Stochastic Volatility  

Above we have assessed the success of a delta-hedging strategy assuming a GBM for the stock price and a value for delta given by the Black–Scholes equation, which assumes a constant volatility. But what if in the real world volatility is stochastic, how might we undertake the delta hedge?  

In this case the ‘correct’ delta of the call is not given by the Black–Scholes equation $\Delta_{c}=N(d_{1})$ . In the presence of stochastic volatility, Heston (1973) provides an (approximate) closed-form solution for the option premium and a ‘correct’ formula for the option’s delta, which we denote $\Delta_{H}$ . Assume Ms Short sells a call option at the price $C_{H}$ given by Heston’s approximate closed-form solution (see Chapter 26):  

$$
C_{H}=f[(S,K,r,\delta,T-t);\quad(\overline{{V}},\xi,\rho,\alpha,b)]
$$  

and she dynamically delta hedges by initially buying $\Delta_{H}$ stocks. To simulate changes in the stock price (under stochastic volatility) we need two equations:  

$$
d S=\mu S d t+S\sqrt{V}d z_{s}a n d d V=\beta(\overline{{V}}-V)d t+\xi V^{\alpha}d z_{\nu}
$$  

where $d z_{i}=\varepsilon_{i}{\sqrt{d t}}$ and $\mu=$ the real world growth in the stock price.6 Given simulated ‘real world’ values of $S$ , Ms Short then delta hedges each day (say) using the changing value of Heston’s $\Delta_{H}$ and calculates the daily standard error of hedging error $\%H E$ , over repeated simulations.  

We can repeat this experiment for diferent rebalancing periods (e.g. 2 days, 5 days, 25 days, etc.) in order to fnd the smallest $\%H E$ after incorporating realistic rebalancing costs of buying and selling stocks and hence taking account of transactions costs. The $\%H E$ will tend to be smaller the more frequently Ms Short rebalances but this may be ofset by higher transactions costs.  

We could also see whether simulating $s$ in a stochastic volatility world using (27.10) but hedging using the ‘incorrect’ delta $\Delta_{B S}$ from the Black–Scholes model (which assumes a constant volatility) is substantially larger than the hedging error when using the ‘correct’ $\Delta_{H}$ . Ignoring transactions costs, we expect the hedging error using Heston’s $\Delta_{H}$ to be smaller than the hedging error using $\Delta_{B S}$ , but with transactions costs the outcome is not obvious. It is possible that with transactions costs, the hedging error using the ‘incorrect’ Black–Scholes delta $\Delta_{B S}$ may not be substantially diferent from using the more complex $\Delta_{H}$ from the Heston model.  

# 27.3 SUMMARY  

• Dynamic delta hedging a written (sold) call requires a long position in $\Delta_{c}$ stocks (i.e. delta hedging calls, requires a long-short position). Delta hedging a long position in puts requires a long position in $|\Delta_{p}|$ stocks (i.e. delta hedging puts requires a long-long position).   
• Ignoring transactions costs, a trader who sells a call option (say) and continuously rebalances her hedge portfolio by buying and selling stocks, will end up neither gaining nor losing whenever she closes out all her positions (in stocks and calls) and pays of any loans (debts) incurred. This is true if she closes out at any time up to and including the expiration date of the options.   
• Hedging using the Black–Scholes delta does not provide a hedge against large changes in S, or against changes in volatility or interest rates, unless we explicitly include stochastic models for these variables (e.g. Heston’s stochastic volatility model).   
• The transactions costs of delta hedging an options position are recouped by initially selling the call or put, above the ‘theoretical’ price given by the Black–Scholes equation. The quoted price will be infuenced by the forces of competition (e.g. wage costs of traders, costs of IT, etc.) amongst market makers in options (either traders on exchanges such as the CBOT or by the trading desks of large universal banks such as JPMorgan-Chase, Morgan Stanley, Citibank).  

# EXERCISES  

# Question 1  

Suppose you currently hold several (European) put options on the same underlying asset (Apple-stocks). Will these call options all have the same value for delta? Explain.  

# Question 2  

Explain how you delta hedge a long call option (on a stock) with $\Delta_{0}=0.6$ . After delta hedging explain what happens if the stock price rises by $\$2$ .  

# Question 3  

Explain how you would delta hedge a short put (on a stock) with $\Delta_{0}=-0.4$ . After delta hedging explain what happens if the stock price rises by $\$2$ .  

# Question 4  

How would you replicate the price movements of a long put, when the put has a delta of minus 0.4?  

# Question 5  

Today you own 2,000 stocks with price $S=\$100$ . A call option with $\Delta_{0}=0.4$ is available. Assume each call delivers one stock. Explain how to set up a delta-neutral portfolio. Explain what happens when the stock price falls by $\$2$ .  

# Question 6  

You have just purchased (at $t=0$ ) one long call option on a stock, with strike $K=98$ and $\Delta=0.4$ . The call premium, $C_{o}=\$5$ , the time to maturity is $T={}^{1}/_{4}$ (year, 3 months). The current stock price is $S_{0}=\$100$ and the risk-free rate is $r=3\%$ .  

Using some or all of the above illustrative fgures carefully explain how you can delta hedge your options position over the next 3 months (when the call option expires).  

(a) Consider the outcome after 1 day if the stock price falls by $\$2$ .   
(b) Consider the outcome at expiration, $T$ , if the stock price falls monotonically and the call option ends out-of-the-money (OTM, $S_{T}\ll K\`.$ ). Assume at expiration, $T$ you have $\$5.14$ in a deposit account.  

# Question 7  

At $t=0$ you buy an at-the-money put option for $P_{0}=\$5$ , with $K=100$ , and $\Delta=-0.5.$ . The time to maturity is $T={}^{1}/_{4}$ (year, 3 months). The current stock price is $S_{0}=\$100$ and the risk-free rate is $r=3\%$ .  

You delta hedge the long put to maturity. Assume the stock price falls monotonically and ends up well below the strike price at $S_{T}=\$60$ . At $T$ you have debt (bank loan) of $D_{T}=\mathfrak{H}100.2$ . Using some or all of the above illustrative fgures carefully explain what happens in the hedge, particularly at $t=0$ and at $t=T$ .  

# Question 8  

Suppose you believe that the volatility of the stock return over the next 3 months will be ${\widehat{\boldsymbol{\sigma}}}=$ $25\%$ which implies a Black–Scholes price of $\widehat{C}=\delta2$ . Given the current quoted price of a 3-month European call option of $C_{i m p}=\$3$ , you calculate that implied volatility is $\sigma_{i m p}=$ $30\%$ . What should you now do to speculate on your view of volatility while protecting your position against changes in the stock price?  