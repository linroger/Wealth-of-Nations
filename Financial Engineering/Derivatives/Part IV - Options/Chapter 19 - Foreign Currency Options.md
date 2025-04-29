---
tags:
  - foreign_currency
  - fx_options
  - hedging
  - otc_market
  - speculation
aliases:
  - Currency Options
  - FX Options
  - OTC Options
key_concepts:
  - Call option
  - FX options contracts
  - Hedging with options
  - OTC market
  - Put option
---
# Foreign Currency Options  

# Aims  

• To examine contract specifcations for foreign currency options and the payofs from calls and puts.   
• To analyse the advantages and disadvantages of hedging future foreign currency receipts/payments with either futures or options   
• To briefy outline some non-standard (‘exotic’) currency options.  

# 19.1 CONTRACT SPECIFICATIONS  

Most FX-options contracts are traded in the OTC market as they can be tailored to meet the needs of corporate treasurers in terms of size of the deal, currency used, and maturity dates. The exchange-traded FX options markets are much smaller in volume although exchange traded options on spot FX rates are available on NASDAQ (which was the Philadelphia Stock Exchange, now called NASDAQ-OMX-PHLX).  

Most contracts traded are against the US dollar and the option premium is quoted in cents per unit of foreign currency, with the only exception being contracts on the Japanese yen which are quoted in hundredths of a cent. Delivery is the foreign currency (in exchange for USD). There are also options contracts which deliver an FX-futures contract – futures options are dealt with in Chapter 20.  

For example (Table 19.1), the contract size for the (British) pound sterling (GBP) is for £31,250 and entries are quoted in cents per GBP. If the current spot rate on 26 July is $S_{0}=$ $1.5000(\S/£)$ then October-options would be available with strike prices around this value; for example, for strikes of 1.490, 1.495, 1.510, and 1.520 (although these are not the only strike prices available). If the quoted call premium for one October-1.5200 (American style) contract on GBP is 2.05 cents (per GBP) then the invoice price for one contract is $\$640.63[=£31,250\times$ 0.0205 $(\$/£)]$ .  

TABLE 19.1 Foreign currency options (NASDAQ-OMX-PHLX)   


<html><body><table><tr><td>Currency against dollar</td><td>Contract size</td><td>Strike price increments</td><td>Min. price change</td></tr><tr><td>Pound sterling</td><td>31,250</td><td>$0.025</td><td>$0.0001 (1 pip or point) = $3.125</td></tr><tr><td>Euro</td><td>62,500</td><td></td><td></td></tr><tr><td>Japanese yen</td><td>¥6,250,000</td><td>$0.050</td><td>$0.000001 = $6.25</td></tr><tr><td>Canadian dollar</td><td>C$50,000</td><td>$0.050</td><td>$0.0001 = $5.00</td></tr></table></body></html>  

In addition to exchange traded options, there is also a large OTC market in currency options where clients are provided with ‘tailor-made’ options with diferent strikes, contract sizes, and time to maturity.  

If a US company has to pay for imports from the UK at a known time in the future then it may be worried about a rise in sterling, as the imports will then cost more in USD. It can set a maximum amount of USD it will pay for the imports in the future by buying a call option on sterling today. The call option gives the US company the right to purchase (receive) GBP at a strike price, $K$ (USD per GBP) even if the spot FX-rate for sterling at expiration is higher than $K$ . The call also allows the US company the right not to exercise the call option if the spot-FX rate is below $K.$ . The US company will then purchase sterling at the low spot FX-rate, $S_{T}<K$ (USD per GBP) thus reducing the USD cost of the imports.  

On the other hand if a US company has to convert sterling into USD in the future (e.g. from export sales in the UK), it may be worried about a fall in sterling, as it will receive less USD for each GBP. It can set a minimum amount of USD it will receive in the future by buying a put option on sterling today. The put option gives the US company the right to sell GBP at a strike price, $K$ (USD per GBP) even if the spot FX-rate for sterling at expiration is lower than $K$ . The put also allows the US company not to exercise the option if the spot-FX rate is above $K$ . The US company will then sell sterling at the high spot FX-rate, $S_{T}>K$ (USD per GBP,) thus increasing its USD receipts.  

# 19.2 SPECULATION  

# 19.2.1 Profit from a Long Call  

Foreign currency options can be used for speculation. Long positions have limited downside risk (the option premium) yet provide the possibility of large speculative profts by exploiting  

![](f57683e1c14c0bb3cecd57ffd5d25e89e634d08729da4a734d06ba2e3c4aa7c3.jpg)  
FIGURE 19.1 Foreign currency call option  

leverage. We demonstrate the payofs from a long position in either a (European) call or put. If held to maturity, a long call gives a proft (Figure 19.1):  

$$
\begin{array}{r l r}{\lefteqn{\Pi=\operatorname*{max}(0,S_{T}-K)-C}}\\ &{}&{=-C\qquad\operatorname{if}S_{T}\leq K}\\ &{}&{=S_{T}-K-C\qquad\operatorname{if}S_{T}>K}\end{array}
$$  

The breakeven spot rate at $T$ is:  

$$
S_{B E}=K+C
$$  

A long call on sterling gives the investor the right to receive $z=\pm31,250$ at expiration, at an exchange rate of $K=140$ cents (per GBP). Suppose in January, the March-140 call on sterling has a premium of $C=4$ cents (per GBP) then:  

$$
\mathrm{ntract}=z C=£31,250\left(0.04\right)=\S1,250
$$  

If the spot price in March at expiration turns out to be $S_{T}=1.50(\Phi/£)$ (see Figure 19.1), then:  

$$
\mathrm{Payoff}=(S_{T}-K)z=(1.50-1.40)\:\pm31,250=\S3,125
$$  

The proft on one contract is:  

$$
\Pi=(S_{T}-K-C)£31,250=\S1,875
$$  

If $S_{T}<K$ then the option will not be exercised and the loss will be limited to the call premium, or more precisely the invoice price of one contract $\$1,250$ . The breakeven spot rate at expiration is:  

$$
S_{B E}=K+C=1.40+0.04=1.44(\Phi/£)=144(\mathrm{cents}/£)
$$  

It should be obvious that the appropriate speculative strategy is:  

Buy (go long) a call on sterling if you expect sterling to appreciate (above $S_{B E}=K+C)$ .  

# 19.2.2 Profit from a Long Put  

A long put on sterling gives the investor the right to sell £31,250 at a strike price of $K(\$4$ . Hence the investor makes a proft if spot sterling depreciates below $K$ , at expiration of the option (Figure 19.2). The proft is:  

$$
\begin{array}{r l r}{\lefteqn{\Pi=\operatorname*{max}(0,K-S_{T})-P}}\\ &{}&{=K-S_{T}-P\qquad\operatorname{if}S_{T}<K}\\ &{}&{=-P\qquad\operatorname{if}S_{T}\geq K}\end{array}
$$  

The breakeven spot rate (at $T$ ) is:  

$$
S_{B E}=K-P=1.44-0.025=1.44-0.025=1.415
$$  

The proft profle is given in Figure 19.2 for $K=1.44\left({\Phi/£}\right)$ and $S_{T}=1.40\left(\mathbb{\Phi}/£\right)$ where the put premium $P=\$025$ (2.5 cents).  

Invoice price contract $=P z=\left(0.025(\Phi/£)\right)£31,250=\mathfrak{F}781.25$  

![](ca785d78eabd46c8f0a8825ecc9c405d2ffa7bb02d753b68d3c6339a5b15cfb0.jpg)  
FIGURE 19.2 Foreign currency put option  

$$
\mathrm{Grossprofit}=(K-S_{T})z=(1.44-1.40)\:£31,250=\mathfrak{F}1,250
$$  

The proft per contract is:  

$$
\Pi=(K-S_{T}-P)£31,250=\S468.75
$$  

The maximum proft occurs if the spot FX-rate $S_{T}$ falls to zero:  

$$
\Pi_{\mathrm{max}}=(K-P)£31,250=(1.44-0.025)£31,500=\S44,218.75
$$  

The appropriate speculative investment strategy is:  

Buy (go long) a put on sterling if you expect sterling to depreciate (below K P).  

Foreign currency calls and puts can be combined to give more complex payofs (at maturity) such as straddles, straps, butterfy spreads, condors etc. (as discussed in Chapter 17).  

# 19.3 HEDGING FOREIGN CURRENCY EXPOSURE  

Foreign currency options are not as widely used in hedging as foreign currency futures, nevertheless options provide a useful alternative particularly when the receipt or payment of foreign currency is not known with certainty. We have seen how foreign currency futures (or forwards) can be extremely useful in hedging when the investor knows for certain that she will either receive or have to pay out foreign currency at some time in the future. Using options can be useful when the investor might receive or might have to make foreign currency payments in the future but she doesn’t know her future cash fow position for certain.  

For example, suppose a US frm is making a bid on an investment project to supply IT hardware to the UK but it doesn’t know in advance whether the bid will be accepted and hence whether it will receive any sterling in the future. Next, consider a US investor who has prospective foreign currency receipts in the form of dividends on foreign stocks or she feels she may have to sell some stocks in 1 year’s time to obtain additional USDs, but she does not know for certain if this is what she will actually do when the time arrives.  

Next consider a US multinational that may have to buy foreign currency in 1 year’s time when it starts to build a new plant in a foreign country (i.e. direct investment abroad) but it raises USD fnance from its US ‘correspondent bank’. Similarly, a US investor who is contemplating the purchase of a foreign security (e.g. stocks or bonds) fnanced from USD cash infow in the future, may wish to remove exchange rate risk. If the USD fnance becomes available, all is well, but she might not want to go ahead with the FX deal if her (dollar) cash infow does not materialise.  

In all these cases a foreign currency option is appropriate since it gives the holder the right to exchange currencies in the future at an exchange rate fxed today, but crucially the option also allows the holder to ‘walk away’ from the deal if it is not to her advantage.  

For our specifc example we consider a US frm UncleSam, that in January is making a bid on an investment contract, to supply IT hardware to the UK. But UncleSam doesn’t know in advance whether the bid will be accepted and hence whether it will receive any sterling (GBP) in the future. Suppose the outcome of the bid will be announced in 1 year’s time (December) and if successful involves an immediate receipt by UncleSam of $V=£12.5\mathrm{m}$ . The current (1-year) forward rate $F_{0}=1.61(\Phi/\mathrm{\Phi})$ giving a dollar equivalent of $\$20.125m$ . Now consider the alternatives of having no hedge in place versus using either forwards, futures or options to hedge its sterling exposure.  

# 19.3.1 Numerical Example  

The initial data is given in Table 19.2. In January, the initial spot and forward rates are $S_{0}=$ $1.60(\S/£)$ and $F_{0}=1.61\left(\Phi/\mathfrak{L}\right)$ and the two possible outcomes for the spot rate in December are $S_{T}=1.65$ and $S_{T}=1.50$ .  

# 19.3.2 No Hedge  

Clearly under the ‘no hedge’ scenario (Table 19.2A, column 2) if the bid is successful, UncleSam receives sterling and will gain (lose) if sterling appreciates (depreciates) – the payofs being $V S_{T}$ which are $\$20.625\mathrm{m}$ for an appreciation of sterling (to $S_{T}=1.65)$ and $\$18.75m$ for a depreciation (to $S_{T}=1.50\rangle$ . Hence, if the bid is successful, UncleSam has exchange rate risk. However, if the bid is unsuccessful there are no cash fows and no risk.  

TABLE 19.2 Foreign currency hedge (January)   


<html><body><table><tr><td>Value of bid</td><td>V = 12.5m</td></tr><tr><td>Spot rate</td><td>Sg= 1.60($/)</td></tr><tr><td>Forward rate</td><td>Fo= 1.61($/)</td></tr><tr><td>Strike price</td><td>K = 1.60($/)</td></tr><tr><td>Put premium</td><td>0.025($/)</td></tr><tr><td>Size of option contract</td><td>z = 31,250</td></tr><tr><td>Invoice price of put contract</td><td>IP = z.P = $781.25</td></tr><tr><td>Number of put contracts</td><td>Np= V/z = 12.5m/31,250 = 400 contracts</td></tr><tr><td>Total costs of put contracts in USD</td><td>Np(z.P)=Np.IP = V.P = $312,500</td></tr><tr><td>Possible outcomes for spot FX</td><td>S = 1.65($/) 0r S = 1.50($/)</td></tr></table></body></html>  

TABLE 19.2A Bid successful   


<html><body><table><tr><td>(1) Scenario</td><td>(2) No hedge</td><td>(3) Sell  in forward market at Fo = 1.61($/)</td><td>(4) Put option</td></tr><tr><td>A : S = 1.65($/) (appreciation GBP)</td><td>I =VS = (12.5m)1.65($/) = $20.625m</td><td>II = VF0 = (12.5m)1.61($/) = $20.125m Lock in Fo</td><td>S > K, hence puts not exercised Convert s at 1.65($/) Cash FX market =(12.5m)1.65($/)= $20.625m Cost of puts = $312,500 Net profit II = $20,312,500</td></tr><tr><td>B : S = 1.50($/)</td><td>I =VS (depreciation GBP) =(12.5m)1.50($/) = (12.5m)1.61($/) = $18.75m</td><td>II = VF0 = $20.125m Lock in Fo</td><td>Exercise puts Payoff = VK = (12.5m)1.60($/) Less cost of puts VP = $312,500 Net profit II = $19,687,500</td></tr></table></body></html>  

# 19.3.3 Using the Forward Rate  

UncleSam selling $\mathtt{f l}2.5\mathrm{m}$ sterling in the forward market (Table 19.2A, column 3) at $F_{0}=1.61$ implies certain USD receipts of $V F_{0}=£12.5(1.62)=\$20.125\mathrm{m}-b$ ut only if the bid is successful (Table 19.2A, column 3).  

If in January, UncleSam hedges by selling $\mathtt{f l}2.5\mathrm{m}$ sterling in the forward market at $F_{0}$ then a problem may arise if the frm fails to win the contract, next December. It will then have a naked short futures position in sterling. The US frm has agreed to sell $\mathtt{f l}2.5\mathrm{m}$ in 1 year’s time at $F_{0}$ , in exchange for receipt of $\$20.25\mathrm{m}$ .  

If the bid is unsuccessful and sterling appreciates $S_{T}>F_{0}$ , then UncleSam must purchase sterling at $S_{T}=1.65$ and sell sterling at the agreed forward rate $F_{0}=1.61$ , with a resulting loss of $\$500,000$ Table 19.2B, column 3.  

However, if the bid is unsuccessful but spot sterling depreciates to $S_{T}=1.50$ the cash infow to Uncle Sam is $V(F_{0}-S_{T})=\ensuremath{\mathtt{E}}12.5(1.61-1.50)=\ensuremath{\mathtt{S}}1.375\ensuremath{\mathrm{m}}$ . Hence:  

When the bid is unsuccessful, hedging using forwards (or futures) does not reduce risk since UncleSam has an open short position in forward sterling and will either ‘win’ (if sterling depreciates) or lose (if sterling appreciates).  

# 19.3.4 Put Options (Bid Successful)  

Now consider the risk if UncleSam buys put options on sterling and the bid is successful. If sterling appreciates the put expires worthless but UncleSam converts the $V=£12.5\mathrm{m}$ sterling  

TABLE 19.2B Bid unsuccessful   


<html><body><table><tr><td>(1) Scenario</td><td>(2) No hedge</td><td>(3) Sell  in forward market at Fg= 1.61($/)</td><td>(4) Put option</td></tr><tr><td>C : S = 1.65($/) (appreciation GBP)</td><td>No cash flows</td><td>Purchase 12.5m at S = 1.65($/f) and receive at F。= 1.61($/) I =(F-S)V = -$500,000</td><td>Put not exercised Lose put premium = VP = $312,500</td></tr><tr><td>D : S = 1.50($/f) (depreciation GBP)</td><td>No cash flows</td><td>Purchase 12.5m at S = 1.50($/) and receive at F。= 1.61($/) II = (F-S)V = -$1,375m</td><td>Purchase at S = 1.50($/) and exercise puts at K = 1.60($/) I =(K-S- P)V = $937,500</td></tr></table></body></html>  

at a ‘high’ spot rate of 1.65, giving $V S_{T}=\$20.625\mathrm{m}$ less the cost of the puts (Table 19.2A, column 4). This proft is the ‘upside capture’ of the protective put.  

$$
\begin{array}{c}{{\Pi=V(S_{T}-P)=\S20,312,500}}\\ {{V P=\S312,500}}\end{array}
$$  

When the bid is successful but sterling depreciates, the sterling receipts are worth ‘less’ in USD $(=\$123,456$ but the puts end up in-the-money with a payof $=V(K-S_{T})$ , hence:  

$$
\mathrm{Grosspayoff}=V S_{T}+V(K-S_{T})=\mathrm{VK}=1.60\:(£12.5\mathrm{m})=\mathfrak{F}20\mathrm{m}
$$  

$$
\mathrm{Profit}=V(K-P)=\S20\mathrm{m}-\S312,500=\S19,687,500\
$$  

The proft is independent of the level of $S_{T}$ . Hence, when the bid is successful and sterling depreciates, UncleSam has minimum cash infow of $\$19,487,500$ . Also if the bid is successful but sterling appreciates this allows Uncle Sam to take advantage of the high USD-GBP spot FX-rate (and the put expires worthless). In summary we have:  

# Bid successful:  

If $S_{T}>K$ puts worthless: $\Pi=V(S_{T}-P)$ upside capture If $S_{T}<K$ exercise puts: $\Pi=V S_{T}+V(K-S_{T}-P)=V(K-P)$ insurance foor  

# 19.3.5 Put Options (Bid Unsuccessful)  

If the bid is not successful UncleSam has a naked position in the long put but the most UncleSam can lose is the put premium. Hence, if sterling appreciates, the puts are not exercised but  

UncleSam’s losses are limited to the put premium: $\Pi=V P=\S312,500$ (Table 19.2B, column 4). If sterling depreciates, the put ends up in-the-money giving a net proft of:  

$$
\Pi=(K-S_{T}-P)£12.5\mathrm{m}=(1.60-1.50-0.025)\ £12.5\mathrm{m}=\S937,500.
$$  

# Bid unsuccessful:  

$$
\begin{array}{l l l}{{\textsl{1}^{>}K,\ p u t s\ a r e\ w o r t h l e s s:}}&{{\Pi=-V P}}&{{(D o w n s i d e\ l i m i t e d\ a n d\ k\nonumber}}\\ {{\textsl{I}^{<}K,\ e x e r c i s e\ p u t s:}}&{{\Pi=(K-S_{T}-P)}}&{{(P r o f t f o r S_{T}<K-P)}}\end{array}
$$  

The key diference between hedging with the put and the forward contract is that even in the worst-case scenario – when the bid is unsuccessful and sterling appreciates – the maximum loss is limited to the cost of the puts. Overall, our conclusion is that whether or not the bid is successful, the put limits downside risk but allows upside capture. But with the forward contract, if the bid is not successful, UncleSam could experience substantial losses if sterling appreciates.  

# 19.3.6 Using Futures  

Finally, for completeness, we consider the case where the frm hedges in January by selling (shorting) futures contracts. If the futures are held to maturity, the outcomes are (analytically) the same as when using the forward market.  

At maturity, the proft from the short futures position is ${V(F_{0}-F_{T})z_{f}N_{f}}$ where $z_{f}=\pm62,500$ (for sterling futures on the CME). However, to hedge the position, the number of futures contracts to short is $N_{f}=V/z_{f}$ so the proft from the short futures position is simply $V(F_{0}-F_{T})$ . Furthermore, at maturity of the futures $F_{T}=S_{T}$ , so the cash proft from the futures position at maturity is $V(F_{0}-S_{T})$ .  

If the bid is successful, then net receipts at maturity in USD are $V S_{T}+V(F_{0}-S_{T})=V F_{0}$ . If the bid is unsuccessful, net receipts are $V(F_{0}-S_{T})$ . These results are the same as those obtained when using forward contracts. If the short futures position is closed out at $t=1$ (before maturity), then the story is a little more complex. UncleSam’s USD receipts are:  

$$
\begin{array}{r l}{\mathbf{Bid~successful}\quad}&{\Pi=V S_{1}+V(F_{0}-F_{1})=V[F_{0}+(S_{1}-F_{1})]}\\ {\mathbf{Bid~unsuccessful}\quad}&{\Pi=V(F_{0}-F_{1})}\end{array}
$$  

If basis risk $(=S_{1}-F_{1})$ is small, the cash fow if the bid is successful will be close to ${V F}_{0}$ , which is the same as we obtained for the forward contract. If the bid is unsuccessful, the proft from the short futures position ${}={\cal V}(F_{0}-F_{1})$ . This will be close to the outcome for the forward contract if the futures contract is closed out near its maturity date (i.e. $F_{1}=F_{T}=S_{T}\mathrm{.}$ ). In practice, the latter is usually the case.  

# 19.4 OTHER CURRENCY OPTIONS  

Some of the more complex currency options come under the heading of ‘exotic options’. Consider, for example, a type of barrier option known as a ‘down-and-in’ (at-the-money, $S_{0}=K)$ call option, with a lower barrier $L<K$ . This ‘down-and-in’ call option only ‘comes alive’ when the spot FX rate at any time $t\left(<T\right)S_{t}$ falls below the lower barrier $L$ , set in the option contract. Hence, there is a positive payof at maturity to the long call if $S_{T}>K$ , as long as the exchange rate has fallen below the lower barrier (i.e. $S_{t}<L\dot{}$ ), before the maturity date of the option. If $S_{T}>K$ , but the exchange rate has never fallen below the lower barrier, then the payof at maturity to the long call is zero. Hence the payofs to the down-and-in call are less favourable than for a plain vanilla call and this is refected in the lower call premium for the down-and-in call (see Chapter 31).  

There are also FX options whose payof is based on the average value of the spot-FX rate (e.g. USD-GBP) over the life of the option. These are known as Asian FX options and can be used by a corporate to hedge a series of future foreign cash infows or outfows each month, over a period of a year (say). The Asian option is cheaper than buying a series of plain vanilla options, each of which has an expiration date at the end of each month.  

Also, a useful option for a US multinational corporation, UncleSam, which has net cash infows or outfows in a number of diferent foreign countries is a basket option, sold in the OTC market. Here the payof is denominated in dollars using the FX-rate on a basket of currencies. For example, if UncleSam has net cash infows in many diferent currencies then it can guarantee minimum receipts of USDs by buying put options on each separate currency – but this could be expensive. However, if FX-rates on diferent currencies are not perfectly correlated then the volatility of a ‘basket of currencies’ will be less than the sum of the volatilities of the individual currencies. From Black–Scholes we know that option premia (on calls and puts) are positively related to the volatility of the ‘underlying asset’ in the option contract. Hence, a ‘basket’ FX put option will have a premium which is less than the sum of the premia for the individual plain vanilla put options, on each separate currency.  

# 19.5 SUMMARY  

• Traded foreign currency options, both European and American style, are available (OTC) for all major currencies against the US dollar. There are also a (smaller) number of contracts on cross-rates (e.g. Euro-GBP and Euro-Yen). The OTC market is very active since contracts can be ‘structured’ to suit clients’ needs as regards contract size, maturity date, currencies etc.   
• Foreign currency options provide leverage when used for speculation and the usual types of options strategies (e.g. straddles, straps, spreads) on a spot FX rate are possible by combining currency options with diferent strikes (but the same expiration dates and currency).   
• A US frm with known future receipts in sterling (e.g. from sales in the UK) can ‘lock in’ known USD receipts, by today shorting (selling) forwards or futures on sterling. However, if the future sterling receipts do not materialise (e.g. are not paid), then the ‘naked’ short forward/futures position will result in a gain if sterling appreciates and a loss if sterling depreciates. The forward/futures hedge is therefore ‘risky’, if future sterling cash fows are uncertain.   
• Foreign currency options are useful for when future foreign currency receipts or payments are uncertain. If a US frm has uncertain future sterling receipts then buying a foreign currency put option on sterling today, provides a known minimum receipt in USD (o $\mathsf{f}K-P)$ , while allowing upside potential (should sterling appreciate), regardless of whether the future sterling receipts are received or not. If the sterling receipts do not materialise the most that can be lost is the put premium (times the number of puts purchased).  

# EXERCISES  

# Question 1  

Explain the key items in the following quotes for calls and puts on sterling (GBP). The contract size is for delivery of GBP31,250 and the options expire on 28 September. Assume the options are European.  

<html><body><table><tr><td colspan="4">f31,250 British Pound. Cents per unit (19 August)</td></tr><tr><td>British pound Spot FX rate</td><td>Strike</td><td>Calls (28 Sept)</td><td>Puts (28 Sept)</td></tr><tr><td>160.60</td><td>164</td><td>0.48</td><td>4.14</td></tr></table></body></html>  

# Question 2  

A US exporter expects to receive £1m (GBP) in 1 year’s time. The current spot FX rate is $S_{0}=$ $1.1\S/£$ (USD/GBP). What type and how many options will the US exporter require to cover her position and set a minimum value for the FX rate of 1.1 USD/GBP in 1 year’s time? Contract size is for delivery of GBP 31,250.  

# Question 3  

It is January. You are a US portfolio manager, holding $\epsilon20\mathrm{m}$ in stocks in 25 large European companies and these stocks are likely to be sold in 6 months’ time (in July). You predict that the Euro spot-FX rate is likely to fall from its current level of $S_{0}=1.20$ against the USD over the next 6 months (because of the interest rate policy of the European Central Bank). You need a currency strategy that will be benefcial if your prediction is correct but will not lead to large losses if you are incorrect. Discuss the relative merits of using either a European FX option (with $K=1.10$ USD/Euro) or an FX futures contract to achieve your aims. Assume the spot FX rate in 6 months’ time turns out to be either 1.15 or 1.0. Note any risks in your strategy.  

# Question 4  

It is 12 December and a US exporter expects to receive $\mathsf{\epsilon}0.5\mathrm{m}$ from the sale of Barbie dolls in Germany, and payment will arrive in March. The March-102 put contract on euros has a premium of 6.0 (cents per euro) and the current spot rate is $S_{0}=100$ (cents per euro). The contract size is \$62,500. What is the hedged/insured position using puts with a strike of $K=102$ cents/euro? What is the outcome if the spot FX rate in 3 months is $\begin{array}{r}{S_{T}>K}\end{array}$ or $S_{T}<K$ .  

Question 5 On 26 September you are faced with the following quotes for December calls and puts on the Philadelphia Stock Exchange for options on sterling (GBP).   


<html><body><table><tr><td>B. Pound GBP</td><td>Strike price</td><td>Calls (December)</td><td>Puts (December)</td></tr><tr><td>144</td><td>140</td><td>5.10</td><td></td></tr><tr><td>144</td><td>145</td><td>-</td><td>2.5</td></tr></table></body></html>

All quotes are in cents per GBP. The current spot rate is $S=144$ US cents/GBP. Contract size $=\yen31,250$ .  

Draw the payof/proft profle for a long call and a long put taken individually, indicating the breakeven spot FX rate at expiry.  

Question 6 On 26 September you are faced with the following quotes for December calls and puts on the Philadelphia Stock Exchange for options on sterling (GBP).   


<html><body><table><tr><td>B. Pound GBP</td><td>Strike price</td><td>Calls (December)</td><td>Puts (December)</td></tr><tr><td>144</td><td>140</td><td>5.10</td><td>-</td></tr><tr><td>144</td><td>145</td><td></td><td>2.5</td></tr></table></body></html>

All quotes are in cents per GBP. The current spot rate is $S=144$ US cents/GBP. Contract size $\mathtt{\Omega}=\mathtt{f}31,250$ .  

You purchase one call and one put on GBP, with the above strikes. Calculate the payof and proft outcomes at expiration, when the spot FX rate ends up (i) below 145, (ii) between 140 and 145, and (iii) above 140.  

What is the general shape of the payof to the long call and put (with the above strikes)? What strategy have you implemented and under what circumstances does it give a positive proft?  

# Question 7  

In 6 months’ time a US frm has to pay for imports from Germany of either $\epsilon2\mathrm{m}$ or $\epsilon3\mathrm{m}$ (depending on the amount of imports delivered). What are the advantages and disadvantages of hedging with FX-futures? Consider the outcomes if the US frm decides to cover $\epsilon3\mathrm{m}$ but only $\epsilon2\mathrm{m}$ are required to pay for imports and consider the outcome if either the euro appreciates or depreciates over the next 6 months.  