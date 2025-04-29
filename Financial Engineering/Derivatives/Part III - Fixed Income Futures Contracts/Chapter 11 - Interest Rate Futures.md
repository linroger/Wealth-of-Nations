---
tags:
  - eurodollar_futures
  - futures_contracts
  - hedging
  - interest_rate_futures
  - libor
  - t_bill_futures
aliases:
  - 3-month Eurodollar
  - 3-month Sterling
  - IRF
  - US T-bills
key_concepts:
  - arbitrage strategies
  - contract specifications
  - implied repo rate
  - price quotes
  - settlement procedures
---
# FIXED INCOME FUTURES CONTRACTS  

# Interest Rate Futures  

# Aims  

• To discuss contract specifcations, settlement procedures and price quotes for futures contracts on 3-month Sterling deposits, 3-month Eurodollar deposits and US T-bills.   
• To show how interest rate futures contracts are priced.   
• To examine arbitrage strategies using the implied repo rate on T-bill futures.   
• To examine speculation and spread trades using interest rate futures.  

Interest rate futures (IRF) became of increasing importance in the late 1970s and early 1980s when the volatility of interest rates increased dramatically. This was because of high infation and consequent attempts by Central Banks to control the money supply and exchange rates by altering interest rates. Corporates have bank loans and bank deposits based on foating (LIBOR) interest rates and many fnancial institutions hold short-term fxed income assets (e.g. T-bills, Commercial bills). Interest rate futures contracts are used to hedge risks due to changes in interest rates (yields) which afect the market value of ‘interest sensitive’ cash market assets held by corporates, mutual funds, hedge funds and pension funds.  

In the US, Eurodollar futures (CME/IMM) are one of the most actively traded contracts – much more so than EuroYen and US T-bill futures. The contract specifcation for 3-month Sterling futures (on Euronext), Eurodollar futures (CME/IMM) and US T-bill futures are given in Table 11.1.  

Derivatives:TheoryandPractice, First Edition. Keith Cuthbertson, Dirk Nitzsche and Niall O’Sullivan. $\circledcirc$ 2020 John Wiley & Sons Ltd. Published 2020 by John Wiley & Sons, Ltd.  

TABLE 11.1 Contract specifcations   


<html><body><table><tr><td></td><td>Sterling 3-month (NYSE-Euronext, London)</td><td>90 day Eurodollar Futures US T-bill futures (CME-Group, Chicago)</td><td></td></tr><tr><td>Contract size</td><td>500,000</td><td>$1m</td><td>$1m</td></tr><tr><td></td><td>Delivery months March/ June/ September/ December</td><td>March/ June/ September/ December</td><td>March/ June/ September/ December</td></tr><tr><td>Quotation</td><td>Futures Price F = (100 - forward rate)</td><td>IMM index = 100 － futures discount rate</td><td>IMM index = 100 － futures discount rate</td></tr><tr><td>Tick size (value)</td><td>0.01 (12.50)</td><td>1 bp ($25)</td><td>1 bp ($25)</td></tr><tr><td>Settlement</td><td>Cash settled</td><td>Cash settled</td><td>Delivery of 90-92 day T-bill</td></tr></table></body></html>

Notes: Margin requirements are set by the exchange. They are higher for speculators than for hedgers and spread traders. bp $\mathbf{\sigma}=\mathbf{\sigma}$ basis point.  

# 11.1 THREE-MONTH EURODOLLAR FUTURES CONTRACT  

The underlying asset in the 3-month Eurodollar futures contract is a deposit which pays the (90-day) LIBOR (Eurodollar) rate.1 The ‘contract size’ is for ‘notional delivery’ of a $\$10$ , 90-day deposit. Because Eurodollar deposits are non-transferable, the futures contract is settled in cash based on the contract size of $\$10$ .  

Contracts are available which mature (towards the end of) March, June, September, and December of each year. These maturity dates extend out for over 10 years – because Eurodollar futures are widely used to hedge either the foating interest rate cash fows on long-term bank loans or deposits and also to hedge the net positions of interest rate swap dealers.  

Suppose on 15 April $(t=0)$ we buy the June-Eurodollar futures contract, which matures on 28 June (Figure 11.1). The quoted ‘price’ on 15 April is not really a ‘dollar price’ but is an index known as the IMM-(June) index – it is linked to the forward discount rate $d_{f}=8\%$ p.a., which applies to the 90-day period between 28 June and 26 September. The forward discount rate is measured on an ‘actual/360’ day count convention. The relation between the IMM-index and the forward discount rate is:  

$$
I M M_{0}=100-d_{f}=92
$$  

The next issue to consider is the tick size and tick value. The ‘tick size’ for the Eurodollar future contract is 1 basis point (bp; i.e. $0.01\%$ p.a.). If the discount rate changes by 1 basis  

![](88311e7a12ccf39b029b047351a598b0a47bb240447e7c1f0f32b674cc9fc4ff.jpg)  
FIGURE 11.1 June Eurodollar futures contract  

point, so does the IMM-index (see Equation 11.1), and the dollar value of one (90-day) futures contract with a contract size of $\$10$ changes by $\$25$ (‘the tick size’):  

$$
\mathrm{Tick\:value}=\S1\mathrm{m}\times(0.01/100)\times(90/360)=\S25
$$  

The reason the IMM-Index appears in the Wall Street Journal and on trading screens is that it allows dealers in Eurodollar futures to quickly assess their gains and losses by using the tick size and tick value.  

A 1 bp change in the IMM index (or the futures discount rate $d_{f}$ ) corresponds to a $\$25$ change in the value of one Eurodollar futures contract.  

The dollar payof is linear and hence independent of the initial futures discount rate – a change from $3\%$ to $3.01\%$ or from $6\%$ to $6.01\%$ will both lead to a change in the value of one Eurodollar futures contract of $\$25$ . Similarly, a change in the futures discount rate of 5 bps implies a change in the value of one Eurodollar futures contract of $\$125$ . Also, note that a change of 1 bp (over 1 day say) in the IMM-index for Eurodollar futures contracts of any maturity (e.g. the June-contract, September-contract, etc.) will result in the same $\$25$ change (over 1 day) in the value of both the June-contract and the September-contract.  

Although dealers mainly use the IMM-index quote (e.g. $\mathrm{IMM}=92\$ ) when analysing Eurodollar futures, there is also (somewhat confusingly) a genuine ‘futures price’ (in dollars) – which is useful when linking the futures price to the futures yield (see below). Given the IMM-index the Eurodollar futures price is given by:  

$$
\begin{array}{c}{F_{0}=100-(100-I M M_{0})(90/360)}\\ {=100[1-(d_{f}/100)(90/360)]=\S98}\end{array}
$$  

When discussing hedging using the Eurodollar futures contract we can either calculate the gains and losses on the futures position using the change in the IMM-index, (with each  

1 bp change being worth $\$25$ ) or we can calculate the gains and losses using the futures price $F$ (see below) – both will give the same answer.  

The contract size for the Eurodollar futures is for a ‘notional’ delivery of a $\$10$ , 90-day deposit and therefore the ‘value of one futures contract’ (or ‘invoice price’ or ‘contract price’)3 is:  

$$
V_{F}=\mathfrak{F}\mathrm{1m}\left(F_{0}/100\right)=\mathfrak{F}\mathrm{1m}\left(\mathfrak{G}98/\mathfrak{G}100\right)=\mathfrak{G}980,000
$$  

# 11.2 STERLING 3-MONTH FUTURES CONTRACT  

This futures contract is written on a sterling 3-month deposit with a notional value of £500,000 per contract. The futures price $F_{0}$ is:  

$$
F_{0}=(100-{\mathrm{quoted~forward~interest~rate}},\%{\mathrm{p.a.}})=100-f_{12}
$$  

A change in the annual forward rate of 1 bp (i.e. 0.01 of $1\%$ p.a.) gives a 1bp change in the futures price (Equation 11.4). But a change of 1 bp over a year is equivalent to a change of 0.25 bps over 3 months, which with a contract size of £500,000 amounts to a change in value of one sterling futures contract of £12.50 $(=(0.25/100)\times£500,000)$ .  

Tick size is 1 bp $0.01\%$ p.a.) which gives a tick value of £12.50 per contract.  

# 11.3 T-BILL FUTURES  

Suppose it is 1 July and Ms Long buys the September T-bill futures contract (Figure 11.2). This contract allows delivery of T-bills at maturity of the futures contract, which we assume is 25 September. The contract allows delivery of T-bills each with a face value of $\$100$ , which on 25 September have a further 90, 91 or 92 days to maturity. However, the convention is that the quoted IMM-index is based on delivery of a 90-day bill. If a 90-day T-bill is delivered on 25 September it can be redeemed (at the Central Bank, ‘the Fed’) for $\$100$ on 24 December. The contract size is for delivery of $\$10$ of 90-day T-bills.  

T-bill futures contracts have maturity dates out to about 2 years. The contract expiration months are March, June, September, and December, with the last trading day being the business day prior to the date of issue of cash market (spot) T-bills, in the 3rd week of the month. So on 15 April there will be June, September, December contracts available, all of which deliver in these expiry months a T-bill with a further 90 days to maturity.  

Delivery is allowed on the next business day after the last trading day and any business day thereafter during the expiration month. It is the uncertainty in these variable delivery arrangements that often lead to the contracts being closed out before expiration. Also, the delivery date on the futures is often timed to coincide with the date on which US 365-day T-bills have between 90 and 92 days left to maturity as this facilitates a liquid spot market for delivery of T-bills.  

The 90-day T-bill futures contract has an IMM-index quote, discount rate $d_{f}$ and futures price $F$ , given above, by Equations (11.1), (11.2), and (11.3) for the Eurodollar futures.4 So the tick value for the T-bill futures contract is $\$25$ . These two futures contracts are therefore very similar, the main diferences being that Eurodollar futures are available with very long maturity dates and the T-bill futures allows delivery, whereas the Eurodollar futures is always cash settled at maturity. Of course you can close out either of the contracts at any time (up to the maturity date).  

# 11.4 FUTURES PRICE AND FORWARD RATES  

We examine the negative relationship between the forward (interest) rate and the futures price for a T-bill futures contract. Also we see that if a T-bill futures contract is purchased today and held to maturity, then today you ‘lock in’ a known forward rate (Figure 11.2).  

On 1 July you purchase one September T-bill futures for $F_{0}=\$98$ (and no cash changes hands). You hold the contract to maturity on 25 September and take delivery of one $\$100$ face value T-bill, which matures 90 days later on 24 December. On 1 July what is the interest rate you have ‘locked in’ between 25 September and 24 December?  

![](34fff5a15b3159a04a0fa6acf7c2373c58a7a9766e6f088ff122ff799c4a2551.jpg)  
FIGURE 11.2 September T-bill futures contract  

On 24 December your 90 day T-bill matures, you take it to the US Federal Reserve (i.e. the Central Bank) and receive $\$100$ . Hence, on 1 July, you know that the 90-day forward rate you will earn between 25 September and 24 December is:  

$$
f_{12}=[(100/98)-1]\:(365/90)=[(M/F_{0})-1]\:(365/90)=8.28\:\%
$$  

On 1 July you know that if you hold the futures to maturity and then hold the T-bill delivered in the futures contract for a further 90 days, that you will earn a forward interest rate of $8.28\%$ p.a. (simple rate), between 25 September and 24 December. On 1 July you have therefore ‘locked in’ this (forward) interest rate. Later we see that you can lock in this forward rate even if you close out the future contract before its maturity date of 25 September – although there will be some residual basis risk. Rearranging the above equation, the September-futures price on 1 July is:  

$$
F^{S e p t}=\frac{\$100}{[1+f_{12}(90/365)]}
$$  

The equivalent formulas using compound and continuously compounded rates6 are:  

$$
\begin{array}{l l l}{{F^{S e p t}=\displaystyle\frac{\S100}{(1+f_{12})^{90/365}}}}&{{\quad\mathrm{(compoundrate)}}}&{{}}\\ {{F^{S e p t}=\S100e^{-f_{12}t_{12}}}}&{{\quad\mathrm{(f_{12}=c o n t i n u o u s l y c o m p o u n d e d r a t e,}t_{12}=90/365/100e^{-f_{12}})}}\end{array}
$$  

According to Equations (11.5a)–(11.5c), as the 90-day forward rate rises (or falls) over time (i.e. between 1 July and 25 September), the futures price will fall (or rise). As can be seen from all of the above (alternative) equations for $F_{;}$ , all interest rate futures contracts have the feature that the futures price $F$ and the 90-day forward rate $f_{12}$ move in opposite directions.  

Note, however, that the forward rate applicable to each contract is diferent. On 1 July, the September-futures price is determined by the 90-day forward rate that applies from 25 September to 24 December. On 1 July the December-futures price, is determined by the 90-day forward rate that applies from the maturity date of the December-futures (say 24 December) over the next 90 days to 25 March (of the next year). Both are 90-day forward rates but they apply over diferent time periods.  

# 11.5 PRICING INTEREST RATE FUTURES  

Consider an interest rate futures contract which matures at $t=1$ year and delivers a 1-year cash market T-bill which has a face value at $t=2$ , of $\$100$ . The futures contract ‘locks in’  

the current quoted forward rate $f_{12}$ (simple interest, which applies between $t=1$ and $t=2$ ). We can show that the no-arbitrage price of the futures contract is:  

$$
F_{0}=\frac{\S100}{(1+f_{12}t_{12})}
$$  

All Equation (11.6) says is that you would be prepared to enter into a contract today (at $t=0$ ) in which you agree to pay $F_{0}$ at time $t=1$ , if you have a guaranteed payment of $\$100$ at $t=2$ . We can show that this is indeed the case by constructing an arbitrage portfolio consisting of a ‘synthetic’ or ‘replication’ futures contract – that is, a portfolio that has the same payof as the futures contract, itself. The idea is that at $t=0$ , a 1-year cash-market T-bill plus a futures contract which matures in one year (and delivers a 1-year T-bill) is equivalent to holding a 2-year cash-market T-bill (at time $t=0$ ).  

Today, if you invest $\$1$ over 2 years with Citibank at a (simple) interest rate $r_{2}$ this is worth $\$1(1+r_{2}t_{2})$ in 2 years’ time. Alternatively, today you can invest $\$1$ with Barclays at the 1-year spot rate $r_{1}$ , which will be worth $\$1(1+r_{1}t_{1})$ at the end of year-1. Today, you can also agree a forward deposit of $\$1(1+r_{1}t_{1})$ with Bank of America (BoA) to begin in 1 year’s time and to last for a further year. The $\$1$ investment in Barclays together with the forward agreement with Bank of America will accrue to $\mathbb{S}(1+r_{1}t_{1})(1+f_{12}t_{12})$ in 2 years’ time. The 2-year investment in Citibank and the two 1-year investments in Barclays and BoA must be worth the same in 2 years’ time, otherwise arbitrage profts can be made (see Cuthbertson and Nitzsche 2008). Hence, the no-arbitrage forward rate is given by7:  

$$
\S1(1+r_{2}t_{2})=\S1(1+r_{1}t_{1})(1+f_{12}t_{12})
$$  

$$
f_{12}=\left(\frac{t_{2}}{t_{12}}r_{2}-\frac{t_{1}}{t_{12}}r_{1}\right)\frac{1}{\left(1+r_{1}t_{1}\right)}\approx\left(\frac{t_{2}}{t_{12}}r_{2}-\frac{t_{1}}{t_{12}}r_{1}\right)
$$  

Figure 11.3 provides the basic steps to determine the (no-arbitrage or ‘fair’ or ‘correct’) futures price. Note that we use (simple) yields (not discount rates) throughout – and a day-count convention of ‘actual/365’.  

$m_{i}=$ number of days to delivery (maturity) date of futures contract   
$m_{12}=$ number of days to maturity of the T-Bill underlying the futures contract $m_{2}=m_{1}+m_{12}$ $t_{1}=(m_{1}/365)$ $t_{2}=(m_{2}/365)$ and $t_{12}=(m_{12}/365)$ $r_{1}=\mathrm{spot}$ rate over period $t=0$ to $t=1$ , $r_{2}=$ spot rate over period $t=0$ to $t=2$ $f_{12}=$ forward rate over period $t=1$ to $t=2$   
$\$100=$ maturity/face value of (cash market) T-bills delivered in the futures contract  

![](aa0fa77e258c909112ff704a24c754e911afd20fd21d3dc9621f3b4bceee9a15.jpg)  
At $t=1$ , on payment of $F$ , the T-bill futures contract delivers a cash market T-bill with 1-year to maturity and face value $\$100$ .  

# FIGURE 11.3 Pricing T-bill futures  

We form two portfolios A and B which have the same payout of $\$100$ after 2 years. Hence for zero arbitrage profts to be made, the two portfolios must be worth the same today.  

Portfolio-A $({\pmb t}={\bf0})$ : Purchase a $t_{2}=2$ -year cash market T-bill with maturity value $\$100$ . Today, the quoted spot price of the 2-year T-bill is:  

$$
S=\frac{100}{(1+r_{2}t_{2})}=\frac{100}{(1+r_{1}t_{1})(1+f_{12}t_{12})}
$$  

Suppose today a futures contract with maturity of 1 year and current quoted futures price of $\mathrm{~F~}$ is available. The futures contract delivers a $\$100$ face value T-Bill in $t_{1}=1$ year’s time and the T-bill delivered has a further $t_{12}=1$ years to maturity. Now consider the replication portfolio-B:  

# Portfolio-B $\mathbf{\eta}(\mathbf{\pmb{t}}=\mathbf{0}),$  

(i) buy a 1-year cash-market T-bill with maturity value $F$ and (ii) go long a 1-year T-bill futures contract with quoted price $F$ (payable at $t=1$ ), which delivers a cash-market 1-year T-bill at $t=1$ , with face value of $\$100$ at $t=2$ .  

Portfolio-B(i) pays out $\$5$ at $t=1$ when the 1-year cash-market T-bill matures. This $\$5$ is used at $t=1$ to pay for delivery of the T-bill in the futures contract. Hence, there is no net cash fow at $t=1$ .  

At $t=2$ , the T-bill delivered (1 year ago) in the futures contract matures and receipts at $t=2$ from portfolio-B are $\$100$ . The futures contract cost zero at $t=0$ (as no money changes hands) and hence the cost of setting up portfolio-B is simply the price of a cash market 1-year T-bill with maturity value $\$1$ .  

$$
{\mathrm{Price~of~cash~market~1-year~T-bill~at}}t=0={\frac{\S F}{(1+r_{1}t_{1})}}
$$  

Portfolio-A (the 2-year T-bill), also gives $\$100$ at $t=2$ . Hence both portfolio-A and portfolio-B have a cash fow of $\$100$ at $t=2$ , with no intermediate net cash fows – therefore they must have the same value at $t=0$ , otherwise risk-free arbitrage profts can be made:  

$$
S={\frac{100}{(1+r_{1}t_{1})(1+f_{12}t_{12})}}={\frac{F}{(1+r_{1}t_{1})}}
$$  

Therefore, the no-arbitrage (or fair or correct) futures price (at $t=0$ ) is:  

$$
F=\frac{100}{\left(1+f_{12}t_{12}\right)}
$$  

# 11.6 ARBITRAGE: IMPLIED REPO RATE  

As we have seen, cash-and-carry arbitrage is possible between the T-bill futures market and the T-bill cash market – this is the process by which the T-bill futures is priced. Potential arbitrage opportunities can also be analysed in terms of the implied repo rate.  

Suppose today (i.e. $t=0$ ), you can purchase a T-bill in the spot market with a remaining maturity of 32 days. And if you also go long a T-bill futures contract with maturity $T=32$ days, at a quoted price $F_{0}$ , which delivers a 90-day $\$100$ face value) T-bill, you have efectively purchased the equivalent of a 122-day cash market T-bill. Put another way you have created a ‘synthetic’ or ‘replication’ 122-day T-bill.  

If the 32-day and the 122-day T-bills and the futures contract are not correctly priced then a risk-free arbitrage proft can be made by trading these three assets. This arbitrage opportunity can be expressed in terms of the implied repo rate, (see Chapter 3) which we now examine.  

Suppose at $t=0$ we purchase the spot asset for $S_{0}$ using our own funds. At $T$ , we deliver the spot asset when the short futures contract matures and receive a cash amount $F_{0,T}$ . The gross (compound) annual return (excluding any interest cost of fnance) is known as the implied repo rate:  

$$
\widehat{r}=(F_{0,T}/S_{0})^{1/T}-1
$$  

When the implied repo rate $\widehat{\boldsymbol{r}}$ exceeds the cost of fnance (i.e. repo rate) $r$ , then arbitrage profts can be made by shorting (selling) the futures and purchasing the spot asset with funds borrowed at the actual repo rate.8  

An example of a proftable cash-and-carry arbitrage transaction by shorting T-bill futures is given in Example 11.1. We use the (cash market) T-bill day-count convention of ‘actual/ $360^{\circ}$ together with the quoted discount rates to obtain the cash market price. The underlying asset for delivery in the futures contract is a 90-day T-bill (with face/maturity/par value of $\$100$ ). The T-bill futures contract matures in 32 days. Financing the purchase of a cash market T-bill is via a repo transaction (with a bank), where the actual 32-day repo rate (for borrowing cash) is $6\%$ p.a. (compound rate).  

# EXAMPLE 11.1  

# Implied Repo Rate and Arbitrage  

Today:  

The 32-day repo rate is $6\%$ p.a. (compound rate)   
US T-bill with 122-days to maturity, discount rate $d=6\%$ (days/360) Price of T-bill $S_{0}=\S97.97\left(=100-6[122/360]\right)$ . Face value $=\$100$ . T-bill futures, 32 days to maturity, -index $=94.2\$ (discount rate $d_{f}=5.8\%)$  

Contract size T-bill futures $=\$10$ (per $\$100$ face value T-bills).  

Question: (i) Calculate the futures price and the implied repo rate. (ii) Show how arbitrage profts can be made.  

Answer: Price of 122-day T-bill : $S_{0}=\$97.97$ Futures price : $F_{0,T}=100-5.8(90/360)=\mathbb{\S}98.55$ delivery of 90- -bill Implied Repo Rat,e+ : $\widehat{r}=(F_{0,T}/S_{0})^{365/32}-1=0.0696$ $(6.96\%$ compound rate   
Arbitrage: The implied repo rate $\widehat{r}=6.96\%$ exceeds the actual repo rate (cost of borrowing) $\mathrm{r}=6\%$ . So cash and carry arbitrage is proftable, namely:  

• At $t=0$ : Buy 122-day T-bill for $\$97.97$ , fnanced by borrowing at the repo rate of $6\%$ p.a. over 32 days and sell one futures contract.  

• At $t=T$ : Use the 122-day T-bill for delivery against the short futures position in 32 days’ time (when it will be a 90-day T-bill) and receive $F_{0,T}=\$98.55$ . The amount owed on $\$97.97$ borrowed at actual repo rat,+e is $\$97.97(1.06)^{32/365}=\S98.47$  

Arbitrage proft $=\$782$  

The time to maturity of the futures contract is 32 days, at which time a 90-day T-bill is delivered. Thus, for the arbitrage transaction to be risk-free, you need to purchase a 122-day T-bill today, in order to be able to deliver a 90-day T-bill when the futures contract matures. The implied repo rate on the cash and carry arbitrage is $\widehat{r}=6.96\%$ which exceeds the actual repo rate $r=6\%$ . Hence selling (one) T-bill futures and fnancing the purchase of the 122-day cash market T-bills (at the ‘low’ repo rate of $r=6\%$ ) yields positive arbitrage profts of $\$782$ .  

In practice, fnancing cash-and-carry arbitrage using actual repos may involve some risk because the repo market is illiquid at ‘long’ horizons. Indeed, much of the liquidity is in overnight repos. Hence the arbitrageur may have to roll over her overnight repo fnancing until the futures contract reaches maturity (when all positions can then be closed out). But any ‘new repos’ that are rolled over may be more or less expensive depending on the future course of short-term repo rates – that is, there is ‘roll-over risk’.  

# 11.7 SPECULATION  

Directional bets on interest rate changes using futures is relatively straightforward. Compared to speculation by purchasing the underlying asset (e.g. spot T-bills), the futures position provides leverage, since you do not pay the futures invoice price at inception. You merely have to provide a relatively small ‘good faith deposit’ for your initial margin payment (which usually pays a competitive interest rate). Also, you may have to ‘top up’ your margin account and therefore you need cash or eligible collateral readily available.  

For any fxed income futures contract, the key feature is the inverse relationship between interest rates and futures prices. If you close out a long futures position before maturity then the proft on each futures contract is $F_{1}-F_{0}$ . Hence, if you want to speculate on a future fall in interest rates, then today you buy (go long) an interest rate futures contract (e.g. a T-bill futures contract or a Eurodollar futures contract). If interest rates fall, the futures price rises and hence you make a proft from your long position when you close out by selling the futures contract at a higher price.  

Today, if you forecast a rise in interest rates, you would sell (‘short’) interest rate futures contracts – if interest rates subsequently rise, you close out (i.e. buy back) your futures contracts at a lower price, making a proft on the futures position. Of course, a ‘naked position’ in a futures contract (either long or short) is highly risky, since futures prices can change rapidly in either direction as interest rates change.  

# 11.8 SPREAD TRADES  

An ‘intracommodity long spread’ position consists of a long position in one nearby futures contract (i.e. with a short maturity date $t_{1,}$ ) and a short position in the far contract (i.e. with a longer maturity date $t_{2}$ ). Both contracts are on the same underlying (e.g. either 90-day T-bill futures or 3-month Eurodollar futures). Clearly, this intracommodity long spread is less risky than an outright (naked) position in either all long or all short contracts (and for this reason the initial margin is usually about one-third of that for a naked (open) position).  

As we shall see, if the yield curve undergoes a parallel shift (either up or down) there will be little or no change in value of a spread-futures position. Hence a spread position is hedged against parallel shifts in the yield curve and is a ‘bet’ placed solely on a change in the shape of the yield curve (e.g. a twist in the yield curve).  

Spread positions can be used to speculate on changes in the shape of the yield curve.  

To see how this works consider the formula for a 3-month sterling-futures contract (where we have substituted from Equation (11.7b) for the forward rate:  

$$
F=100-f_{12}\approx100-\left(\frac{t_{2}}{t_{12}}r_{2}-\frac{t_{1}}{t_{12}}r_{1}\right)
$$  

Remember that the underlying asset in $a l l$ the sterling contracts (with diferent maturity dates) is always a 3-month deposit, so $t_{12}=3$ months is fxed. Suppose it is 27 December. Consider the June-sterling futures contract which matures in $6$ months (line b, Table 11.2), and therefore has $t_{1}=6$ months and $t_{2}=9$ months $\stackrel{\prime}{t}_{12}=9-6=3$ months). Here, the ‘short-rate’ $r_{1}$ is the 6-month interest rate and the ‘long-rate’ $r_{2}$ is the 9-month interest rate. From (11.13) we have $\partial F/\partial r_{1}=t_{1}/t_{12}=(6/3)=+2$ and $\partial F/\partial r_{2}=-t_{2}/t_{12}=-9/3=-3$ .  

TABLE 11.2 Parallel shift: change in futures prices   


<html><body><table><tr><td>Futures contract</td><td>3-month rate</td><td>6-month rate</td><td>9-month rate</td><td>Parallel shift △r = △r</td></tr><tr><td>a) Long March-futures, △FMarch</td><td>+1</td><td>+2</td><td>0</td><td>-1</td></tr><tr><td>b) Long June-futures, △FJune</td><td>0</td><td>+2</td><td>-3</td><td>-1</td></tr></table></body></html>  

Notes: Today is 27 December. The March-futures matures in 3 months and the June-futures matures in 6 months – the underlying for each contract is a 90-day interest rate. Figures show the change in the March and June futures prices after a 100 bp $1\%$ p.a.) increase in short and long spot interest rates.  

The ‘payof’ of $\left\{0,+2,-3\right\}$ for the June-futures contract means that (a) the June-futures price will rise by $+2$ points if the $^{\cdot}6$ -month rate’ increases by $1\%$ (over the next week, say) and (b) the June-futures price will fall by 3 points if the $^{\cdot_{9}}$ -month rate’ increases by $1\%$ (over the next week). The net result of a simultaneous $1\%$ rise in both short (6-month) and long (9-month) rates (i.e. a parallel shift in the yield curve) is a change in the June-futures price of $\Delta F^{J u n e}=+2-3=-1$ , over the next week (line b, last column in Table 11.2).  

Now consider being long the March-futures which matures in 3 months (line a, Table 11.2). If you repeat the above (with $t_{1}=3$ months and $t_{2}=6$ months and $t_{12}=6-3=3$ months) then the efect of a $1\%$ rise in both rates on the change in March-futures price is also $\Delta F^{M a r c h}=-1$ .  

Hence if you are long the March-futures and short the June-futures (Table 11.2), the net efect of a parallel shift in the yield curve on this ‘long futures spread’ $=-1+1=0$ . The long-short spread position is hedged against parallel shifts in the yield curve. We now wish to demonstrate that:  

If you hold a ‘long-spread’ then you gain when the yield curve becomes steeper.  

The above conclusion holds regardless of whether the yield curve, as a whole, moves up or down – as long as it becomes steeper. Consider the following ‘long spread’ on futures on 27 December when you are:  

• Long, the March-futures contract (nearby contract) • Short, the June-futures contract (far contract)  

The change in value of this ‘long-spread’ futures position depends on the change in the 3, 6 and 9 month spot rates. The long March-futures contract has a $\{+1,-2,0\}$ payof and the short June-futures contract has a $\{0,-2,+3\}$ payof. The net exposure in the spread is given in Table 11.3.  

TABLE 11.3 Long Eurodollar futures spread   


<html><body><table><tr><td>Futures contract</td><td>3-month spot rate</td><td>6-month spot rate</td><td>9-month spot rate</td></tr><tr><td>Long March-futures, △FMarch</td><td>+1</td><td>-2</td><td>10</td></tr><tr><td> and Short June-futures, △FJune</td><td>10</td><td>-2</td><td>+3</td></tr><tr><td>= (Net) Long spread</td><td>+1</td><td>-4</td><td>+3</td></tr></table></body></html>  

Notes: Today is 27 December. The March-futures matures in 3 months and the June-futures matures in 6 months – the underlying for each futures contract is a 90-day interest rate. Figures show the change in the March and June futures prices after a 100 bp $1\%$ p.a.) increase in short and long spot rates – which causes changes in the respective forward rates, which then determine the futures prices (see Equation 11.13).  

Let us see what happens when there is a steepening in the yield curve – that is, the 9-month spot rate moves up more than the 6-month rate, which in turn increases more than the 3-month rate. For example, $\Delta r_{9m}=+3$ , $\Delta r_{6m}=+2$ , $\Delta r_{3m}=+1$ , so:  

$$
\Delta r_{9m}>\Delta r_{6m}>\Delta r_{3m}
$$  

hence $\Delta r_{9m}-\Delta r_{6m}\geq\Delta r_{6m}-\Delta r_{3m}$ .  

From the long-spread position in Table 11.3, the net efect is:  

Change in value of ‘long spread’:  

$$
\begin{array}{r l}&{\mathrm{~\gamma=(+1)}\Delta r_{\mathrm{3m}}-4\Delta r_{\mathrm{6m}}+3\Delta r_{\mathrm{9m}}=3(\Delta r_{\mathrm{9m}}-\Delta r_{\mathrm{6m}})-(\Delta r_{\mathrm{6m}}-\Delta r_{\mathrm{3m}})>0}\\ &{\mathrm{~\gamma=3(+1)}{-}(+1)=+2}\end{array}
$$  

The above result shows that when the yield curve steepens the value of a long-spread position in Eurodollar futures increases. This also holds even if the $\Delta r$ are all negative, as long as this involves the yield curve becoming steeper. The converse of the above also holds:  

If you hold a ‘short spread’ (i.e. short March-futures, long June-futures,), you gain when the yield curve becomes less steep (i.e. fatter).  

The change in the value of various futures positions, to changes in the position and shape of the yield curve are summarised in Table 11.4. It is clear that naked futures positions (i.e. either all long or all short interest rate futures) can be used to speculate on the general direction of changes in all interest rates (i.e. parallel shifts, either up or down). In contrast, spread positions are hedged against parallel shifts in the yield curve but are ‘bets’ on changes in the slope of the yield curve (e.g. ‘twists’).  

TABLE 11.4 Change in futures prices   


<html><body><table><tr><td>Scenario</td><td>Long futures</td><td> Short futures</td><td>Long spread</td><td>Short spread</td></tr><tr><td>All yields rise (upward parallel shift)</td><td>-</td><td>+</td><td>0</td><td>0</td></tr><tr><td>All yields fall (downward parallel shift)</td><td>+</td><td></td><td>0</td><td>0</td></tr><tr><td>Yield curve steeper</td><td>+or -</td><td>+or-</td><td>+</td><td>-</td></tr><tr><td>Yield curve less steep</td><td>+or -</td><td>+or-</td><td></td><td>+</td></tr></table></body></html>

Notes: The table shows the direction of change of futures prices for long and short positions and for long and short spread positions in interest rate futures contracts, to various movements in the spot yield curve.  

# 11.9 SUMMARY  

• Contract details and quotes for short-term interest rate futures on 3-month (90-day) Eurodollars and 3-month (90-day) US T-bills are very similar. The quoted IMM-index is linked to the forward discount rate $d_{f}$ (quoted at $t=0$ ):  

$$
I M M_{0}=100-d_{f}
$$  

• A change in the IMM-index of $0.01\%$ (i.e. 1 tick) leads to a change in value of one Eurodollar futures contract or one T-bill futures (both of which have a contract size of $\$10$ ) of $\$25$ ( $\mathbf{\bar{\Psi}}=\mathbf{\Psi}$ tick value).  

• Today, the fair price $F$ of a 90-day US T-bill futures contract or 90-day Eurodollar futures contract which matures at $t=1$ is determined by riskless arbitrage and results in:  

$$
F=\mathbb{S}100/(1+f_{12}t_{12})
$$  

where $f_{12}$ is today’s quoted forward yield (simple rate) applicable between the maturity date of the futures $t_{1}$ (years) and $t_{2}=t_{1}+90/365$ , hence $t_{12}=90/365$ .  

• If $f_{12}$ is the continuously compounded yield then $\mathrm{F}=\$100e^{-f_{12}t_{12}}$ . Alternatively if $f_{12}$ is a compound rate then $F=\mathbb{S}100/(1+f_{12})^{t_{12}}$ . Finally, given the index quote then the (futures) discount rate $d_{f}=100-I M M$ and the futures price is $F=100[1-(d_{f}/100)(90/360)]$ . All of the formulas give the same value for the futures price, when used with the appropriately measured forward rate.  

• A person who speculates on the direction of interest rate changes would buy (sell) an interest rate futures contract today, if she forecasts interest rates to fall (rise) in the future.  

• The implied repo rate (compounded) is the percentage return from buying the underlying asset and selling the futures contract $\widehat{r}=(F_{0,T}/S_{0})^{1/T}-1$ . The repo rate $r$ is the actual cost of borrowing funds. When the implied repo rate $\widehat{\boldsymbol{r}}$ is not equal to the actual repo rate $r$ (i.e. cost of borrowing or lending money), then risk-free arbitrage profts can be made.  

• For example, if today $\widehat{r}>r$ then arbitrage profts can be made by selling (shorting) an interest rate futures contract (which matures at $T=t_{1}\mathrm{\cdot}$ ) and today borrowing cash at the repo rate to purchase a cash market T-bill with maturity at $t_{2}=t_{1}+90/365)$ . At time $T=t_{1}$ , the cash market T-bill has 90-days to maturity and can be delivered in the futures contract.  

• Spread trades using interest rate futures, can be used to speculate on changes in the slope of the yield curve (e.g. a twist in the yield curve), while being hedged against parallel shifts in the yield curve.  

# APPENDIX 11.A: FUTURES PRICES AND INTEREST RATES  

In this appendix we:  

• Derive futures prices from spot yields and forward yields. • Show how diferent conventions for calculating spot-yields and forward-yields give different formulas for the futures price, but all formulas result in the same futures price. • Show how to calculate discount rates and the quoted IMM index from futures prices.  

# Using Compound Rates  

It is 25 May. We want to calculate the T-bill futures prices and IMM-index quotes for the June and September interest rate futures contracts, using only the known term structure of spot yields $r$ at $t=0$ . First, we calculate forward yields from spot yields and use these forward rates to calculate the ‘fair’ (no-arbitrage) futures prices $F$ for the June and September futures. Finally we derive the IMM-indices from the futures prices. We use compound rates. Our results also apply to the June and September (90-day) Eurodollar futures.  

Suppose it is 25 May and we have spot yields on cash-market T-bills with 32, 122, and 212 days to maturity (see Figure 11.A.1). Assume the day-count convention is ‘actual/365’. Note that $122-32=90$ days and $212-122=90$ days. We assume the 32-day spot T-bill matures on exactly the same day that the June-futures contract matures (which delivers a  

![](e586b0690c44a5f4b530a60899aea4ae774d4ffcf8644848954ba4a7be6320a7.jpg)  
FIGURE 11.A.1 Spot and forward yields (compound rates)  

90-day T-bill). Also, the 122-day cash market T-bill matures on exactly the same day that the September-futures contract matures.  

# Compound spot yields:  

$$
\begin{array}{l l l l}{{r_{0,32}=0.09}}&{{\quad r_{0,122}=0.10}}&{{\quad r_{0,212}=0.12}}\\ {{t_{0,32}=32/365}}&{{\quad t_{0,122}=122/365}}&{{\quad t_{0,212}=212/365}}\end{array}
$$  

Using (compound) spot yields we can calculate the (compound) forward yields:  

$$
\begin{array}{c}{{(1+r_{0,32})^{32/365}(1+f_{32,122})^{90/365}=(1+r_{0,122})^{122/365}}}\\ {{}}\\ {{(1+r_{0,122})^{122/365}(1+f_{122,212})^{90/365}=(1+r_{0,212})^{212/365}}}\end{array}
$$  

$$
f_{32,122}=0.1036\qquadf_{122,212}=0.1477
$$  

Note that because the spot yield curve is upward sloping the forward-rate curve lies above the spot-rate curve (e.g. $f_{32,122}=0.1036>r_{0,122}=0.10)$ . Each T-bill futures contract delivers a 90-day T-bill. Hence the no-arbitrage futures prices quoted on $25\mathbf{M}$ ay are:  

$$
F_{32,122}(J u n e\ F u t u r e s)={\frac{\mathfrak{H}100}{(1+f_{32,122})^{90/365}}}=\mathfrak{H}97.60\ (\mathrm{per\}\mathfrak{H}00\ \mathrm{nominal})
$$  

$$
F_{122,212}(S e p t f u t u r e s)={\frac{\mathfrak{H}100}{(1+f_{122,212})^{90/365}}}=\mathfrak{H}96.66\ (\mathrm{per\}\mathfrak{H}00\ \mathrm{nominal})
$$  

# IMM Futures Index  

Now, we take the above futures prices $F$ and calculate the quoted (futures) discount rate $d_{f}$ and IMM-index using:  

$$
F=100\left[1-\left({\frac{d_{f}}{100}}\right)\left({\frac{90}{360}}\right)\right]{\mathrm{~and~}}I M M=100-d_{f}
$$  

Hence:  

$d_{f}(32,122)=9.603\%$ June futures and $d_{f}(122212)=13.358\%$ Sept futures  

$I M M(32,122)=90.396$ June futures and $I M M(122212)=86.641$ Sept futures  

Note that when calculating and $d_{f}$ we use the US T-bill futures day-count convention of ‘actual/360’ and assume a 90-day bill is delivered in the futures contract. By using the no-arbitrage equations (11.A.2a) and (11.A.2b) for the forward rates, we ensure that there are no risk-free profts to be made when the futures prices are calculated in (11.A.3a) and (11.A.3b). For example, it is impossible on 25 May to make a risk-free arbitrage proft by buying (or selling) a combination of the 32-day (June), 212-day (September) cash market T-bills and the June-futures contract, priced at $F_{32,122}(\mathrm{June-futures})=97.60$ .  

Above, we started with T-bill spot yields and calculated forward rates, futures prices and the IMM-index. Note that we could also reverse this line of reasoning. Given ${r}_{0,32}$ we could use the two observed forward prices $F_{32,122}(J u n e\ F u t u r e s)={\mathfrak{G}}97.60$ and $F_{122,212}$ Sept futures $=\$96.66$ to calculate $f_{32,122}{\mathrm{and}}f_{122,212}$ and then use these in Equations (11.A.2a) and (11.A.2b) to calculate the term structure of spot yields – namely $r_{0,122}$ and $r_{0,212}$ . Here we are constructing the spot yield curve from observed futures prices.  

# Continuously Compounded and Simple Interest Rates  

Assume a day-count convention of $t={\mathrm{'days}}/{365\mathrm{:~}\mathbb{\mathbb{S}}1}$ invested over $t$ years (or fraction of a year) must give the same terminal value, independently of what convention we use to measure yields. Hence, the relation between simple yields $r^{s}$ , compound yields $r$ and continuously compounded yields $r^{c}$ is:  

$$
1+r^{s}(d a y s/365)=(1+r)^{d a y s/365}=e^{r^{c}(d a y s/365)}
$$  

It follows that:  

$$
\begin{array}{l}{r^{c}=\ln(1+r)\quad\mathrm{~and~}}\\ {r^{s}=(365/\mathrm{days})(e^{r^{c}(d a y s/365)}-1)}\end{array}
$$  

# Continuously Compounded Rates  

Using (11.A.5a), the equivalent continuously compounded spot rates to those in (11.A.1a) are:  

$$
r_{0,32}^{c}=0.08618\qquadr_{0,122}^{c}=0.09531\qquadr_{0,212}^{c}=0.11333
$$  

Take logarithms of Equations (11.A.2a) and (11.A.2b) and using $r_{i}^{c}=\ln(1+r_{i})$ and $f^{c}=$ $\ln(1+f)$ :  

$$
\begin{array}{c}{{t_{1}r_{1}^{c}+t_{12}f_{12}^{c}=t_{2}r_{2}^{c}}}\\ {{{}}}\\ {{t_{2}r_{2}^{c}+t_{23}f_{23}^{c}=t_{3}r_{3}^{c}}}\end{array}
$$  

where $=32/365,t_{2}=122/365,t_{3}=212/365,t_{12}=t_{2}-t_{1}=90/365=t_{23}=t_{3}-t_{2}.$ Hence:  

$$
f_{32,122}^{c}=0.0986\qquadf_{122,212}^{c}=0.1378
$$  

$$
\begin{array}{r l}{{}}&{{\cal F}_{32,122}(J u n e{-}F u t u r e s)=100~e^{-f_{32,122}^{c}(90/365)}=\S97.60}\\ {{}}&{{\cal F}_{122,212}(S e p t{-}f u t u r e s)=100~e^{-f_{122,212}^{c}(90/365)}=\S96.66}\end{array}
$$  

# Simple Rates  

For the compound spot yields in (11.A.1a), the equivalent simple rates are $r^{s}=(1/t)(e^{r^{c}t}-1)$ , hence:  

$$
r_{0,32}^{s}=0.08651r^{s}\qquadr_{0,122}^{s}=0.09684\qquadr_{0,212}^{s}=0.11714
$$  

The no-arbitrage (simple) forward rates are determined by:  

$$
\begin{array}{r}{[1+r_{0,32}^{s}(32/365)][1+f_{32,122}^{s}(90/365)]=[1+r_{0,122}^{s}(122/365)]}\\ {[1+r_{0,122}^{s}(122/365)][1+f_{122,212}^{s}(90/365)]=[1+r_{0,212}^{s}(212/365)]}\end{array}
$$  

Hence: $\dot{f}_{32,122}^{s}=0.09976$ $f_{122,212}^{s}=0.14012$  

$$
\begin{array}{r l}&{F_{32,122}(J u n e\ F u t u r e s)=100\ /[1+f_{32,122}^{s}(90/365)]=\S97.60\ }\\ &{F_{122,212}(S e p t\ f u t u r e s)=100\ /[1+f_{122,212}^{s}(90/365)]=\S96.66}\end{array}
$$  

Hence as expected, the diferent interest rate conventions all give the same value for the June and September futures prices.  

# EXERCISES  

# Question 1  

Explain how you can use interest rate futures (e.g. Eurodollar futures) to speculate on (parallel) shifts in the yield curve.  

# Question 2  

Explain why 90-day Eurodollar futures prices for contracts with diferent maturities, might move by diferent amounts (over 1 week, say). Assume continuously compounded rates and an actual/360 day-count convention.  

# Question 3  

Explain how a speculator might use 90-day Eurodollar futures with diferent maturity dates to speculate on ‘twists’ (non-parallel shifts) in the yield curve. Assume continuously compounded rates and an actual/360 day-count convention.  

Why might a speculator take a long-short position in Eurodollar futures contracts with diferent maturity dates?  

# Question 4  

The 9-month spot rate is $10\%$ p.a. and the 6-month spot rate is $9\%$ p.a. (continuously compounded). What is the futures price for a contract which delivers a 90-day T-bill (with a face value of $\$100$ ), in 6 months’ time? What is the IMM index quote and the forward discount rate $d_{f}?$  

# Question 5  

The quoted IMM index on a US T-bill futures contract is $I M M=90.00$ . The futures contract matures in 30 days.  

A 120-day T-bill is also available with a discount rate $d=10\%$ (day-count convention is actual/360). The price of the cash-market T-bill is obtained from the discount rate using:  

What is the implied repo-rate (continuously compounded, 365-day year)?  

Explain what arbitrage opportunities exist if the actual repo-rate is $r=10.3\%$ (continuously compounded).  

# Question 6  

Spot yields for 6–month and 9–month interest rates are $r_{6}=5.30\%$ p.a. and $r_{9}=5.2\%$ p.a. (continuously compounded) and the price of the 6–month and 9–month cash-market T-bills are $S_{6}=100e^{-0.05/2}=97.531$ and $S_{9}=100e^{-0.05(0.75)}=96.175$ .  

The fair (no-arbitrage) price of a T-bill futures contract which matures in 6 months’ time and delivers a $\$100$ face value (3-month) T-bill is $\mathrm{F}=\$98.6097$ . The quoted price for a T-bill futures contract which matures in 6 months is $F_{q}=\$98$ .  

Explain how arbitrage profts can be made.  