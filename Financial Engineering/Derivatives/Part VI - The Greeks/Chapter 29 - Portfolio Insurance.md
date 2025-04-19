---
tags:
  - dynamic_hedging
  - portfolio_insurance
  - put_call_parity
  - replication_portfolio
  - stock_put
aliases:
  - Protective Put
  - Static Hedge
  - Stock Put Insurance
key_concepts:
  - Drawbacks of stock put
  - Dynamic portfolio insurance
  - Hedging equity portfolio
  - Replication portfolio of calls
  - Static stock put insurance
---
# Portfolio Insurance  

# Aims  

• To show how static stock $+$ put insurance can achieve a lower bound for the value of a diversifed stock portfolio, while maintaining most of the upside potential. • To demonstrate how static stock $^+$ put insurance is equivalent to a replication portfolio of calls and T-bills. This is an example of put–call parity using stock index options. • To analyse how day-to-day price changes of a ‘stock put’ portfolio can be replicated using either a ‘stock futures’ portfolio or a ‘stock $+\mathrm{T}$ -Bill’ portfolio. Replication portfolios are used because they are often less costly than directly using the ‘stock put’ combination.  

Portfolio insurance is a general term which refers to a strategy of hedging an equity portfolio to ensure that it does not fall below some prescribed minimum value, while also retaining most of the upside potential, should stock prices increase. We have already outlined the static hedging strategy of stock $^+$ put insurance which at maturity (of the put) ensures a lower bound equal to the strike price of the put. Upside potential is also maintained because if the stock price (at maturity of the put) is greater than the strike price, the put expires worthless but the investor benefts from high stock prices (less the put premium). However, in practice, stock put insurance has a number of drawbacks, namely:  

• the hedging horizon of pension funds and mutual fund managers may be long and stock index options then have to be rolled over and this may be costly. • most traded stock index options are American and their prices refect the early-exercise premium. Portfolio managers with fxed hedging horizons are reluctant to bear this cost. • position limits (set by the clearing house) may prevent portfolio managers setting up their optimal hedged position in stock index puts.  

Because of the above practical problems, methods are available to set up a replication portfolio which mimics the price movements of stock $^+$ put insurance. The originators of these alternative forms of portfolio insurance are Leland and Rubinstein (Leland 1980; Rubinstein 1985; Rubinstein and Leland 1981).  

A key distinction in undertaking portfolio insurance is whether the position is held to maturity (static hedge) or is continuously rebalanced (dynamic hedge). From put–call parity we know that a portfolio of ‘stocks $+$ puts’ is equivalent to a portfolio of ‘calls $^+$ T-Bills’ (i.e. zero-coupon bond or cash held in a deposit account). Hence, we can undertake stock put insurance with a replication portfolio of calls and T-bills.  

We also show that the change in value of a stock $^+$ put portfolio can be replicated using ‘stocks $+$ futures’ and this is generally referred to as dynamic portfolio insurance. Prior to the 1987 stock market crash, dynamic portfolio insurance was very popular as transactions costs are lower for rebalancing a ‘stock $^+$ futures’ portfolio, than for the actual stock put position. However, during the 1987 crash investors using ‘stock futures’ portfolio insurance were unable to undertake trades quick enough to replicate the stock put position and hence the method became less popular immediately after the 1987 crash.  

# 29.1 STATIC HEDGE  

# 29.1.1 Stock Put (Protective Put)  

Here we are concerned only with the value of the ‘stock put’ portfolio at maturity $T$ of the option contract. Suppose it is September and you have $V_{0}=\$560,000$ in a diversifed stock portfolio which replicates the S&P 500 $(\beta_{p}=1)$ . Assume the S&P 500 is at $S_{0}=280$ index points and the December-280, put option on the S&P 500 is priced at $P_{0}=2.97$ (index units). Assume each index unit for the put has a dollar value of $z_{p}=\$500$ , hence:  

Invoice price, put option, $z_{p}P=\S500\left(2.97\right)=\S1,485$ Value of stocks underlying the put option, $z_{p}S=\S500\left(280\right)=\S140,000.$  

For a cost of $\$1,485$ the put is a claim on $\$140,000$ of the index. The put premium is $1.06\%$ of the value of stocks underlying the contract $(=P_{0}/S_{0})$ , the fact that this is relatively small can be useful in simplifying some of the mathematical expressions below. The number of index units held in your portfolio of stocks is:  

$$
N_{0}^{*}=V_{0}/S_{0}=\S560,000/280=2,000\quad\mathrm{~(index~units)}
$$  

Holding 2,000 index units implies that a change in the S&P 500 index of 1 point would lead to a $\$2,000$ change in the value of your stock portfolio (with $\beta_{p}=1\dot{}$ ). To implement stock $^+$ put insurance we hold $N_{0}$ index units in both stocks and puts:  

$$
V_{0}=N_{0}(S_{0}+P_{0})
$$  

Hence our initial holding of stocks and puts in index units is:  

$$
\begin{array}{c}{{N_{0}=\displaystyle\frac{V_{0}}{S_{0}+P_{0}}=\displaystyle\frac{\S560,000}{280+2.97}=1{,979~(\mathrm{index~units})}}}\\ {{N_{0}=\displaystyle\frac{V_{0}}{S_{0}+P_{0}}=\displaystyle\frac{V_{0}}{S_{0}}\displaystyle\frac{1}{(1+P_{0}/S_{0})}=N_{0}^{*}\displaystyle\frac{1}{(1+P_{0}/S_{0})}}}\end{array}
$$  

so if $P_{0}/S_{0}$ is small then $N_{0}$ is very close to $N_{0}^{*}$ . Since the index multiple is $z_{p}=\$500$ the actual number of put contracts purchased is:  

$$
N_{p,0}={\frac{N_{0}}{z_{p}}}={\frac{1{,}979}{500}}=3.96\qquad\scriptstyle(=4{\mathrm{contracts}})
$$  

At expiration, the stock $^+$ put portfolio is worth:  

$$
{\begin{array}{r l r l}{V_{T}=N_{0}S_{T}}&{\quad}&{{\mathrm{if}}S_{T}>K}&{\qquad{\mathrm{(Upside~potential)}}}\\ {V_{T}=N_{0}S_{T}+N_{0}(K-S_{T})=N_{0}K}&{\quad}&{{\mathrm{if}}S_{T}<K}&{\qquad{\mathrm{(Insured~floor~level)}}}\end{array}}
$$  

In each case the net proft is $V_{T}-N_{0}P_{0}$ . We have chosen an ATM put $\begin{array}{r}{{{\cal S}_{0}}={\cal K}=280,}\end{array}$ , although in practice we can choose any strike price. The stock $+$ put portfolio has an ‘insured’ lower value at $T$ of $N_{0}K$ , so that:  

$$
V_{\mathrm{min}}=N_{0}K=1,979\left(280\right)=8554,120
$$  

The static stock $+$ put strategy ensures a minimum value for the portfolio of $\$54,120$ (less the cost of the puts of $4\times\$1,485=\$5,940$ , but also allows any upside capture if $\begin{array}{r}{S_{T}>K}\end{array}$ . For example, if $S_{T}=310$ $\phantom{-}>K=280,$ then the puts are not exercised and:  

$$
{\begin{array}{r l r l}&{{\mathrm{lue~of~insured~portfolio}},}&{V_{T}=N_{0}S_{T}}&{=1.979\left(310\right)}&{=\S614.490}\\ &{{\mathrm{lue~of~}}u n i n s u r e d{\mathrm{~portfolio}},}&{N_{0}^{*}S_{T}}&{=2.000\left(310\right)}&{=\S620.000}\end{array}}
$$  

Hence, for $S_{T}=310$ the upside capture is $98.95\%$ $(=\S614{,}490/\S620{,}000=1{,}979/2{,}000).$ .  

# 29.1.2 Call T-bill: Fiduciary Call  

From put–call parity we know that $\mathrm{\dot{\stock{+}p u t}=c a l l{+}T{-}b i}$ ll’, hence the payof from the stock put portfolio can be replicated using ‘calls $+$ T-bills’. Our task, therefore, is to choose the number of calls and T-bills which replicates the minimum payof at maturity $V_{\mathrm{min}}=N_{0}K$  

of the stock $+$ put portfolio. This strategy is sometimes referred to as a fduciary call. The value of a portfolio of $N_{C}$ calls and $N_{B}$ T-bills (i.e. zero-coupon bond) is:  

$$
V_{C,B}=N_{C}C+N_{B}B
$$  

If $B$ is the market price of a T-bill with face value $M=\$100$ and maturity date $T$ then1:  

$$
B=M e^{-r T}
$$  

In a static hedge, the value of the ‘call $+\mathrm{T}$ -bill’ at expiration is:  

$$
\begin{array}{l l}{{V_{T}=N_{B}M}}&{{{\mathrm{if}}S_{T}<K}}\\ {{V_{T}=N_{C}(S_{T}-K)+N_{B}M}}&{{{\mathrm{if}}S_{T}\geq K}}\end{array}
$$  

The worst outcome is when the call expires out-of-the-money and hence the minimum value is:  

$$
V_{\operatorname*{min}}^{C,B}=N_{B}M
$$  

We now set $V_{\operatorname*{min}}^{C,B}$ equal to the minimum value of the stock $+$ put portfolio $V_{\operatorname*{min}}^{S,P}$ since this is what we are trying to replicate (at expiration). Hence, the number of T-bills required is  

$$
N_{B}={\frac{V_{\mathrm{min}}^{S,P}}{M}}={\frac{N_{0}K}{M}}={\frac{{\mathfrak{F}}554,120}{\mathfrak{F}100}}=5,541.2\quad{\mathrm{(T-bills)}}
$$  

Having fxed $N_{B}$ , the number of calls is then determined using (29.8):  

$$
N_{C}=(V_{0}-N_{B}B)/C
$$  

Using (29.13), substituting $N_{B}$ from equation (29.12), and for $M$ from equation (29.10) and using put–call parity $\zeta=P+\bar{S}-K e^{-r T})$ it can be shown that the number of index units held in calls is:  

$$
N_{C}=\left({\frac{V_{0}}{S_{0}+P_{0}}}\right)=1{,}979{\mathrm{~index~units~}}(=1{,}979/500=3{.}96{\mathrm{~contracts}})
$$  

which is the same as the number of puts in our original ‘stock $^+$ put’ portfolio (Equation (29.3)). In practice, the problem with static ‘stock $^+$ put’ and ‘cal $\cdot+$ T-bill’ portfolio insurance is that the required exchange traded calls and puts may not be available with a maturity date which matches the stock investor’s desired holding period, with the desired strike price. The investor could try and obtain the required options from the OTC market but this could be expensive. An alternative is to replicate the period-by-period payofs from ‘stock $^+$ put’ insurance using dynamic hedging with ‘stocks $+$ index futures’ or ‘stocks $^+$ T-bills’. By construction, we make sure the change in value of these two replication portfolios exactly mirrors that of the ‘stock put’ portfolio, over any small interval of time. Hence, as we approach the maturity date of the options, either of these two replication portfolios will also ensure a minimum value $N_{0}K$ – the same as that from the ‘stock put’ portfolio.  

# 29.2 DYNAMIC PORTFOLIO INSURANCE  

Our aim is to continuously mimic the changes in value of a ‘stock $^+$ put’ portfolio frst by using ‘stocks $+$ index-futures’ and second by using ‘stocks $+\mathrm{T}$ -bills’. The initial values of the options and futures contracts are given in Example 29.1, which also summarises the replication portfolios required.  

EXAMPLE 29.1   
Portfolio Insurance   
Value of stock portfolio: $V_{0}=\$560,000$ , S&P 500 index: $S_{0}=280$   
Maturity of derivatives: $T=0.10$ , Risk-free rate: $r=0.10\left(10\%\right)$   
S&P500 : $\sigma=0.12\$ Put premium: $P_{0}=2.97$ index units   
Strike price: $K=280$ , Put delta $\Delta_{p}=-0.3888$   
Call delta: $1+\Delta_{p}=\Delta_{c}=0.6112$ , Futures $(t=0)$ : $\left.F_{0}=S_{0}e^{r T}=282.814\right.$   
Price of T-bill: $B=M e^{-r T}=99.00$ , Value of index point, $z_{F}=\$500$  

# Hedge positions:  

Number of units held in stocks $N_{0}^{*}=V_{0}/S_{0}=2{,}000$ index units  

Stock put insurance: $N_{0}=V_{0}/(S_{0}+P_{0})=1{,}979$ index units Stock futures insurance:  

$$
\begin{array}{l}{N_{F}=\left[N_{0}\Delta_{c}-N_{0}^{*}\right]{\frac{e^{-r T}}{Z_{F}}}}\\ {=[(1{,}979)(0{.}6112)-2{,}000](0{.}99/500)=-1{.}565}\end{array}
$$  

(continued)  

(continued)  

Stock $+\mathbf{T}$ -bill insurance:  

$$
N_{S}=\frac{V_{0}}{\left(S_{0}+P_{0}\right)}\Delta_{c}=1{,}979\left(0{.}6112\right)=1{,}209.6\
$$  

$$
N_{B}=\frac{V_{s,p}-(N_{0}\Delta_{c})S}{B}
$$  

2,235.3 long -bills  

For simplicity we take the time to maturity for both the futures and options contracts to be the same and the options are ATM. These assumptions are easily changed and do not afect the principles involved. Note that the hedge period will often be less than the time to maturity of the derivatives contracts. We assume that rebalancing takes place over small intervals of time, so the actual change in option premia are $\Delta d S$ .  

# 29.2.1 Stock Put Portfolio  

We have $V_{0}$ invested in a stock $^+$ put portfolio consisting of $N_{0}$ index units held in both stocks and puts:  

$$
N_{0}={\bigg(}{\frac{V_{0}}{S_{0}+P_{0}}}{\bigg)}=1{,}979{\mathrm{~index~units}}
$$  

Note that $N_{0}$ is fxed throughout the hedge. At $t>0$ the ‘stock $^+$ put’ portfolio has:  

$$
\begin{array}{l}{V_{s,p}=N_{0}(S+P)}\\ {\partial V_{s,p}/\partial S=N_{0}(1+\Delta_{p})}\end{array}
$$  

# 29.2.2 Stock Futures Portfolio  

We now replicate changes in value of the ‘stock $^+$ put’ portfolio using $N_{0}^{*}$ stocks and $N_{f}$ futures contracts. The futures contract requires no up-front payment (ignore margin calls) so the number of index units held in stocks is:  

$$
N_{0}^{*}=V_{0}/S_{0}=2{,}000\qquad\mathrm{(index\units)}
$$  

which is fxed throughout the hedge. The value of the ‘stock $^+$ futures’ portfolio at $t>0$ is:  

$$
V_{S,F}=N_{0}^{*}S+N_{F}z_{F}F
$$  

where $z_{F}$ is the value of an index point on the S&P 500 futures contract. Also, $F=S e^{r T}$ (on a non-dividend paying stock). The change in value of the ‘stock $^{+}$ futures’ portfolio is:  

$$
\frac{\partial V_{S,F}}{\partial S}=N_{0}^{*}z_{F}+N_{F}\left(\frac{\partial F}{\partial S}\right)
$$  

Our task is to fnd that value for $N_{F}$ which replicates changes in the value of the ‘stock $^+$ put’ portfolio. Equating (29.17) and (29.20) gives:  

$$
N_{0}(1+\Delta_{p})=N_{0}^{*}+z_{F}N_{F}(\partial F/\partial S)
$$  

Solving for $N_{F}$ :  

$$
N_{F}=[N_{0}(1+\Delta_{p})-N_{0}^{*}]\quad\frac{e^{-r T}}{z_{F}}=-1.565(\mathrm{Shortfutures})^{2}
$$  

From (29.22), $N_{F}$ is negative, hence the replication portfolio requires a short position in index futures. The number of futures contracts to replicate the ‘stock $^+$ put’ portfolio must be continually rebalanced (by either buying or selling futures) as the put-delta changes with the stock price, time to maturity, volatility etc. Note that if we assume $N_{0}\approx N_{0}^{*}$ then (29.22) simplifes to $N_{F}=N_{0}\Delta_{p}[e^{-r(T-t)}/z_{F}]$ .  

# 29.2.3 Stock T-bill Portfolio  

We know from put–call parity that a replication portfolio for ‘stock $^+$ put’ is a ‘cal $+\mathrm{T}$ -bill’. Suppose we have a portfolio of $N_{S}$ index units in stocks and $N_{B}$ T-bills, then:  

$$
\begin{array}{r l}&{V_{S,B}=N_{S}S+N_{B}B\quad\mathrm{~and~}}\\ &{\partial{V_{S,B}}/\partial{S}=N_{S}}\end{array}
$$  

Equating (29.23b) with (29.17) gives the number of stocks required to replicate the ‘stock put’ portfolio:  

$$
N_{s}=N_{0}(1+\Delta_{p})=N_{0}\Delta_{c}=1{,}209.6\mathrm{(indexunits)}
$$  

The number of T-bills in the replication portfolio is then derived from (29.23a), using $V_{S,B}=V_{s,p}$ :  

$$
\begin{array}{r l}&{N_{B}=\frac{V_{S,B}-N_{S}S}{B}=\frac{V_{s,p}-N_{S}S}{B}}\\ &{N_{B}=\frac{V_{s,p}-(N_{0}\Delta_{c})S}{B}=2{,}235.3\quad\mathrm{(long\T-bills)}}\end{array}
$$  

The $\$5$ -value of T-bills (cash) held is $N_{B}B$ , which will vary through time as the replication portfolio must be continually rebalanced.  

# 29.2.4 Numerical Example  

The hedge outcomes are given in Example 29.2 for a (small) fall in the stock index $d S=-1$ point (which for simplicity we assume takes place over a small interval of time, so the time to maturity $T$ of the derivatives remains unchanged).  

# EXAMPLE 29.2  

# Outcomes Replication Portfolios  

Fall of 1 unit in the S&P 500 index, $d S=-1$ . Hence $S_{1}=280-1=279$  

# New derivatives prices (at $\mathbf{t}=\mathbf{1}$ )  

Put premium $P$ $=3.377$ using Black-Scholes   
Futures $\left(t=1\right){\cal F}_{1}=S_{1}e^{r T}$ $=281.804\$   
Change in put premium $d P=\Delta_{p}d S$ $=-0.3888$ approximated by the put-delta   
Change in futures price $d F=281.804-282.814=-1.01$  

# 1. Stock put portfolio  

Gain stocks $=N_{0}d S=1\mathrm{,}979\:(-1)$ $=-1,979$   
Gain puts $\begin{array}{r}{=N_{0}\Delta_{p}d S=1,979\left(-0.3888\right)(-1)=769.4}\\ {=-1,20}\end{array}$   
gain 9.6 ( $0.2\%$ of portfolio value  

# 2. Stock futures  

Gain stocks $\begin{array}{l l}{{=N_{0}^{\ast}d S=2,000(-1)}}&{{=-2,000}}\\ {{=N_{F}d F z_{F}=(-1.565)(-1.01)500}}&{{=790.3}}\\ {{}}&{{=-{\bf1},2{\bf09.6}}}\end{array}$   
Gain futures   
gain  

# 3. Stock T-bill  

Gain stocks $;=N_{S}d S=1,209.6(-1)=-1,209.6$   
Gain -bills $=0$ change in -bill price   
gain = -1, 209.6  

Example 29.2 shows that the change in value of the two replication portfolios equals that for the ‘stock $^+$ put’ portfolio (of $-\$1,209.6$ . However, this is because we have assumed that the change in the put premium is exactly given by $d P=\Delta_{p}d S$ . The latter is an approximation and the ‘new’ (correct) put-premium is given by the full Black–Scholes formula $P=P(S,K,\sigma,r,T-t)$ , so the ‘true change’ in the ‘stock $^+$ put’ portfolio is actually –1,173.58, rather than $^{-1,209.6}$ . In practice our two replication portfolios will not produce exactly the same change in value as the ‘stock $+$ put’ portfolio because:  

• option deltas only give an approximation to changes in options premia   
• we ignore transactions costs of rebalancing   
• the option deltas do not take into account changes in the option price due to large changes in the stock price, due to the loss of time value and due to changes in interest rates and volatility – hence the replication portfolios will not exactly mimic changes in value of the stock $^+$ put portfolio.   
• in practical situations there would also be some rounding errors due to the requirement of purchasing whole numbers of calls or futures contracts.  

Replicating the change in value of a ‘stock put’ portfolio over many time periods using ‘stocks futures’ and ‘calls T-bills’ is provided in Excel. We assume that rebalancing is over a ‘small’ time horizon and (to simplify) we hold constant interest rates, volatility and the time to maturity of the option.  

The above practical di\$culties of replicating price movements of a ‘stock $^+$ put’ portfolio were highlighted in the 1987 stock market crash when the ‘foor’ provided by dynamic portfolio insurance (rather than directly holding ‘stocks puts’) turned out to be rather more expensive and less efective than the model outlined above would indicate. These issues are discussed in Finance Blog 29.1.  

# Finance Blog 29.1 Replicating Stock $^+$ Put Insurance  

After the 1974 stock market crash, the idea of portfolio insurance was to dominate the thinking of a UCLA Berkley academic Hayne Leland and his colleague Mark Rubinstein. In 1974 put options on stock indices were not available but Leland realised that you could replicate the payof to a stock $+$ put portfolio by using ‘stocks $+\mathrm{T}$ -bills’. Given a desired foor $\begin{array}{r}{\left(=K<S_{0}\right)}\end{array}$ ) for your stock portfolio, you could achieve this minimum portfolio value by selling stocks  

(continued)  

# (continued)  

as their prices fell and investing these funds in T-bills. If stock prices continue to fall you would continually sell stocks so that you would eventually be $100\%$ in T-bills (and hence insured against any further fall in stock prices). On the other hand, as stock prices rise and you move further above the foor $K_{:}$ , then in your replication portfolio you buy more stock and sell of some of your T-bills – you therefore have more upside potential.  

The portfolio insurance marketed by Leland-Rubinstein Associates promised protection against fve moves of $5\%$ in the market index and remained operative until these ‘fve moves’ had taken place. Because of the complexity of portfolio insurance, Leland and Rubinstein’s frst ‘pitch’ in 1979 at the investment banks yielded few takers. So they hired a marketing manager, John O’Brien, whose name was added to their consultancy frm. Interest grew, but active fund managers (i.e. ‘stock pickers’) did not like being told to sell individual stocks in a falling market. The advent of stock index futures in 1983 solved this problem, since the replication portfolio could now be engineered from ‘stocks plus futures’, so existing stock portfolios could be held unchanged and portfolio insurance implemented by selling index futures, as the S&P 500 index fell.  

Business grew throughout the early 1980s but then the 1987 crash came along. With portfolio insurance using ‘stocks futures’, you have to try and sell stocks or stock index futures in a falling market. Now in principle, market participants should be aware that ‘portfolio insurers’ are selling stocks and index futures, not because they have negative information about the future course of stock prices but merely to protect their existing stock portfolio. Hence, there should be some willing buyers at current market prices.  

On Friday, 16 October 1987, the Dow Jones fell by $10\%$ and about $40\%$ of all selling came from portfolio insurers. There was an overhang of sell orders on Monday, 19 October 1987. Many stocks were failing to trade on the Monday and the Dow fell by a record $23\%$ in one day. So you couldn’t execute ‘sell orders’ from your replication portfolio. But things became worse. The arbitrage link between futures prices and spot prices also broke down. The ‘fair’ futures index value was around 280 but the futures contract opened at around 260, a discount of about $7.5\%$ .  

Arbitrageurs should have stepped in and bought futures (at a ‘low’ price) while simultaneously short-selling stocks. But they couldn’t execute the latter trades, so futures prices were ‘uncoupled’ from spot prices – thus invalidating the ‘mathematics’ of the number of futures to short in the stock futures replication strategy. The Brady Commission (1988) placed much of the blame for the 1987 crash on the large amount of sales by portfolio insurers. However, some of the fall was undoubtedly also due to simple ‘mechanical’ stop-loss orders by investors, whereby sales are triggered when the stock price falls below a pre-specifed price.  

By and large, portfolio insurance did result in portfolios staying at or above their declared minimum values. But a lack of market liquidity meant this was more costly than predicted from the theoretical model. The moral of the story here might be that if you expect a really severe crash then buy the ‘real thing’ – the put – since the writer has to pay you $K$ per stock (and there are margin requirements to ensure ‘writers’ can meet their obligations). Otherwise, if you do decide to use portfolio insurance, it would be prudent to allow for the possibility of ‘illiquid’ markets in crisis periods. A lack of liquidity in derivatives markets (e.g. for credit default swaps [CDSs] and collateralised debt obligations [CDOs]) was also a contributing factor to the crash of 2008–9 – see Chapters 42 and 43.  

Source: Adapted from Cuthbertson and Nitzsche (2001).  

# 29.3 SUMMARY  

• Portfolio insurance is a technique which allows fund managers to secure a minimum insured value for their diversifed stock portfolio, while still allowing considerable upside capture should the stock market increase.   
• Holding a portfolio of stocks and then purchasing $N_{0}$ puts and holding them to maturity ensures a minimum value for the stock portfolio of $V_{\mathrm{min}}=N_{0}K$ , at maturity of the option. This is static portfolio insurance. Stock $^+$ put insurance can be costly and the puts with the required strike prices and maturity dates may not be available.   
• Although a ‘stock $^+$ put’ portfolio has a minimum insured value at maturity, its value changes prior to maturity, as the stock price and hence the put premium change over time. The dynamic price behaviour of the ‘stock $^+$ put’ portfolio can be ‘replicated’ using a number of alternative portfolios which may be more liquid and less costly. This is replication using dynamic trading.   
• A long position in a portfolio of stocks plus a short position in stock index futures provides a low cost method of replicating the change in value of a ‘stock $^+$ put’ portfolio. To replicate changes in a ‘stock put’ portfolio, the number of index futures contracts to short must be frequently rebalanced, as the stock index, volatility, and time to maturity of the option change.   
• A ‘stock T-bill’ portfolio will also replicate the change in value of a ‘stock $+$ put’ portfolio – again continuous rebalancing is required.   
• The delta of an option only provides an approximation to the change in value of the option. Therefore, replicating changes in the value of a ‘stock $^+$ put’ portfolio via dynamic trading will only be successful if changes in stock (index) prices are small (or equivalently, frequent rebalancing takes place) and there are no changes in the volatility of the stock index or in the risk-free rate (both of which infuence the options price).  

# EXERCISES  

Question 1 Briefy explain the idea of portfolio insurance, if you currently hold a stock portfolio.  

# Question 2  

Why undertake dynamic portfolio insurance using stocks $+$ futures, instead of insuring your stocks by buying put options (on the stock) and holding the put option to maturity, T?  

# Question 3  

Why does dynamic portfolio insurance using stocks futures to mimic the price changes of a stock $^+$ put portfolio, cause rapid buying or selling of futures contracts when the stock market moves up or down by a large amount?  

# Question 4  

You hold $\$675,000$ in a diversifed portfolio that tracks the S&P 500 index which currently stands at $S_{0}=1\AA,500$ . The value of an index point on the S&P 500 is $\$250$ . You would like to buy puts to insure your portfolio so that the minimum value is $\$600,000$ at maturity of the puts.  

(a) What strike price will the puts have? (b) What is the total cost of the puts if $P=16$ (index units)?  

# Question 5  

You currently have $V_{0}$ to invest. Consider a portfolio consisting of an equal number of index units $N_{0}$ in stocks with price $S_{0}$ and puts with price $P_{0}$ , so that $V_{0}^{s,p}=N_{0}(S_{0}+P_{0})$ .  

(a) Derive the formula for the number of futures contracts $N_{f}$ needed to replicate the price dynamics of the stock $^+$ put portfolio.   
(b) Why might the stock $^{+}$ futures portfolio not accurately mimic the change in value of the stock put portfolio?  

# Question 6  

On 1 June, you hold a stock portfolio with a current value of $V_{0}=\mathbb{\S}9,750,000$ , that mimics the S&P 500 index. On 1 June the S&P 500 index, $S_{0}=1\mathrm{,}500\$ . (Value of an index point is $\$250$ ). On 1 June index-puts with maturity $T={^{1}\mathrm{/}}_{2}$ year strike $K=1{,}400$ (points) and $\Delta_{p}=-0.23$ , have a premium of $P=31$ (points).  

The S&P 500 futures index is $F_{0}=1{,}538$ and the risk-free rate is $r=5\%$ p.a. (continuously compounded). The time to maturity of futures and the put contract is $T={^{1}\mathrm{/}}_{2}$ year (6 months, maturity 1 December).  

Use the information to set up a dynamic replication portfolio using stocks $+$ index futures which ‘tracks’ the price movements of a portfolio of an equal number $N_{0}$ of stocks and puts. Show that the change in value of the stock $^+$ put portfolio equals that of the stock $^+$ futures portfolio, for $d S=+1$ . Assume you can use fractional numbers of futures contracts.  

# Question 7  

You have $V_{0}$ to invest. You hold $N_{0}$ index units of the S&P 500 in a portfolio of stocks and $N_{0}$ index units in puts. How can you ensure that the change in value of this stock $^+$ put portfolio (for small changes in the S&P 500 index, $S$ ) will mimic the change in value of a call $+\mathrm{T}$ -bill portfolio? (Hint: use the put–call parity condition, for a non-dividend paying stock index).  