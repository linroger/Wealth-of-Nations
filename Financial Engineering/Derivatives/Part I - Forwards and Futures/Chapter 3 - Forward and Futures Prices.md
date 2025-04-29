---
tags:
  - arbitrage
  - cash_and_carry
  - forward_contracts
  - futures_prices
  - risk_free_rate
aliases:
  - Forward Pricing
  - Futures Pricing
  - No-Arbitrage Pricing
key_concepts:
  - Cash-and-carry arbitrage
  - Fair forward price
  - Forward contract replication
  - Implied repo rate
  - Income stream impact
---
# Forward and Futures Prices  

# Aims  

• To construct a synthetic or replication portfolio whose cash fows mimic the cash fows in an actual forward contract.   
• To show how cash-and-carry arbitrage can be used to determine the correct (no-arbitrage) ‘fair’ price for a forward contract on a (non-dividend paying) stock.   
• To interpret cash-and-carry arbitrage in terms of the implied repo rate and the actual repo rate.   
• To extend our arbitrage approach to determine the fair forward price when the underlying asset pays an income stream (e.g. dividends on a stock) or has storage costs (e.g. oil, wheat) or can be used as an input to the production process (e.g. the convenience yield of owning oil).   
• To distinguish between the price of a forward contract at inception and the value of a forward contract that has been in existence for some time.  

# 3.1 PRICING FORWARD CONTRACTS  

In this section we analyse how forward and future prices are determined as functions of known variables such as the current market price of the underlying asset and the risk-free interest rate. Forward contracts are easier to analyse than futures contracts, since the latter have the added complication of daily settlement (i.e. marking-to-market) whereas for the forward contract there is one payment at the maturity date. However, it can be shown that the futures price closely follows that of the forward price (for contracts with the same maturity date). Therefore, for the most part the reader can consider the analysis of ‘forward’ and ‘futures’ prices as being interchangeable. In general we assume:  

zero transactions costs   
• zero tax rates   
• agents can borrow or lend unlimited amounts at the risk-free rate of interest   
• short-selling of the underlying asset is possible   
• risk-free arbitrage opportunities are instantaneously eliminated.  

For the most part we use (risk-free) arbitrage to price futures contracts and this method is also referred to as the cost of carry method.  

# 3.1.1 Non-income Paying Security  

Consider the futures price on a stock (which pays no dividends). The futures contract is for the delivery of a single stock in 3 months’ time (Figure 3.1). We set up a situation where initially it is possible to make a risk-free arbitrage proft because the quoted futures price is incorrect. Consider the following ‘prices’:  

$F_{q}=\$102$ is the quoted futures price in Chicago 25 June $\mathit{\check{t}}=0\mathit{\check{\Psi}}$ with maturity date of 25 September $T=1/4$ is the time to maturity of futures contract in years or fraction of year $S=\$100$ is the spot cash market price of the stock the NYSE 25 June $r=0.04$ is the risk-free interest rate $(=4\%$ simple interest  

FIGURE 3.1 Risk-free arbitrage   


<html><body><table><tr><td>Stock price</td><td>S = $100</td></tr><tr><td>Risk-free rate</td><td>r = 4% p.a.</td></tr><tr><td>Quoted future price</td><td>F= $102</td></tr><tr><td>Strategy today (25 June)</td><td>Sell (short) futures contract at $1o2 (receive no cash today)</td></tr><tr><td></td><td>Borrow $1oo from bank and buy the stock (= synthetic</td></tr><tr><td>future)</td><td></td></tr><tr><td>Use no ‘own funds'</td><td></td></tr><tr><td></td><td>3 months' time : 25 September (T = 1/4)</td></tr><tr><td></td><td>Bank loan outstanding = $100(1 + 0.04/4) = $101</td></tr><tr><td></td><td>Deliver stock,receipt from futures contract = $102</td></tr><tr><td>Riskless profit</td><td>= $1</td></tr></table></body></html>  

# 3.1.2 Overpriced Futures Contract  

Below, we see that the correct (‘no-arbitrage’ or ‘fair’) futures price is $F=\$101$ , which with a quoted price $F_{q}=\$102$ implies the futures contract is overpriced and it is possible to earn a risk-free (arbitrage) proft. Here’s how. The arbitrageur Ms Arb on 25 June (at 11 a.m.) borrows $\$100$ from bank-A and purchases stock-ABC on the NYSE. She therefore knows for certain that she can deliver the stock in 3 months on 25 September (since it is ‘in her pocket’ and will stay there – she ‘carries’ the stock). This strategy involves no ‘own capital’ by Ms Arb, since the money is borrowed.  

Ms Arb on 25 June (at 11 a.m.) also sells a futures contract (on stock-ABC) in Chicago at $F_{q}=\$102$ (to another trader in Chicago, who may be a hedger or a speculator – we don’t care – we only care about our own trades). Note that Ms Arb’s ‘sell order’ is noted by the futures clearing house in Chicago and Ms Arb does not pay any money today (we ignore margin payments). By selling the September-futures contract on 25 June and holding it to maturity, Ms Arb is legally obliged to deliver one stock on 25 September in Chicago, when she will receive today’s quoted futures price, $F_{q}=\$102$ .  

What is the cost between 25 June and 25 September to Ms Arb of ‘carrying’ and then ‘delivering’ stock-ABC in Chicago to fulfl the conditions of her short futures position? On 25 September, Ms Arb owes the bank the initial loan of $\$100$ plus interest, which equals $\$101$ $[=\S100(1+0.04/4)=S(1+r T)]$ . By purchasing stock-ABC in the cash-market in June with borrowed money, Ms Arb can (with certainty) deliver it in 3 months’ time in Chicago on 25 September – she has created a ‘synthetic’ or ‘replication’ futures contract at a cost of $S(1+r T)=\$101$ (which accrues on 25 September).  

At maturity of Ms Arb’s (short) futures contract on 25 September, she delivers one stock and receives $F_{q}=\$102$ in Chicago. The cost of having the stock ‘in her pocket’ ready for delivery in September is $\$101$ – therefore Ms Arb makes a proft of $(102-101)=\S1$ on 25 September. This strategy is risk-free since Ms Arb knows for certain what the outcome will be on 25 September, when she makes her trades on 25 June. The reason there is a ‘cash-and-carry’ arbitrage opportunity is because the quoted futures price $F_{q}$ is greater than the correct (‘fair’) price of the futures contract $F=S(1+r T)$ that is:  

$$
F_{q}>F=S(1+r T)
$$  

Many arbitrageurs will take advantage of this risk-free proft opportunity by ‘buying low’ and ‘selling high’. Buying stock-ABC in the cash market (NYSE) and borrowing money on 25 June tends to increase $s$ and $r$ , while selling futures contracts in Chicago on 25 June will tend to depress the quoted futures price $F_{q}$ – this is just supply and demand and will tend to quickly move the quoted futures price to equal the fair futures price: $F_{q}=F=S(1+r T)$ . So the ‘correct’, ‘no arbitrage’ or ‘fair’ futures price is:  

$$
F=S(1+r T)
$$  

If the quoted futures price on 25 June had been $F=\$101$ , then there would be no risk-free arbitrage opportunities available. Above, we have implicitly assumed that all futures traders are quoting a price $F_{q}=\$102$ which makes the cash-and-carry arbitrage possible for all traders like Ms Arb. However, there is another way all traders will quickly move their quoted futures prices to equal the no-arbitrage futures price, $F=S(1+r T)$ .  

If trader-A is quoting $F_{A}=\$102$ and another trader-B is quoting the no-arbitrage price $F_{B}=\$101$ (for the September contract) then Ms Arb on 25 June will buy a September-futures from trader-B and sell a September-futures to trader-A. She has a long-short position in September-futures. On 25 September, at maturity, she takes delivery from trader-B and pays $F_{B}=\$101$ and immediately delivers the stock in Chicago to futures trader-A and receives $F_{A}=\$102$ – making a risk-free arbitrage proft of $\$1$ . It is the fact that the futures contracts mandate delivery on 25 September that makes this long-short position risk-free. In practice, when lots of Ms Arbs sell futures contracts at $F_{A}=\$102$ , supply and demand ensures that the futures price on 25 June will quickly fall to its no-arbitrage correct value of $F=S(1+r T)=\mathbb{\S}101\$ .  

We can write Equation (3.2) as:  

“Fair” Futures Price $\c=$ Spot Price $^+$ Dollar Cost of Carry \$100 \$1  

$$
F=S+D C C
$$  

where the dollar cost of carry $D C C=S r T=\S1.$ . Equivalently we have:  

“Fair” Futures Price $\c=$ Spot Price $^{1+}$ Percent Cost of Carry  

$$
F=S(1+P C C)
$$  

where the percent (proportionate) cost of carry $\begin{array}{r}{P C C=r.T=1\%}\end{array}$ . Determining the futures price using Equation (3.2) involves cash-and-carry arbitrage.  

The spot price of the stock on the NYSE will change continuously but the actions of arbitrageurs means that $F=S(1+r T)$ at all times. It is immediately apparent from Equation (3.2) that the futures price and the stock price will move closely together (if $r$ stays constant). In our case $F=(1.01)S$ and hence over a short time horizon, the change in the futures price is approximately equal to the change in the spot price: $F_{1}-F_{0}=1.01(S_{1}-S_{0})$ .  

Arbitrageurs ensure that the spot price (in New York) and the futures price (in Chicago) move together (over a short time period), almost dollar-for-dollar  

However, from Equation (3.2), if interest rates change, then $F$ and $s$ will change by slightly diferent amounts – this is a source of basis risk when hedging with futures contracts.1 If the futures contract is correctly priced (i.e. $F=\$101$ ) then it must equal the cost of creating the ‘synthetic (replication) futures’ $S(1+r T)$ – at any other quoted futures price, traders could make a risk-free (arbitrage) proft. This ‘mispricing’ cannot persist in transparent well-functioning markets with many traders looking to exploit any ‘risk-free’ trading strategies.  

Another way of looking at the no-arbitrage approach to determining the fair futures price is to note that the actual futures contract and the ‘synthetic (replication) futures’ both have the same outcome at $T_{\mathbf{\delta}}$ . Hence to prevent arbitrage opportunities, they must have the same value today. To take a long position in the actual futures contract, no ‘own funds’ are required at $t=0$ (we ignore margin payments). At maturity of the actual futures, you pay out $F=\$101$ and take delivery of one stock. To create the ‘synthetic future’ you borrow $\$100$ $@4\%$ p.a.) and purchase the stock today – hence you also use no ‘own funds’. Also, this ‘synthetic portfolio’ replicates the outcome in the actual futures contract since at $T$ , you owe the bank $\$101$ and you own (hold) one stock. The synthetic futures replicates the outcome at $T$ , for the actual futures contract. Hence to prevent arbitrage opportunities both must have the same value today, so the ‘no-arbitrage’ quoted futures price $F=S(1+r T)$ .  

# 3.1.3 Underpriced Futures Contract  

Above we showed that if $F_{q}>S(1+r T)$ this gives rise to ‘cash-and-carry’ arbitrage profts. Alternatively, when this inequality is reversed, $F_{q}<S(1+r T)$ , risk-free profts can be made by ‘reverse cash-and-carry arbitrage’. Suppose (as above) on 25 June, $S=\$100$ , $r=4\%$ p.a., $T=3$ months so the correct (‘fair’ or ‘no-arbitrage’) futures price is $F=\$101$ but the quoted futures price $F_{q}=\$99$ . Hence on 25 June the actual futures contract is underpriced, $F_{q}<S(1+r T)$ . Thus, arbitrage profts can be made by ‘selling high, buying low’.  

On 25 June, Ms Arb borrows stock-ABC from her prime broker and sells it on the NYSE – she also buys the September (3-month) futures contract. The proceeds from the short-sale of stock-ABC2 are placed in a (risk-free, 3-month term) deposit at bank-A at an interest rate r. On 25 September, cash in the deposit account has accrued to $\$101=S(1+r T)$ . Ms Arb takes delivery of stock-ABC (in Chicago) from her short futures position and pays $F_{q}=\$99$ , giving her an arbitrage proft of $\$2$ . The stock delivered in the (short) futures contract is then returned to Ms Arb’s broker.  

Hence, if the quoted futures price $F_{q}$ is either slightly above or slightly below the ‘fair’ (no-arbitrage) futures price $F=S(1+r{\dot{T}})$ , arbitrageurs will initiate simultaneous trades in the cash market (NYSE) and the futures market (Chicago), which will quickly move quoted prices on these two exchanges so that $F_{q}=S(1+r T)$ at almost every instant of time. But it is possible for (3.2) not to hold at absolutely every instant of time and providing lots of ‘Ms Arbs’ act quickly enough, they may make a small arbitrage proft – but such opportunities are likely to be very short lived and the ‘no-arbitrage’ pricing equation $F_{q}=S(1+r T)$ will be quickly restored.  

The above formulas assume $r$ is measured as a simple interest rate. If we use a discrete compound rate or a continuously compounded rate, then the ‘fair’ futures price is given by the following formulas:  

$$
\begin{array}{l}{F=S(1+r)^{T}\mathrm{~(here~}r=\mathrm{compound~interest~rate)}}\\ {F=S e^{r T}\mathrm{(here~}r=\mathrm{continuously~compounded~rate)}}\end{array}
$$  

# 3.1.4 Futures Price at Maturity  

The ‘September-futures’ matures on 25 September and will be continuously traded from 25 June (when it was initiated) and the futures price (in Chicago) changes from day-to-day (as the stock price on the NYSE changes). On 25 September $(=T)$ the maturity date of the futures contract, the quoted futures price $F_{T}$ in Chicago must equal the quoted stock price on the NYSE, $S_{T}$ – otherwise risk-free arbitrage profts can be made.  

For example, suppose the futures price in Chicago on 25 September for the ‘September futures contract’ on stock-ABC is quoted as $F_{T}=\$98$ and the stock price on the NYSE is ${{S}_{T}}=$ $\$98.3$ . An arbitrage proft can be made. Ms Arb buys the futures at $F_{T}=\$98$ on 25 September and takes immediate delivery in Chicago of one stock and pays $F_{T}=\$98$ . Ms Arb can then sell stock-ABC in the cash market (NYSE) for $S_{T}=\$98.3$ making an instantaneous risk-free proft of $\$0.3$ .  

On the maturity date of the September-futures (i.e. 25 September) unless the quoted futures price equals the stock price $(F_{T}=S_{T})$ , then risk-free arbitrage profts are possible. The actions of Ms Arb will tend to lead to a fall in stock-ABCs price on the NYSE and rise the futures price in Chicago – this is supply and demand again. Arbitrageurs will trade futures and stocks until $F_{T}=S_{T}$ , which will happen almost instantaneously on 25 September, in well-functioning liquid markets like the NYSE and the Chicago futures exchange.  

# 3.1.5 Impediments to Arbitrage  

To establish the ‘fair’ or ‘no-arbitrage’ futures price $F=S(1+r T)$ we have assumed that (a) buying and selling prices for spot market assets (e.g. stocks) are equal, and similarly for futures contracts (b) borrowing and lending rates (from the bank) are the same, (c) there are zero transactions costs (e.g. commission fees), and (d) short-selling of the underlying asset in the futures contract is always possible.  

We now relax some of the above assumptions. In practice, ‘cash-and-carry arbitrage’ involves borrowing funds at $r_{b}$ and buying the stock at the ask-price $S_{a s k}$ . If at $T$ , the total dollar transaction costs3 by Ms Arb of borrowing funds, buying the stock (at $t=0\mathrm{\dot{\Omega}}$ ) and selling the futures (at $T$ ) is $T C_{T}$ , then arbitrage is proftable if the quoted futures bid-price $F_{q}>S_{a s k}(1+r_{b}T)+T C_{T}$ . The upper bound for the no-arbitrage futures price is therefore $F_{q}\le S_{a s k}(1+r_{b}T)+T C_{T}$ .  

For ‘reverse cash-and-carry arbitrage’ Ms Arb buys the futures (at the ask-price) and short-sells the stock at the bid-price $S_{b i d}$ . If the broker takes a ‘haircut’ of $(1-z)$ then Ms Arb will place a proportion $z\left(=0.99\right)$ of the proceeds of the short-sale $(z S_{b i d})$ in a bank deposit, earning interest $r_{d}$ . At $T$ , Ms Arb has cash of $z S_{b i d}(1+r_{d}T)-T C_{T}^{*}$ , where $\boldsymbol{T}\boldsymbol{C}_{\boldsymbol{T}}^{*}$ is the (dollar) transaction costs at $T$ of placing funds on deposit, short-selling the stock and buying the futures contract. At $T_{:}$ , Ms Arb pays the quoted futures ask-price $F_{q}$ and if $F_{q}<z S_{b i d}(1+r_{d}T)-T C_{T}^{*}$ there are arbitrage profts to be made. The lower bound for the no-arbitrage futures price is therefore $F_{q}\ge z S_{b i d}(1+r_{d}T)-T C_{T}^{*}$ . Hence, when we take into account these ‘real world’ factors there is no longer a single correct forward price but the no-arbitrage forward price will lie between an upper and lower bound.  

For ‘professional traders’ operating in highly liquid markets for ‘investment assets’ such as stocks, bonds, foreign exchange and even commodities like gold and silver, the upper and lower bounds for the futures price will be ‘close to’ each other. Also, for these investment assets, short-selling the cash market asset is usually not a problem (e.g. gold or silver held as investment assets by traders, can be ‘borrowed’ by short-sellers). Also, there are always many traders who hold spot/cash market assets like gold and silver who are willing to sell from their own inventory and execute reverse cash-and-carry arbitrage. (Note that if you own gold or silver and are selling from inventory the ‘haircut’ $z=0$ , so the upper bound for the futures price is diferent to that for a genuine short-seller who has to borrow the underlying asset from her broker.) In contrast, certain spot market assets (e.g. crude oil, gas, agricultural produce) are used in the production process and for these ‘consumption assets the ease with which short-selling can be undertaken is more questionable – we deal with this below.  

# 3.1.6 Implied Repo Rate  

There is another way we can describe the arbitrage opportunities discussed above. Suppose on 25 June, the quoted futures price is $F_{q}=102\$ and $S=100$ , $r=4\%$ and $T=1/4$ year. The ‘fair’ futures price is $F=S(1+r T)=101\ \mathrm{\dot{~-}~}\mathrm{so}$ the quoted futures price is too high and arbitrage profts can be made.  

Suppose on 25 June Ms Arb sells the September futures contract at $F_{q}=102\$ and simultaneously buys stock-ABC at $S=100$ using her own funds. At maturity of the futures $T$ , Ms Arb holds stock-ABC to deliver against her short futures position and she receives $F_{q}=102$ in Chicago. The return per annum she earns (on her initial outlay of ‘own funds’ of $\$100$ ) is known as the implied repo rate:  

$$
\widehat{r}=(1/T)[(F_{q}/S)-1]=0.08\:(8\%\mathrm{p.a.})
$$  

Alternatively, if Ms Arb executes the arbitrage strategy by borrowing the $\$100$ (at $t=0$ ) in (what is called) the ‘repo market’, then the actual cost of borrowing is known as the repo rate.4 Suppose the repo cost of 3-month borrowing is $r=4\%$ p.a. then:  

If the ‘implied repo rate’ $\widehat{r}$ is greater or less than the ‘quoted repo rate’ (i.e. cost of borrowing funds, r) then a (risk-free) arbitrage trade is possible.  

If the implied repo rate $\widehat{\boldsymbol{r}}$ and actual repo rate $r$ are equal then there are no arbitrage opportunities:  

$$
\widehat{r}=(1/T)[(F_{q}/S)-1]=r,\mathrm{~which\implies\}F_{q}=S(1+r T)
$$  

So comparing the implied repo rate with the actual repo rate is just a diferent way of seeing whether the quoted futures price $F_{q}$ is higher or lower than the fair futures price $F=S(1+r T)$ and if so, then proftable arbitrage opportunities are possible.  

# 3.2 DIVIDENDS, STORAGE COSTS, AND CONVENIENCE YIELD  

In practice, many futures contracts are not as straightforward as the one described above. For example, a stock might pay dividends (over the life of the futures contract). We frst consider the case of discrete dividend payments. Suppose (again) on 25 June, $S=100$ , $r=4\%$ p.a., and the September-futures contract has a maturity of $T=1/4$ year (3 months) but is written on a dividend paying stock-ABC, which pays $a$ known dividend of $D_{1}=\$1$ in one month’s time, on 25 July (Figure 3.2). We also assume (for simplicity of exposition) that the yield curve is fat, so that $r=4\%$ p.a. for borrowing or lending money at any horizon (e.g. over 1 month, 2 months, etc.).  

Consider implementing cash-and-carry arbitrage. For example, on 25 June, Ms Arb borrows cash, buys stock-ABC and holds the stock for 3 months. This is the ‘synthetic future’. The actual quoted price for the September-futures must equal the cost of creating this ‘synthetic future’ (on stock-ABC) – if there are to be no arbitrage profts possible. We repeat our initial example (see above) but in this case Ms Arb borrows funds from the bank over two diferent time horizons: using 1-month and 3-month interest rates (which are both $4\%$ p.a.).  

![](27fb3bc8c28ac28db5bcc9ebb4f95d39224e5eaf88e8bdb350619c506c53e8b6.jpg)  
FIGURE 3.2 Futures price on dividend paying stock  

There is a single known dividend payment after 1 month (1/12th year) of $D_{1}=\$1$ , on 25 July. We have a fat yield curve with $r=4\%$ p.a. so the present value of this future dividend payment is $P V(D_{1})=\S1/\left[\left(1+0.04(1/12)\right]=\S0.9967.$ Hence Ms Arb can borrow $\$0.9967$ on 25 June from bank-A at the one-month interest rate and know that she can pay back the $\$1$ (owed to bank-A) from the (known) dividend payment on stock-ABC, on 25 July. For Ms Arb there are zero net cash fows on 25 July – the dividend received on the stock will be used to pay of the bank loan outstanding of $\$1$ .  

Therefore in order to purchase the stock at a price of $S=\$100$ , Ms Arb only needs to borrow an additional $S-P V(D_{1})=\S99.0033$ on 25 June from bank-A. For this second loan she borrows at the 3-month rate, so that repayment of this loan coincides with the maturity date of the futures contract. In 3 months’ time (on 25 September) Ms Arb will owe bank-A, $\$99.9933,[=\S99.0033(1+0.04/4)]$ . But 25 September is also the maturity date of the actual futures contract and from our earlier discussion we know that the correct (‘fair’, ‘no-arbitrage’) futures price $F$ must equal the cost of creating the synthetic futures hence:  

$$
F=[S-P V(D_{1})](1+r T)=\S99.9933
$$  

Notice that all the borrowed funds, $\$0.9967+\S99.0033$ are used to purchase the stock for $\$100$ , in order to execute the arbitrage strategy. The ‘frst’ $\$0.9967$ Ms Arb borrows means she owes $\$1$ after $^{1}$ month – but this debt is paid of with the $\$1$ dividend payout on 25 July from stock-ABC that Ms Arb holds. The net cost of the cash-and-carry arbitrage is the $\$99.9933$ owed to the bank after 3 months – and this is the correct (no-arbitrage) price for the September-futures contract, quoted on 25 June.  

# 3.2.1 Several Discrete Dividend Payments  

Suppose there are $N$ dividend payments of diferent dollar amounts $D_{i}$ on the stock, between today and the maturity date of the futures contract, that are payable at discrete times $t_{i}$ (from  

today). Then the correct (no-arbitrage) futures price is:  

$$
F=[S-P V(D)](1+r T)
$$  

where $\begin{array}{r}{P V(D)=\sum_{i=1}^{N}D_{i}/(1+r_{i}t_{i})}\end{array}$ , $r_{i}=$ spot interest rates (simple rate) between today and $t_{i}$ and $r=$ interest rate with maturity $T$ (when the futures contract matures).  

# 3.2.2 Bond Futures  

In principle, the above formula can also be applied to pricing a futures contract on a coupon paying T-bond. The futures price is $F=[S-P V(\mathbf{C})](1+r T)$ where $s$ is the current cash-market price of the underlying (deliverable) bond, $P V(\mathrm{C})$ is the present value of the coupon payments on the underlying bond over the life of the futures contract, $T$ is the maturity of the futures and $r$ is the risk-free rate for maturity $T$ . This formula ignores several ‘real world’ complications (e.g. accrued interest) which are discussed in Chapter 13.  

# 3.2.3 Continuous Dividend Payments  

Suppose stocks pay out dividends (evenly) at a rate of $\delta=2\%$ p.a. Then in the above arbitrage example, when Ms Arb buys the stock for $\$100$ , some of the borrowed money can be paid back from the receipts of future dividends – this reduces the ‘cost of carry’. If the rate at which dividends are paid is $\delta=2\%$ p.a. then over 3 months Ms Arb receives $\$0.5$ in dividends $(=\S100\times0.02\times\:^{1}/_{4}=S\delta T)$ which reduces the overall cost of carry. So the correct (no-arbitrage) futures price is:  

$$
F=S\ \left[1+(r-\delta)T\right]
$$  

When using compound and continuously compounded interest rates the formulas are:  

$$
\begin{array}{r l}&{\boldsymbol{F}=S(1+r-\delta)^{T}\mathrm{\ensuremath{\mathrm{\(compoundrates)}}}}\\ &{\boldsymbol{F}=S e^{(r-\delta)T}\mathrm{\ensuremath{\mathrm{\(continuouslycompoundedrates)}}}}\end{array}
$$  

Using Equations (3.6a)–(3.6c), the quoted futures price (in Chicago) on 25 June (say) will be above the quoted stock price (on the NYSE), if $r>\delta$ and below the quoted stock price if $r<\delta$ . These two cases are referred to as:  

Often backwardation is also referred to as an inverted market. Contango and backwardation are also used in a slightly diferent way, to describe a whole series of futures prices for contracts with diferent maturity dates (but on the same underlying asset). This is the term structure of futures prices – which can be represented graphically. For example, the futures market is said to be in contango (on 25 June, say) if the quoted futures prices increase with the maturity dates of the contracts – $(F^{T=5}>F^{T=4}>F^{T=3}>F^{T=1}>S)$ , so prices of ‘far dated’ futures contracts are higher than those of ‘near dated’ contracts.  

# 3.3 COMMODITY FUTURES  

Let’s consider the determination of the correct (no-arbitrage) future prices on commodities such as grains and oilseed (e.g. wheat, soybeans, sunfower oil), or food (e.g. cocoa, orange juice), or metals and petroleum (e.g. gold, silver, platinum, heating oil), or livestock and meat (hogs, live cattle, pork bellies), which are actively traded on various exchanges around the world – for example, New York Cotton Exchange (NYCE), Kansas City Board of Trade (KCBT), Mid America Commodity Exchange (MCE), New York Mercantile Exchange (NYMEX) and London Metals Exchange (LME).  

When discussing futures prices we split commodities into two main types. Investment commodities include precious metals such as gold, silver, platinum and copper which are widely held as investment assets (as well as being used in the production of other goods). Production commodities are primarily held as inputs to the production process to provide consumer goods (e.g. agricultural and energy commodities) and are not usually held for investment purposes.  

# 3.3.1 Investment Commodities  

Investment commodities can be priced using ‘cash-and-carry’ arbitrage, if we take account of storage costs. If to undertake cash-and-carry arbitrage you purchase gold in the cash market (using borrowed money), then you have to store and insure the gold until the maturity date of the futures contract. You have storage costs on top of the existing interest cost on your borrowed money, so the futures price for gold is given by5:  

$$
F=S[1+(r+s)T]
$$  

where $s=$ storage cost of gold (per annum). This equation will hold at all points in time since arbitrage strategies including those which require short-selling the spot asset (gold, silver) will always be possible, because many holders of such investment assets do not have an alternative use for them (e.g. they are not jewellery manufacturers). Arbitrage involving purchases of these spot investment assets clearly poses no problems in liquid markets. Equation (3.7) indicates that at any time, the current quoted futures price $F$ for gold (in Chicago) will always be above the spot price $s$ for gold (quoted in New York, say).  

# 3.3.2 Production Commodities  

One might think that a futures contract on a ‘production commodity’ like oil would be determined by Equation (3.7), which implies the oil futures price (in Chicago in USD) would always be above the spot price for oil (quoted in USD in Texas, say). But for many production commodities such as oil, at certain times it is observed that the quoted futures price is actually below the spot price, (i.e. $F<S$ ) – we then say that oil futures are in backwardation. This outcome is rationalised by adapting Equation (3.7) and introducing a concept known as the convenience yield $y$ , for oil. How does this come about?  

The convenience yield arises because the holder (Exxon) of a spot commodity (e.g. barrels of crude oil) has the added advantage that they can supply his local customers (in Texas) if the oil goes into short supply (e.g. during abnormally cold winter months) and hence retain customer loyalty. This ‘convenient’ state of afairs has an intrinsic value for the holder of oil, which is referred to as the convenience yield.  

The presence of a convenience yield might therefore prevent cash-and-carry arbitrage operating and this invalidates Equation (3.7). For example, suppose the current spot price of oil (quoted in Texas) is high – an indication that oil is currently in short supply (i.e. low levels of oil stored on-shore in Texas). Ms Arb wants to undertake an arbitrage strategy which requires her to short-sell spot oil at $s$ ( $\mathfrak{P}$ per barrel) and simultaneously buy futures contracts on oil at $F$ ( $\mathfrak{P}$ per barrel). Short-selling means Ms Arb has to borrow oil from a holder of oil (Exxon) – which is being stored in onshore oil containers (or maybe sitting in the hold of a tanker in the middle of the ocean). Short-selling may not be possible in practice if Exxon is unwilling to ‘loan out’ their oil inventory.  

To make a risk-free proft Ms Arb has to borrow barrels of oil today and quickly sell them in the spot market (in Texas) and immediately invest the proceeds in a risk-free deposit account. When her long futures contract matures she pays F and takes delivery of oil in the futures contract and ‘returns’ the ‘borrowed oil’ to Exxon. But if holders of spot oil (Exxon) will not provide spot oil to Ms Arb (at the required geographical destination) then arbitrage involving short-selling of oil becomes impossible.  

Hence at these times Equation (3.7) will not hold for quoted futures prices on oil and $F\neq S$ $[1+(r+s)T]$ based on historical data. But (daily) historical data on $F,S,r,s$ and $T$ are available. We therefore introduce an ‘unknown variable’, the convenience yield $y$ , to force an equality, so that:  

$$
F=S[1+(r+s-y)T]
$$  

We do this by taking quoted (daily) prices from the historical data, on $F,S,r,s$ and $T$ we derive (‘back out’) the historical ‘convenience yield’ (p.a.) which is given by:  

$$
y=r+s-{\frac{1}{T}}\left({\frac{F-S}{S}}\right)
$$  

Using calculated daily values for $y$ using (3.8b) it must be the case that for the historical data the equality in (3.8a) holds. The right-hand side of Equation (3.8a) now provides the determinants of the historical oil futures price, $F$ . This provides a way of trying to determine what will happen to the futures price for oil over the coming days and months. If today, we know what the convenience yield $y$ of holding a spot barrel of oil (over say the next 3 months) is likely to be, then we could use (3.8a) to price a 3-month futures contract. The historical time series for $y$ can be used to try and forecast what $y$ might be over the next 3 months. But clearly this is a forecast and could be very inaccurate. However, the market will today set a futures price, which will embody traders’ best estimate of the future convenience yield.  

If the convenience yield remains constant then changes in the oil futures price (over the next 3 months) will be closely linked to changes in the spot price of oil. But the convenience yield of oil could itself change dramatically over the next 3 months, as supply and demand for oil in the production process and by consumers, as well as inventories of spot oil, change. Hence there is therefore not such a close link between changes in spot and futures prices for ‘production commodities’ as there is for futures contracts on other ‘investment’ assets (e.g. stocks, stock indices, currencies, bonds, gold) – so $F$ and $s$ may not move approximately dollar-for-dollar because of changes in y. This makes hedging ‘production commodities’ more di\$cult – the technical way of saying this is that ‘basis risk’ is high for commodity futures where the underlying asset is a ‘production commodity’. We will consider these issues further in the chapter on energy derivatives.  

# 3.3.3 Continuous and Discrete Compounded Rates  

The above formulas for futures prices using simple rates, compounded rates, and continuously compounded interest rates, look slightly diferent. However, they all give exactly the same value for F. This is easily verifed by recalling the relationship between the various defnitions. Let $r_{s}=$ simple rate, $r=$ discrete compound rate and $r_{c}=$ continuously compounded rate – all expressed ‘per annum’ (decimal). If $\$1$ is invested today, we require that this will result in the same amount at the end of, say, 3 months (i.e. $T={\sqrt[1]{4}}.$ ), regardless of which interest rate convention is used. Therefore the interest rate conventions are defned so that:  

$$
1+r_{s}T=(1+r)^{T}=e^{r_{c}.T}
$$  

For a futures contract on (a non-dividend paying) stock we have $F=S(1+r_{s}T)$ – but using (3.9) this is equivalent to $F=S(1+r)^{T}$ and $\bar{\boldsymbol{F}}=\bar{S e}^{r_{c}T}$ – hence the alternative formulas give the same value for $F$ . It is also true that all three formulas would give approximately the same answer for $F$ even if we used the ‘incorrect’ interest rate in each formula. This is because for ‘small’ values of $r$ , the following approximations are quite accurate:  

$$
e^{r.T}\approx1+r T\quad\mathrm{and}\quad(1+r)^{T}\approx1+r T
$$  

Finally note that if:  

$$
\begin{array}{r}{F=S e^{r_{c}T}\quad\mathrm{then}\quad S=F e^{-r_{c}T}}\end{array}
$$  

# 3.3.4 Non-storable Commodities  

How can we price a forward/futures contract on a non-storable commodity like electricity and what about any seasonality in the spot prices of commodities such as an agricultural product like wheat? The spot price of wheat tends to rise just before the harvest, usually around August and then falls as the wheat supply comes onto the (spot/cash) market. Seasonality in the spot price will be refected in seasonality in the futures price because arbitrage is possible within the year, using inventories of wheat. The convenience yield of wheat just before the harvest is likely to be high and just after the harvest, when inventories of wheat are large, the convenience yield is likely to be low. We can use Equation (3.8a) to determine the futures price providing we can obtain an estimate of the market’s view of the future availability of the commodity, which infuences the convenience yield. We can ‘back out’ the historical time series of the convenience yield using (3.8b) and then use statistical forecasting methods, to forecast the convenience yield (over the life of the futures contract).  

Instead of trying to estimate the convenience yield, a diferent approach to determine today’s futures price involves trying to forecast the future spot price of a commodity. Suppose it is 1 May and we wish to determine today’s futures price $F_{0}$ for delivery of wheat in 6 months’ time on 1 November $\left\langle T={}^{1}/_{2}\right.$ year). Suppose the expected spot price of wheat (per bushel) for November is $E S_{T}$ and the riskiness of wheat prices means that investors require a (simple) return of $R$ p.a. to speculate on the future spot price of wheat. If the futures price quoted today for delivery and payment of wheat in 6 months is $F_{0}$ , then a speculator could borrow cash equal to $F_{0}/(1+r T)$ and take a long position in the futures contract. Hence, at $T$ the speculator has funds available to take delivery of wheat in the futures contract. Suppose the speculator believes that the expected price of wheat in 6 months’ time is $E S_{T}$ which has a present value of $E S_{T}/(1+R.T)$ . If we equate the present value of payment for the wheat delivered in the futures contract with the present value of supplying spot-wheat in 6 months’ time, we have:  

$$
F_{0}/(1+r T)=E S_{T}/(1+R.T)
$$  

and  

$$
F_{0}=E S_{T}[(1+r T)/(1+R.T)]
$$  

So today’s futures quote depends on the expected spot price of wheat, which itself is infuenced by forecasts of supply and demand for wheat in 6 months’ time – this can lead to seasonality in spot and futures prices. Where possibilities for arbitrage are limited then the close link between spot and futures prices is broken and successful hedging becomes more di\$cult. Note also that the above approach implies that the forward price is not an unbiased forecast of the expected future spot price – unless the required return on the underlying asset $R$ , equals the risk-free rate, r. (This can be shown to be the case using the Capital Asset Pricing Model [CAPM], when the underlying asset and the ‘market return’ are uncorrelated and hence the asset-beta is zero.)  

# 3.4 VALUE OF A FORWARD CONTRACT  

In this section we explicitly deal with forward contracts rather than futures contracts. Because a futures contract is marked-to-market daily and cash is credited or debited to the margin account, a futures contract has a value of zero at the end of each trading day.  

But when dealing with forward contracts it is important to distinguish between price and value. Suppose that on 25 January $(t=0)$ ) you initiate (go long) a 6-month forward contract 1 $\left\langle T={}^{1}/_{2}\right.$ year) on a stock, at a forward price $F_{0}=\$90$ . At $t=0$ no cash changes hands. The maturity date of the contract is 25 July. On 25 January you have agreed to exchange the underlying assets (stocks) in exchange for a cash payment of $F_{0}=\$90$ on 25 July.  

At any future date (e.g. $t=\mathrm{April})$ during the life of the forward contract, you can enter into a ‘new’ forward contract with the same delivery date, 25 July, as the initial forward contract. The forward price $F_{t}$ for a ‘new’ forward contract entered into on 25 April (with delivery date, 25 July) will be diferent from the price of the ‘old’ forward contract $F_{0}=\$90$ initiated on 25 January (because of changes in the stock price between 25 January and 25 April). The question we wish to answer is: what determines the value of the ‘old’ forward contract (initiated on 25 January) each day, as this contract approaches its maturity date of 25 July?  

# 3.4.1 Value When Initiated  

Suppose at the initiation of the forward contract on 25 January the forward price is $F_{0}=$ $S_{0}(1+r T)=\S90$ . However, the value of the long forward contract is zero, since no arbitrage opportunities exist and no cash changes hands.  

At the initiation of a forward contract, the value of the contract is zero.  

# 3.4.2 Value at Maturity  

Clearly the price of a forward contract on its maturity date must equal the spot price: $F_{T}=S_{T}$ . If $F_{T}\neq S_{T}$ it would be possible to make arbitrage profts. For example, if $F_{T}=\$90$ and ${{S}_{T}}=$ $\$100$ you could buy a long forward contract, take delivery of the underlying (stock) immediately and pay $\$90$ . You could then immediately sell the underlying (stock) in the spot market (NYSE) for $\$100$ and pocket the diference of $\$10$ . The deal is virtually risk-free. Hence arbitrage will ensure that $F_{T}=S_{T}$ on the maturity date of the forward contract.  

Now consider the value of a long position in $a$ forward contract at maturity. If the forward contract was initially entered into on 25 January at a price $F_{0}=\$90$ , then at maturity $T$ (25 July), the value of this ‘old’ (maturing) forward contract is the proft you could make at $T$ , hence:  

VT Value of long position in ‘ ’ forward contract maturit $\mathrm{\Omega}^{\prime}=S_{T}-F_{0}$  

If you are long the ‘old’ forward contract at an initial forward price (agreed on 25 January) of $F_{0}=\$90$ , then at $T$ (on 25 September) you can take delivery of the underlying stock in the forward contract, pay $F_{0}=\$90$ and immediately sell the underlying for $S_{T}$ in the cash market. If $S_{T}>F_{0}$ the long position in the forward contract has a positive value (and vice versa).  

# 3.4.3 Value of Forward Contract Prior to Expiration  

Suppose on 25 January $(t=0)$ a 6-month forward contract (on a non-dividend paying stock) with maturity on 25 July is purchased at a forward price $F_{0}=\$90$ . Sometime later on 25 April, the forward price $F_{t}$ for a ‘new’ forward contract (with the same maturity date, 25 July) has only 3 months to maturity $(T-t=0.25)$ (see Figure 3.3) and if $S_{t}=\S100$ and $r=0.05$ (continuously compounded), then the price of this ‘new’ forward contract on 25 April is:  

$$
F_{t}=S_{t}e^{r(T-t)}=\mathbb{\S}100\mathrm{e}^{0.05(0.25)}=\mathbb{\S}101.2578
$$  

The question we wish to answer is: what is the value $V_{t}$ on 25 April, of the original ‘old’ forward contract?  

On 25 January, an investor Ms Player initiated her long position in the ‘old’ contract at a forward price of $F_{0}=\$90$ . On 25 April, Ms Player could short the ‘new’ contract (with the same maturity date of 25 July) at a forward price $F_{t}=\$101.2578$ . Then at maturity of both contracts on 25 July Ms Player can (a) take delivery of the stock from her long position in the ‘old’ forward contract by paying $F_{0}=\$90$ , and (b) then deliver this stock to fulfl her obligations in the ‘new’ short forward contract and receive $F_{t}=\$101.2578$ in cash on 25 July. This cash proft at time $T(25\mathrm{{July})}$ is $F_{t}-F_{0}$ and is risk-free, because at $t=25$ April she knows what this proft will be. The value of the old contract at time $t=25$ April must therefore equal the present value of $F_{t}-F_{0}$ over the remaining period $T-t$ :  

$$
\begin{array}{r}{V_{t}(\mathrm{`Old'forwardcontract})=P V[\mathrm{`New'forwardprice\at\}t-\mathrm{`Old}}\\ {=[F_{t}-F_{0}]e^{-r(T-t)}=S_{t}-F_{0}e^{-r(T-t)}}\end{array}
$$  

![](fcad115f828448b0b0dd7387bab3d6c2aa227f2372d29d2ccb845b6f04a0085e.jpg)  
FIGURE 3.3 Value of forward contract  

where we have used $F_{t}=S_{t}e^{r(T-t)}$ . The above expression for the value of the ‘old’ contract follows from arbitrage arguments.  

Ms Player purchased the ‘old’ July-forward contract on 25 January at a forward price $F_{0}=\$90$ and on 25 April she shorts a new July-forward contract at $F_{1}=\$101.2578$ . Shorting the ‘new’ contract on 25 April will yield receipts of $F_{1}=\$101.2578$ on 25 July and the ‘old’ contract requires a payment of $F_{0}=\$90$ on 25 July. Hence the proft on 25 July is $\$11.2578[=\S101.2578-\S90]$ . Since this strategy is risk-free, another investor would be prepared to pay Ms Player $V_{t}={\tt811.118}[={\tt811.2578}\mathrm{e}^{-0.05(0.25)}]$ on 25 April, for the ‘old’ forward contract (which was initially negotiated on 25 January). Otherwise, arbitrage profts can be made.6  

Value of an ‘old’ forward contract at any time prior to maturity  

$$
V_{t}=\left[F_{t}-F_{0}\right]e^{-r(T-t)}=S_{t}-F_{0}e^{-r(T-t)}
$$  

The ‘mark-to-market’ value of the long forward contract on 25 April is $V_{t}=\mathbb{\$11.118}$ . If JPMorgan had initially sold this contract it would have to pay the person holding the long position $\$11.118$ on 25 April, to nullify the contract.  

# 3.4.4 Replication Portfolio  

The value of the ‘old’ forward contract can also be determined by creating a ‘replication portfolio’ at $t=25$ April. Suppose on 25 April you purchase the stock for $S_{t}$ and also borrow a cash amount of $F_{0}e^{-r(T-t)}$ from the bank at interest rate, $r-$ this is the replication portfolio which will mimic the outcome of the ‘old’ forward contract at maturity, $T_{\mathbf{\delta}}$ .  

The amount you owe the bank on 25 July is $F_{0}$ . The net cost (i.e. ‘own funds’) to initiate this replication strategy at $t=25$ April is $S_{t}-F_{0}e^{-r(T-t)}$ . At $T$ you have one stock worth $S_{T}$ and you owe the bank $F_{0}$ . But the latter outcome from the replication portfolio at $T$ is exactly the same as if you were long a forward contract (which matures at $T$ ) with forward price of $F_{0}$ . We have therefore ‘replicated’ the outcome at $T$ , for a forward contract with a forward price of $F_{0}$ . The cost of setting up this ‘replication portfolio’ at $t=25$ April is $S_{t}-F_{0}e^{-r(T-t)}$ . At $t$ , the value of the ‘old’ forward contract must equal the cost of setting up the replication portfolio (otherwise arbitrage profts can be made) hence, $V_{t}=S_{t}-F_{0}e^{-r\bar{(T-t)}}$ .  

Note that if we use compound interest rates or simple interest (rather than continuously compounded rates), the value of a forward contract (if the underlying asset has no cash fows) is:  

$$
V_{t}={\frac{F_{t}-F_{0}}{(1+r)^{T-t}}}=S_{t}-{\frac{F_{0}}{(1+r)^{T-t}}}
$$  

or  

$$
V_{t}={\frac{F_{t}-F_{o}}{[1+r(T-t)]}}=S_{t}-{\frac{F_{o}}{[1+r(T-t)]}}\quad({\mathrm{simple~rates}})
$$  

# 3.4.5 Underlying Asset Has a Cash Inflow  

For a forward contract on a dividend paying stock, which matures on 25 July, the ‘new’ forward contract (initiated on 25 April) has a forward price:  

$$
F_{t}=S_{t}e^{(r-\delta)(T-t)}
$$  

where $\delta$ is the (continuously compounded) dividend yield. On 25 April, the value of an ‘old’ forward contract (initiated on 25 January, with maturity date 25 July) which pays dividends on the underlying stock is:  

$$
V_{t}=\left[F_{1}-F_{0}\right]e^{-r(T-t)}=S_{t}e^{-\delta(T-t)}-F_{0}e^{-r(T-t)}
$$  

At inception, a forward contract has a value of zero which is consistent with the above equation – set $t=0$ and note that at inception $F_{0}=S_{0}e^{(r-\delta)T}$ so we obtain $V_{0}=0$ . At maturity $t=T$ and (3.15) implies $V_{T}=S_{T}-F_{0}$ , which is consistent with the value of the forward contract at maturity, as we found earlier. Note that at $t>0$ the value of the forward contract $V_{t}$ can be either positive or negative.7  

Note also that $\delta$ could represent any (continuous) cash infows from the underlying asset. For a forward contract on a commodity (e.g. oil), $\delta=$ convenience yield less the storage cost $(=y-s)$ . For a forward contract on foreign currency, $\delta=$ risk-free interest rate on foreign bank deposits and $r=\mathrm{risk}$ -free rate on domestic deposits.  

If the net cash infows on the underlying asset are discrete then the value of the ‘old’ forward contract at $t$ is  

$$
V_{t}=S_{t}-P V\left(n e t c a s h i n f l o w s\right)-F_{0}e^{-r(T-t)}
$$  

where $P V$ is the present value of any (dollar) net cash infows between today $t$ and the maturity date of the forward contract, $T.$ . The net cash infows could be ‘dollar dividends’ on a stock, or receipts of coupons on a bond, or for commodities the ‘dollar’ convenience yield less storage costs.  

# 3.5 SUMMARY  

• Risk-free arbitrage ensures that the correct/fair forward price is determined by the cost of a synthetic or replication portfolio which produces the same outcomes as the forward contract itself – this is cash-and-carry arbitrage. For the simplest forward contract on an underlying asset $s$ (which pays no cash fows) we have: $F=S(1+r T)$ .   
• We assume that futures prices are determined by arbitrage in the same way as forward prices – this is usually a good working assumption because margin payments on futures contracts do not have a major impact on the above relationship.   
• If the quoted futures price does not equal the ‘correct’ (no-arbitrage) futures price determined by the cost-of-carry model, then risk-free arbitrage profts can be made.   
• Cash-and-carry arbitrage ensures that the futures price on a stock (traded in Chicago) moves almost dollar-for-dollar with the spot (cash-market) price of the stock (on the NYSE), over small time intervals.   
• Cash-and-carry arbitrage can be used to determine the correct (no-arbitrage) futures price where the underlying assets involve intermediate cash fows (e.g. futures contract on dividend paying stocks and stock indices) and that involve storage costs (e.g. silver, gold).   
• Futures contracts on commodities that are also used in the production of consumer goods (e.g. oil, gas, wheat, live cattle) are more di\$cult to price by cash-and-carry arbitrage because the futures price depends on the ‘convenience yield’ which is di\$cult to forecast.   
• The futures price may not move exactly in line with the (underlying) spot price if interest rates, dividends, storage costs or the convenience yield change in unpredictable ways – and the convenience yield is the most unpredictable element.   
• The forward price (on a non-dividend paying stock) with maturity in $T$ years is $F_{0}=S_{0}e^{r T}$ determined today $(t~=~0)$ . After initiation, the value of this forward contract changes over time and at time $t>0$ the value of the forward contract is: $V_{t}=\left[F_{t}-F_{0}\right]\bar{e}^{-r(T-t)}=S_{t}-F_{0}e^{-r(T-t)}$ . Hence $V_{t}$ varies with the spot price $S_{t}$ , interest rate and time to maturity.   
• On the other hand, the value of $a$ futures contract at the end of each day is zero, since the contract is marked-to-market and the margin account is credited or debited daily.  

# EXERCISES  

# Question 1  

How do futures contracts provide ‘leverage’?  

# Question 2  

For a futures contract on a (non-dividend paying) stock, carefully explain how you can make an arbitrage proft if the quoted futures price $F_{q}$ is less than the ‘fair’ (or ‘synthetic’) futures price.  

# Question 3  

For a futures contract on a dividend paying stock, with a single dividend payment $D$ before maturity of the futures, carefully explain how you can make an arbitrage proft if the quoted futures price $F_{q}$ is above the ‘fair’ (or ‘no-arbitrage’ or ‘synthetic’) futures price.  

# Question 4  

What is the ‘convenience yield’ and how does it complicate arbitrage between the spot and futures markets?  

# Question 5  

The stock price is currently at $S=400$ , and the quoted futures price on a $T=4$ -month contract is $F_{q}=405$ , $r=10\%$ p.a. and the dividend yield is $4\%$ p.a. (both continuously compounded). How could you make an arbitrage proft?  

# Question 6  

The spot price of an asset is $S_{0}$ , the futures price today for delivery or settlement at period $T$ in the future is $F_{0}$ , the risk-free rate over the period from $t=0$ to $t=T$ is $r$ (simple rate). Explain the relationship that must hold between $S_{0},F_{0}$ , and $r$ .  

Now suppose the asset pays a known income stream $c$ over the period, the present value of which is $P V(C)$ . Explain the relationship that must hold between $S_{0},F_{0},P V(C)$ and $r$ .  