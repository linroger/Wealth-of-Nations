---
tags:
  - arbitrage
  - cme
  - derivative_securities
  - forward_contracts
  - futures_contracts
  - hedging
  - interest_rate_swaps
  - options
  - short_selling
  - speculation
aliases:
  - Derivatives
  - Forward Contracts
  - Futures
  - Options
  - Swaps
key_concepts:
  - Call and put options
  - Derivative securities
  - Futures and forwards
  - Hedging and arbitrage
  - Interest rate swaps
---
# Derivative Securities

# Aims

• To explain forward and futures contracts, their similarities and diferences.
• To examine the basic concepts behind call and put options and how their payofs at maturity can provide ‘insurance’.
• To show how interest rate swaps can be used to alter the cash fow profle of uncertain payments or receipts, and hence reduce the risk attached to such cash fows.
• To analyse how derivative securities are used in speculation, hedging and arbitrage.
• To explain short-selling.

There are three main types of derivative securities, namely futures, options and swaps. Derivative securities are assets whose price depends on the price of some other (underlying) asset. Hence the derivatives price is derived from the price of this underlying asset.

For example, lets assume a futures contract on AT&T stocks is traded on the Chicago Mercantile Exchange (CME). The underlying asset in the futures contract is the stock of AT&T itself, which is traded on a diferent exchange, namely the New York Stock Exchange (NYSE). The price of the stock on the NYSE is for immediate delivery of the stock, and is known as the spot or cash market price. In contrast, today’s futures price (on AT&T stock) quoted in Chicago is a price quote for delivery of AT&T stock (in Chicago) at a specifc date in the future. However, we can show that the AT&T futures price (in Chicago) is (largely) determined by the stock price of AT&T (quoted on the NYSE). If AT&T’s stock price changes on the NYSE by $\$1$ (in the next few seconds) then the AT&T futures price will also immediately change by about $\$1$ on the Chicago futures exchange – even though the two markets are separated by around $1,000\mathrm{km}$ . The tight link between the spot/cash market price of AT&T in New York and the AT&T futures price in Chicago is due to a process known as (risk-free) arbitrage.

Derivatives are used by hedgers, speculators and arbitrageurs. Derivatives often receive a ‘bad press’, in part because there have been some quite spectacular derivatives losses. For example, in 1994 Nick Leeson, who worked for Barings Bank in Singapore, lost $\$1.45\mathrm{n}$ when trading futures and options on the Nikkei 225, the Japanese stock index. This led to Barings going bust. In 1998, Long Term Capital Management (LTCM), a hedge fund which leveraged its trades using derivatives, had losses of over $\$4b n$ and had to be rescued by a consortium of banks under the imprimatur of the Federal Reserve Board. This was somewhat ironic since Myron Scholes and Robert Merton, two academics who received the Nobel Prize for their work on derivatives, were key players in the LTCM debacle. Derivatives are a bit like nuclear fssion – they can be used in ‘good ways’ (like low cost, low carbon electricity from nuclear power) or in ‘bad ways’ (like nuclear bombs) – if used incorrectly they may become ‘fnancial weapons of mass destruction’ – to quote Warren Bufett (2002). Let us now examine how derivatives are used in practice, so that you can begin to make up your own mind on this issue.

# 1.1 FORWARDS AND FUTURES

Forward and futures contracts are analytically very similar, although the way the two contracts are traded difer in some respects. A holder of a long (short) forward contract has an agreement to buy (sell) an asset at a certain time in the future for a certain price which is fxed today.

The buyer (seller or short position) in a forward contract:

• acquires a legal obligation to buy (sell) an asset (the underlying) • at some specifc future date (maturity/expiry date) • in an amount (contract size) • and at a price (the forward price) which is fxed today.

A forward contract is an over-the-counter (OTC) instrument, and trades take place directly between the buyer and seller as negotiated between the two parties (usually over the phone) for a specifc amount and specifc delivery date.

Originally, forward (and futures) markets were introduced to eliminate risk due to changes in the spot (cash market) price of agricultural commodities. For example, a farmer might know in April that he will harvest 5,000 bushels of wheat in September. A wholesaler who purchases grain for use in the food industry might know their requirements for wheat in September, as early as April. The two participants can eliminate (or hedge) risk by negotiating a contract to supply 5,000 bushels of grain in September at a price which is agreed in April – so the September-forward price is agreed in April but will not be paid until September, when the grain is delivered.

The forward contract (if held to maturity) eliminates risk for each side of the bargain. Both sides of the deal are ‘locked in’ to the forward price (of the September contract) quoted in April and thereby remove any ‘price risk’. This is a ‘natural hedge’ since both sides of the deal wish to ‘lock in’ a known forward price, quoted today, for delivery of wheat at a specifc date (and location) in the future. If, when we get to September, the spot/cash market price of wheat (for immediate delivery) is very high or very low, this is of no consequence, since both parties to the forward contract have agreed to exchange wheat in September at the pre-agreed forward price.

If a futures contract on wheat is held to maturity then delivery of the underlying asset (wheat) takes place at the pre-agreed futures price and under these circumstances the futures contract is the same as a forward contract. Theoretically the quoted forward and futures prices will be the same if they are entered into at the same time (and with the same maturity date). Although futures contracts are very similar analytically to forward contracts, they do difer in certain practical aspects.

In a forward contract the terms in the contract (e.g. delivery quantity, delivery date, etc.) are ‘tailor made’ between two traders (a buyer and seller) whereas the terms of a futures contract are standardised (e.g. delivery quantity, delivery point, delivery dates, etc.). Also, trading in futures contracts takes place on an organised exchange, rather than over-the-counter as with forward contracts.

Consider wheat. The physical commodity wheat can be bought and sold for (near) immediate delivery in the spot (cash) market for wheat. When you buy or sell a futures contract on wheat, it is the ‘legal right’ to the terms in the futures contract that is being purchased or sold – you do not immediately receive the physical commodity ‘wheat’ when you buy a wheat futures contract. However, as we shall see, there is a close link between the futures price of wheat and the spot price for wheat but they are not the same thing – the spot price and the futures price are quoted in two diferent markets.

Futures contracts are traded between market makers in a ‘pit’ on the foor of the exchange, of which the largest are the Chicago Board of Trade (CBOT) and the Chicago Mercantile Exchange (CME) – which merged to form the CME Group in 2007. However, in recent years there has been a move away from trading by ‘open outcry’ in a ‘pit’ towards electronic trading between market makers (and also over the internet). The largest ‘pit trading’ futures exchange in Europe was the London International Financial Futures Exchange (LIFFE), which has now merged and become NYSE-Euronext – an electronic trading platform. You can also trade ‘out-of-hours’ in many futures contracts using the GLOBEX electronic trading platform. Some futures contracts that are traded on US exchanges are shown in Table 1.1.

# 1.1.1 Market Classification

A key feature of a futures contract is that it involves deferred delivery of the underlying asset (e.g. wheat, AT&T stocks), whereas spot (cash market) assets are for immediate delivery (although in practice, there is usually a delay of a few days). A primary use of derivative securities is to minimise price uncertainty. Therefore, where the underlying assets (e.g. currencies, stocks, oil, agricultural produce) are widely traded and yet their spot prices exhibit great volatility, there is likely to be a large active derivatives market.

TABLE 1.1 Selected futures contracts


<html><body><table><tr><td>Contract</td><td>Exchange</td><td>Contract size</td></tr><tr><td>1. Metals and petroleum</td><td></td><td></td></tr><tr><td>Gold</td><td>CME Group (COMEX)</td><td>100 troy oz</td></tr><tr><td>Silver</td><td>CME Group (COMEX)</td><td>5,000 troy oz</td></tr><tr><td>Crude oil</td><td>CME Group (NYMEX)</td><td>1,000 barrels</td></tr><tr><td>Natural gas</td><td>CME Group (NYMEX)</td><td>10,000 mm Btu</td></tr><tr><td>2. Agricultural</td><td></td><td></td></tr><tr><td>Corn</td><td>CME Group (CBOT)</td><td>5,000 bu</td></tr><tr><td>Lean hogs</td><td>CME</td><td>40,000 Ibs</td></tr><tr><td>Pork bellies</td><td>CME</td><td>40,000 Ibs</td></tr><tr><td>Frozen orange juice</td><td>ICE</td><td>15,000 Ibs</td></tr><tr><td>3. Foreign currency</td><td></td><td></td></tr><tr><td>British pound</td><td>CME</td><td>62,500</td></tr><tr><td>Swiss franc</td><td>CME</td><td>SFr125,000</td></tr><tr><td>Euro</td><td>CME CME</td><td>125,000</td></tr><tr><td>Japanese yen</td><td></td><td>¥12.5m</td></tr><tr><td>4. Stock indices</td><td></td><td></td></tr><tr><td>S&P 500</td><td>CME Group (CBOT)</td><td>$250 × Index</td></tr><tr><td>FTSE 100</td><td>NYSE-Euronext</td><td>10 × Index</td></tr><tr><td>Eurotop 100</td><td>NYSE-Euronext</td><td>20 × Index</td></tr><tr><td>Nikkei 225</td><td>CME Group (CBOT)</td><td>$5 × Index</td></tr><tr><td>5. Interest rates</td><td></td><td></td></tr><tr><td>Eurodollar - 90 days</td><td>CME Group (IMM)</td><td>$1,000,000</td></tr><tr><td>US T-bills</td><td>CME Group (IMM)</td><td>$1,000,000</td></tr><tr><td>US T-bonds</td><td>CME Group (CBOT)</td><td>$100,000</td></tr><tr><td>UK 3-month Euro LIBOR</td><td>NYSE-Euronext</td><td>100,000</td></tr><tr><td>UK Long Gilt Futures</td><td>NYSE-Euronext</td><td>1,000,000</td></tr></table></body></html>

Note: CBOT $\mathbf{\Sigma}=\mathbf{\Sigma}$ Chicago Board of Trade (part of CME Group), CME $\mathbf{\Sigma}=\mathbf{\Sigma}$ Chicago Mercantile Exchange, $\mathsf{I M M}=$ International Money Market (Chicago, part of CME Group), NYSE-Euronext (previously London International Financial Futures Exchange, LIFFE).

Trading in derivative securities can be on a trading foor (or ‘pit’) or via an electronic network of traders, within a well-established organised market (e.g. with a clearing house, membership rules, etc.). However, many derivatives contracts – for example, all FX-forward contracts and swap contracts – are traded in OTC markets, where the contract details are not standardised but individually negotiated between clients and dealers. Options are traded widely on exchanges but the OTC market in options (particularly ‘complex’ or ‘exotic’ options) is also very large.

Today there are a large number of exchanges which deal in futures contracts. Most can be categorised as either agricultural futures contracts (where the underlying ‘asset’ is, for example, pork bellies, live hogs or wheat), energy futures (e.g. crude oil, natural gas, heating oil), metallurgical futures (e.g. silver, platinum) or fnancial futures contracts (where the underlying asset could be a portfolio of stocks represented by the S&P 500, currencies, T-bills, T-bonds, Eurodollar Deposits, etc.). Agricultural, energy and metallurgical futures are often generically referred to as ‘commodity futures’. There are some futures contracts that do not really ft into any of these defnitions, such as weather futures – which we meet later.

Futures contracts in agricultural commodities have been traded (e.g. on the CBOT) for over 100 years. In 1972 the CME began to trade currency futures, the introduction of interest rate futures occurred in 1975 and in 1982 stock index futures (colloquially known as ‘pinstripe pork bellies’) were introduced. The CBOT introduced a clearing house in 1925, where each party to the contract had to place ‘cash deposits’ into a margin account. The latter provides insurance if one of the parties defaults on the futures contract.

Analytically, forwards and futures can be treated in a similar fashion. However, they difer in some practical details (see Table 1.2). Forward contracts (usually) involve no ‘up front’ payment and ‘cash’ only changes hands at the maturity of the contract. A forward contract is negotiated between two parties and (generally) is not marketable. In contrast, a futures contract is traded in the futures market (in Chicago)1 and when initiated, traders have to provide a cash deposit known as the initial margin. However, the initial margin is merely a form of collateral to ensure both parties can fulfl the terms of the futures contract – it is not a payment for the futures contract itself and it is not the ‘futures price’. The margin usually earns a competitive interest rate so it is not a ‘cost’. As the futures price changes then ‘payments’ (i.e. debits and credits) are made into (or out of) the margin account. Hence a futures contract is a forward contract that is ‘marked-to-market’, daily.

TABLE 1.2 Forward and futures contracts


<html><body><table><tr><td>Forwards</td><td>Futures</td></tr><tr><td>Private (non-marketable) contract between two parties</td><td>Traded on an exchange</td></tr><tr><td>(Large) trades are not communicated to other market participants</td><td>Trades are immediately known by other market participants</td></tr><tr><td>Delivery or cash settlement at expiry</td><td>Contract is usually closed out prior to maturity</td></tr><tr><td>Usually one delivery date</td><td>Range of maturity dates</td></tr><tr><td>No cash paid until expiry</td><td>Cash payments into (out of) margin account, daily</td></tr><tr><td>Negotiable choice of delivery dates and size of contract</td><td>Standardised contracts</td></tr></table></body></html>

Because the futures contract is marketable, the contracts have to be standardised – for example, by having a set of fxed delivery dates and a fxed ‘contract size’ (e.g. 1,000 barrels of oil for the oil futures contract or $\$100,000$ for the US T-bond futures contract). In contrast, a forward contract can be ‘tailor made’ between the two parties, in terms of size and delivery date. Finally, forward contracts almost invariably involve actual delivery of the underlying asset (e.g. currency) whereas futures contracts can be (and usually are) ‘closed out’ prior to maturity which cancels any delivery obligations.

Forward contracts can be used for speculation. First, consider a speculator who on 1 April thinks the gold (spot) price will be high in September. On 1 April she therefore ‘buys’ (‘goes long’) a September-forward contract on gold, but does not pay any cash on 1 April. If the spot price of gold rises (falls), the speculator will make a gain (loss) on the forward contract at the time the contract matures in September.

For example, suppose on 1 April $\overset{\cdot}{t}=0\overset{\cdot}{\underset{\cdot}{\mathrm{~\rightmoon~}}}$ ) the quoted spot (‘cash-market’) price of gold is $S_{0}=\$1,000$ per oz and the gold forward price quoted in Chicago (for delivery in September, $T)$ is $F_{0}=\$1,010$ per oz. Assume the speculator is correct and the spot (cash market) price for gold in September $(T)$ turns out to be higher at $S_{T}=\mathfrak{H}1,200$ per oz. The speculator holding the (‘long’) forward contract can take delivery of the ‘physical’ gold (in the forward contract, in Chicago) for which she pays $F_{0}=\$1,010$ in September. But she can now immediately sell the gold in the spot/cash market for $S_{T}=\$1,200$ , giving an overall proft of $\$190$ per contract $(=S_{T}-F_{0})$ .

Now consider speculation using futures contracts, which can be closed out at any time before maturity. Most futures contracts are closed out prior to maturity and when they are, the clearing house (CH) in Chicago sends out a cash payment which refects the change in the futures prices between the opening trade and closing out the contract (i.e. a buy followed by a sell, or vice versa). Therefore futures contracts can be used for speculation over very short time horizons. Remember that the futures price moves (approximately) dollar-for-dollar with changes in the price of the underlying spot (‘cash-market’) asset. If you think the futures price will rise (fall) then today a speculator will buy (sell) a futures contract.

Suppose on 15 June you purchased a September-futures contract on stock-XYZ at a price $F_{0}=\$100$ and one week later on 22 June you closed out the contract by selling it at its new price of $F_{1}=\$110$ .2 Then the CH ‘efectively’ sends you a cheque for $\$10$ – the diference between your buying price and selling price. Simplifying a little, the CH obtains this $\$10$ from the person who initially sold the contract to you at $\$100$ and is now buying it back at $\$110$ – if you have gained $\$10$ then the ‘other side of the contract’ must have lost $\$10$ . It also follows that a speculator would earn a $\$10$ proft if she initially sold a contract at $F_{0}=\$100$ and later closed out the contract by buying it back at a lower price of $F_{1}=\$90$ (i.e. ‘sell high, buy low’). The diferent types of futures contracts that can be traded is almost limitless but only those which are useful for hedging and speculation will continue to be traded. The exchange will cease to trade any futures contracts where the trading volume is below a certain threshold.

# 1.2 OPTIONS

Options are a little more di\$cult to understand than forwards and futures and here we present a quick introductory overview. While futures markets in commodities have existed since the middle of the 1800s, options contracts have been traded for a shorter period of time. There are two types of option, calls and puts:

The holder of a call (put) option has the right (but not an obligation) to buy (sell) the ‘underlying asset’ at some time in the future (‘maturity date’) at a known fxed price (the ‘strike price’, K) but she does not have to exercise this right.

Table 1.3 provides a summary of several types of option contract and the assets underlying these contracts.

TABLE 1.3 Selected option contracts


<html><body><table><tr><td>Options contract</td><td>Exchange</td><td>Contract size</td></tr><tr><td>1. Individual stocks (Stock options)</td><td>CBOE, NASDAQ PHLX, NYSE-Euronext</td><td>Usually for delivery of 100 stocks</td></tr><tr><td>2. Stock indexes (Index options)</td><td></td><td></td></tr><tr><td>S&P 500 (SPX)</td><td>CBOE</td><td>$100 x Index</td></tr><tr><td>FTSE 100</td><td>NYSE-Euronext</td><td>10 × Index</td></tr><tr><td>S&P 100 Index (OEX)</td><td>CBOE</td><td>$100 x Index</td></tr><tr><td>3. Foreign currency</td><td></td><td></td></tr><tr><td>British pound</td><td>NASDAQ PHLX</td><td>31,250</td></tr><tr><td>Japanese yen</td><td>NASDAQ PHLX</td><td>¥6.25m</td></tr><tr><td>Canadian dollar</td><td>NASDAQ PHLX</td><td>C$50,000</td></tr><tr><td>Swiss franc</td><td>NASDAQ PHLX</td><td>SFr62,500</td></tr><tr><td>4. Futures Options</td><td></td><td></td></tr><tr><td>S&P 500 Futures Index</td><td>CME</td><td></td></tr><tr><td>US T-bill Futures</td><td>CME Group (IMM)</td><td></td></tr><tr><td>US T-bond Futures</td><td>CME Group (IMM)</td><td></td></tr></table></body></html>

Note: CBOE $\mathbf{\Sigma}=$ Chicago Board Options Exchange, CME $\mathbf{\Sigma}=\mathbf{\Sigma}$ Chicago Mercantile Exchange, $\mathsf{I M M}=$ International Money Market (Chicago, part of CME Group), NYSE-Euronext (previously London International Financial Futures Exchange, LIFFE). PHLX $\mathbf{\sigma}=\mathbf{\sigma}$ Philadelphia Stock Exchange (part of NASDAQ).

For the moment we consider stock option contracts, so the underlying asset in the option contract is the stock of a particular company-XYZ which is traded on the NYSE. The option contract itself, we assume is traded in Chicago.

Above we noted that the holder of a long futures contract on a stock-XYZ commits herself to buy the stock at a certain price at a certain time in the future and if she does nothing before the maturity date, she will have to take delivery of stock-XYZ, at the pre-agreed futures price. In contrast, the holder of a (European) ‘call option’ on stock-XYZ can decide whether to pay the known strike price and take delivery of stock-XYZ on the maturity date of the option contract – this is called ‘exercising the option contract by taking delivery’. If it is advantageous not to exercise the option (in Chicago) then the holder of the call option will simply do nothing. For the privilege of being able to decide whether or not to take delivery of stock-XYZ (at maturity of the option contract) the buyer of the call option must pay an upfront, non-refundable fee – the option price (or premium).

The holder of a European call option can ‘exercise the option’, that is, take delivery and buy the stock-XYZ in Chicago for $K$ – only on the maturity date (expiration date) of the option contract. But the holder of an American call option can ‘exercise the option’ contract in Chicago on any day (up to and including the maturity date).3 Below, we deal only with European options.

Note, however, that any option contracts you hold (whether American or European) can be sold to a third party, at any time prior to expiration – this is known as trading and allows closing out the option contract. If you ‘close out’ your call (or put) option contract then delivery (to you) of the underlying asset in the option contract, will not take place.

# 1.2.1 Call Options

If today you buy a European call option and pay the call premium/price, then this gives you the right (but not an obligation):

• to purchase the underlying asset
• at a designated delivery point
• on a specifed future date (known as the expiration or maturity date) • for a fxed known price (the exercise or strike price)
• and in an amount (contract size) which is fxed in advance.

For the moment, think of a call option as a ‘piece of paper’ that contains the contract details (e.g. strike price, maturity date, amount, delivery point, type of underlying asset). You can purchase this contract today in the options market in Chicago if you pay the quoted call premium. There are always two sides to every trade – a buyer and a seller – but we will concentrate on your trade, as a buyer of the option. Note that all transactions in the option contract are undertaken in Chicago but the underlying asset, for example a stock, is traded on another exchange (e.g. NYSE).

TABLE 1.4 Leverage from options


<html><body><table><tr><td></td><td>Chicago (options market)</td><td>NYSE (cash market)</td></tr><tr><td rowspan="2">15 July</td><td>Call premium, C = $3</td><td>Spot price, Sg = $80</td></tr><tr><td>Strike price, K = $80</td><td></td></tr><tr><td rowspan="3">25 October</td><td>Payoff = $8 = ($88 - $80)</td><td>Spot price, S = $88</td></tr><tr><td>Profit = $5 = ($8 - $3)</td><td>Profit = $8 = ($88 - $80)</td></tr><tr><td>Returns = $5/$3 = 167%</td><td>Return = $8/$80 = 10%</td></tr></table></body></html>

Suppose the current price of stock-XYZ on the NYSE on 15 July is $S_{0}=\$80$ . On 15 July you can pay the call premium $C=\$3$ and buy (in Chicago) an October-European call option on the stock-XYZ. The strike price in the contract is $K=\$80$ ,4 and the expiry date $T$ is in just over 3 months’ time on 25 October. Because the maturity of the call is in October, and the strike is $K=\$80$ , it is known as the ‘October-80 call’ (Table 1.4). Assume each call option is for delivery of one stock of XYZ.

# 1.2.2 Long Call: Speculation

How might a speculator use this call option contract? As we shall see, the speculator will buy the call option if she thinks stock prices will increase (su\$ciently) in the future and end up above the strike price, $K$ (on the option’s maturity date). If stock prices do increase (su\$ciently) then the speculator will make a proft when she exercises the call option (on 25 October, its maturity date).

For example, if the stock price on 25 October (on the NYSE) turns out to be $S_{T}=\$88$ , then the holder of the call option can ‘present’ (i.e. exercise) the option contract in Chicago on 25 October (the maturity date of the option), pay the strike price $K=\$80$ and receive one stock. This is exercising the option by taking delivery. She could then immediately sell the stock on the NYSE for $S_{T}=\$88$ , making a cash proft on 25 October equal to $S_{T}-K=\S88-\S80=\S8$ . Alternatively, the long call option can be ‘cash settled’ for $S_{T}-K=\$8$ which is paid via the clearing house in Chicago (and no stock is delivered). In either of these scenarios (i.e. delivery or cash settlement) the option’s speculator has made $\$8$ on an initial outlay of ‘own funds’ of $C=\$3$ , which is a percentage return of $[(8-3)/3\times100\%]=167\%$ (over a 3-month period).

Had the speculator bought the stock itself (with her ‘own funds’) for $\$80$ and then sold at $S_{T}=\$88$ , she would have made a percentage return of $10\%$ (i.e. $\$8$ on an initial outlay of $\$80$ ).

The much larger percentage return when using the call option arises because you can purchase the option for the relatively small payment of $\$3$ , whereas the stock costs you $\$80$ . The higher percentage return from the option (relative to the percentage return from buying the stock with your ‘own funds’) is called leverage – here, a $10\%$ increase in the stock price gives rise to a $167\%$ return on the option strategy.

If the stock price on 25 October turns out to be $S_{T}=\$75$ which is less than the strike price $K=\$80$ then the option is not worth exercising – after all, why pay $K=\$80$ for delivery of stock-XYZ in Chicago, when XYZ is only worth $S_{T}=\$75$ on the NYSE. In this case the option on 25 October is worth zero and the speculator ‘throws it away’ (i.e. does not present/exercise the option in Chicago). Note, however, that no matter how low the stock price turns out to be on 25 October, the maximum amount the option’s speculator can lose is known in advance and is equal to the call premium $C=\$3$ .

So a speculator who buys a call option has some rather nice advantages – she can beneft substantially from any upside in the stock market but can never lose more than the (rather small) option premium of $\$3$ she initially paid, even if stock prices fall to zero. Contrast this with buying the stock on 15 July for $S_{0}=\$80$ on the NYSE – this might lead to a maximum loss of $\$80$ , if company-XYZ entered bankruptcy before 25 October.

# 1.2.3 Closing Out

When a speculator buys a call option she can make a proft if the stock price increases at any time before the maturity date of the option. She does this by selling (shorting) the call option to another options trader, after the stock price has increased – this is called ‘closing out’ (or ‘reversing’) her initial long position in the option. The speculator is able to make a proft because when stock-XYZ increases in price on the NYSE then this results in a rise in the call premium (on XYZ) in Chicago. For example, if stock-XYZ increases in price by $\$2$ over one day then the price of the call option (quoted in Chicago) may increase from say $\$3$ to $C_{1}=\$4$ , over one day. Hence the speculator who purchased the October-call for $\$3$ on 15 July, can now sell the call in Chicago on 16 July (to another options trader) for $\$4$ . The speculator actually receives her $\$4$ from closing out the contract, via the options clearing house in Chicago. She therefore makes a speculative proft of $\$1$ $(=\$4-\$3)$ , the diference between the buying and selling price of the call – a return of $33\%$ $(=\$1/\$3)$ over one day.

Conversely, after the speculator purchased the October-call for $C_{0}=\$3$ , on 15 July, if the stock price falls by $\$1$ (say) on the NYSE, then the October-call premium will fall to $\$2.2$ (say) and when she sells it to another trader (i.e. closes out) in Chicago, the options speculator will make a loss of $\$0.8$ on the deal (but she will never lose more than the initial option premium of $\$3$ ). Thus a naked (or open) position in a long call is risky.

# 1.2.4 Put Options

If you buy a European put option (in Chicago) this gives you the right to sell the underlying asset (in Chicago) at some time in the future, for a price which is fxed in the contract.

If today you buy a European put option and pay the put premium/price, then this gives you the right (but not an obligation):

• to sell the underlying asset at a
• specifed future date (the expiration/maturity date) at a • designated delivery point
• for a known fxed price (strike/exercise price)
• in an amount (contract size) which is fxed in advance.

# 1.2.5 Long Put: Speculation

A put option can be used for speculation. In contrast to speculation with a long call, a speculator will buy (‘go long’) a put option if she expects the stock price to fall in the future (and end up below the strike price). Suppose on 15 July the stock price for company-XYZ is $S_{0}=\$72$ on the NYSE and a speculator thinks the stock price will fall in the future. Assume the speculator is not going to gamble on the price fall by using stock-XYZ, itself. Instead, on 15 July the speculator buys (in Chicago) a European ‘October-put’ (expiry date is 25 October) with a strike price $K=\$70$ for a put premium paid of $P=\$2.2$ .

Suppose the spot price of stock-XYZ on the NYSE on 25 October is $S_{T}=\$65$ (i.e. below $K=\$70$ ). Then on 25 October the speculator can purchase stock-XYZ on the NYSE for $S_{T}=\$65$ and then immediately ‘deliver’ stock-XYZ in Chicago along with the put contract and receive $K=\$70$ , given the terms in the put contract. The options speculator makes a proft of $(K-S_{T})=\S70-\S65=\S5$ on 25 October. Alternatively, the speculator can simply ‘cash settle’ the long put contract, in which case the options clearing house makes a cash payment of $(K-S_{T})=\$5$ when the long put is ‘cash settled’ on 25 October (and the holder of the long put does not have to deliver stock-XYZ).

In either of the above cases the speculator who is long the put, receives $\$5$ on 25 October. The speculator’s initial outlay was the put premium of $P=\$2.2$ paid on 15 July. The speculator by using the (long) put contract to speculate on a future stock price fall, has made a percentage return of $127\%$ $(=[(5-2.2)/2.2]100\%)$ , over a 3-month period. The fall in the stock price is $9.7\%[=(S_{T}-S_{0})/S_{0}=(65-72)/72]$ . But the percentage return from investing in the long put (and exercising the put at maturity) is much larger at $127\%$ . Hence, buying the put option for $P=\$2.2$ has provided a leveraged return for the speculator.

If the spot price of stock-XYZ on the NYSE on 25 October turns out to be higher than the strike price (e.g. $S_{T}=\$73$ , $K=\$70$ ) then the put option will not be exercised. Why would a speculator who holds the put, buy the stock for $\$73$ on the NYSE on 25 October, if she could then only obtain $K=\$70$ by delivering the stock and exercising her put contract in Chicago? The put option is therefore worth zero on 25 October and the speculator ‘throws it away’ (i.e. does not exercise the option). But the most the speculator with a long put can lose is the put premium of $P=\$2.2$ . So a speculator who is long a put option can beneft from a su\$- ciently large fall in the price of stock-XYZ – but if she guesses wrong and the stock price rises, she can never lose more than the (rather small) put premium initially paid.

# 1.2.6 Long Put plus Stock: Insurance

Options can also be used to provide insurance. For example, suppose you run a pension fund and already own stocks whose current price on 15 July (on NYSE) is $S_{0}=\$72$ . But you are worried about a fall in price of the stocks between now and 25 October when your stocks will be sold to provide lump sum payments to pensioners. Well, you can ‘insure’ your stocks by buying an October-put option with a strike price of, say, $K=\$70$ (with maturity date 25 October). Note that in this example you hold two assets: the stock-XYZ and a put option (on stock-XYZ).

If stock prices in New York fall to $S_{T}=\$30$ on 25 October, then instead of selling your stocks in New York at $S_{T}=\$30$ , you can exercise your October-put option in Chicago, which means delivering your stock-XYZ in Chicago and you will receive $K=\$70$ for each stock (from the options clearing house). By buying the put option on 15 July, you have guaranteed a minimum price of $K=\$70$ on 25 October at which you can sell the stocks-XYZ, held by the pension fund. The cost of this ‘insurance’ is the put premium $P=\$2.2$ paid on 15 July. True, the pension fund has lost $\$2$ per stock as the initial price of the stock was $S_{0}=\$72$ in July since the pension fund can only obtain $K=\$70$ when they deliver the stock and exercise the put option in Chicago – the $\$2$ is the ‘deductible’ in the put insurance contract.5 Losing $\$2$ per stock because you had the foresight to take out insurance by buying a put option (with $K=\$70$ ), is a lot better than if you had not purchased the put, since then your stocks-XYZ would have fallen in value by $\$42$ on the NYSE.

How does this ‘options insurance contract’ look if prices rise over the next 3 months? Suppose prices rise on the NYSE from $S_{0}=\$72$ in July to $S_{T}=\$80$ in October. Then your long put is worthless as the pension fund would not ‘deliver’ (sell) its stocks in Chicago for $K=\$70$ (using the stocks and the put) when it can sell its stocks in New York for $S_{T}=\$80$ . Indeed the pension fund will ‘throw away’ (i.e. not exercise) the put option in Chicago and will sell stocks-XYZ on the NYSE for $\$80-50$ the pension fund (and the new pensioners) will be very happy.

The insurance policy provided by the ‘stock $^+$ put’ has allowed the pension fund to fx a minimum selling price of $K=\$70$ at which it can sell its stock holdings on 25 October, by exercising the October-put contract in Chicago. No matter how low the stock price on the NYSE on 25 October, the pension fund – by exercising the put option – can secure a minimum price of $K=\$70$ . But the ‘stock $^+$ put’ also allows the pension fund to beneft from any ‘upside’ if stock prices rise, because then the pension fund simply sells its stocks-XYZ on the NYSE at the high price. There are many types of situation that can be analysed using an options approach and some of these are discussed in Finance Blog 1.1.

# Finance Blog 1.1 Hidden Options

Aristotle in Book I of Politics, mentions the Greek philosopher Thales who developed a ‘fnancial device’ which was in fact an option. One winter he ‘read the stars’ and decided that next autumn would result in an exceptionally good olive harvest. He therefore quietly went around the owners of olive presses and paid them a small retainer (i.e. the call option premium) to secure the right to be frst to use their olive presses in the autumn, for a fxed price (the strike price), if he so wished. Come autumn, the harvest was good and therefore the demand for the olive presses was high and Thales could charge a high price to the olive growers to let them use the olive presses, but Thales only paid the lower strike price to the owners of the olive presses. Even if Thales had been wrong about the harvest, the most he could have lost was the small option premium he initially paid to the owners of the olive presses.

Although some people may not be aware of it, they probably hold options. For example, consider rural bus services whose fares are often subsidised via local government taxes (e.g. sales taxes and community charges). If you live out of town, you have the option to take the bus into town by paying the known fxed fare ( $\mathbf{\bar{\Psi}}=\mathbf{\Psi}$ strike price). You will do this if the value of your journey on that day by bus exceeds the fxed fare (strike price). Hence, if you live out of town you are holding an implicit call option and the call premium is that part of your local taxes that goes to subsidise the bus company. You may never use the bus but the option to use the bus (e.g. if your car breaks down) has a positive value to you and hence you may be willing to see the rural bus service subsidised by local taxes.

Next, suppose in January you have been ofered a place at one of several universities, if you achieve a grade B (or above) in your examinations in June. You will make your fnal decision about attending a specifc university or not, in September. The (implicit) option premium you pay is the time and efort you put into studying between January and June. You have nine months to decide on your choice of ‘the best’ university for you (i.e. the time to maturity of the option), which is conditional on getting appropriate grade B or above in the June exams.

In September, if you decide to go to a university, you will have to ‘pay’ the strike price (i.e. tuition and living expenses and income foregone while attending the course). In September you will choose that university with the largest net payof $S_{T}-K>0$ where $S_{T}$ is the (expected) present value of your additional earnings after graduating from a particular university. If $S_{T}-K>0$ then you will ‘take delivery’ of one of the university courses, so the option you have is a ‘call option’. Of course if $S_{T}<K$ then you will choose not to go to university (and instead look for a job) – that is, you will not exercise your ‘call option’, as your extra post-university earnings do not cover the costs of attending university.

The above is a type of exotic option since in September you are allowed to choose that university which maximises the possible payofs $S_{T}-K$ across the diferent universities who have made you an ofer. Because you can choose that university with the highest payof (i.e. the largest value of $S_{T}-K)$ then this is known as a rainbow option (or min-max option).

Suppose it is January so you do not yet have your June examination results. You are holding a form of exotic option known as a barrier option. If your intellectual prowess increases and you achieve the grade B in June, then you cross the exam barrier and the option ‘knocks in’ (i.e. comes ‘alive’) and can be exercised later (in September), if you wish.

To be even more precise you are holding a knock-in, rainbow call option. If you do not achieve the grade B in June, then all your university ofers are void and your implicit option expires worthless in June. All that efort spent studying (i.e. the implicit option premium) will not help you get into any of your chosen ‘top’ universities in September. The option you hold is a path dependent rainbow barrier option, since the fnal payof in September (i.e. your choice of the ‘best’ university) depends on whether you achieved at least a B-grade at an earlier date on your path to success (i.e. in your examinations in June).

Source: Adapted from Cuthbertson and Nitzsche (2001).

# 1.3 SWAPS

Swaps are another type of derivative contract which frst appeared in the early 1980s. They are primarily used for hedging interest rate or exchange rate risk over many future periods.

A swap is a negotiated (OTC) agreement between two parties to exchange cash fows over a series of pre-specifed future dates (‘reset dates’).

A plain vanilla interest rate swap involves a periodic exchange of interest payments. One set of future interest payments are at a fxed swap rate, $s p_{0}=3\%$ p.a. (say), which is determined when the swap is initiated. The other set of interest payments are determined by the prevailing level of some ‘foating’ interest rate (usually LIBOR). The swap will be based on a notional principal amount of $\$1000$ , say.

For example, in July 2018 a US frm ‘BigBurger’ might have a swap-deal with JPMorgan where BigBurger has agreed to receive annual interest payments from the swap dealer based on (USD) LIBOR rates on 15 July 2019 and on 15 July 2020 (the reset dates). BigBurger also agrees to pay the swap dealer (JPMorgan) a fxed swap rate of $s p_{0}=3\%$ p.a., on these dates (on a notional principal amount of $\$1000$ . BigBurger is a ‘foating-rate receiver’ and a ‘fxed-rate payer’ in the swap. The payments are based on a $\$1000$ (notional) principal amount, but only the interest payments are exchanged (and not the $\$1000$ principal itself). The maturity of the swap, the reset dates, notional principal, the fxed swap rate and the type of floating rate (usually LIBOR) to be used in the swap deal are set at the outset of the contract.

The agreed swap rate is $s p_{0}=3\%$ p.a. Suppose LIBOR rates turn out to be $\mathrm{LIBOR}_{1}=5\%$ on 15 July 2019 and $\mathrm{LIBOR}_{2}=2\%$ on 15 July 2020. Then on 15 July 2019 the swap dealer

JPMorgan owes BigBurger, $\$50$ in interest based on $\mathrm{LIBOR}_{1}=5\%$ and BigBurger owes JPMorgan (the swap dealer) $\$30$ based on the fxed swap rate of $s p_{0}=3\%$ , hence:
$$
S w a p d e a l e r_{S}^{\prime}p a y o f f t o B i g B u r g e r=\S100\mathrm{m}(L I B O R_{1}-s p_{0})=\S2\mathrm{m}
$$
On 15 July 2020 the swap dealer owes BigBurger $\$20$ based on the out-turn $\mathrm{LIBOR}_{2}=2\%$ and BigBurger owes the swap dealer $\$30$ (based on $s p_{0}=3\%$ ). So on 15 July 2020, BigBurger pays the swap dealer $\$10$ :

$$
S w a p d e a l e r^{\prime}s p a y o f f t o B i g B u r g e r=\S100\mathrm{m}(L I B O R_{2}-s p_{0})=-\S1\mathrm{m}
$$

The negative sign indicates that it is actually BigBurger who pays $\$10$ to the swap dealer (JPMorgan).6

Suppose BigBurger has a bank loan of $\$1000$ (say) with Citibank with interest payments (each year) based on future values of LIBOR. If BigBurger, in July 2018, also has a ‘receive-fxed, pay-foat (LIBOR)’ interest rate swap (with JPMorgan), at a fxed swap rate of $s p_{0}=3\%$ (say) then the ‘efective cost’ of the bank loan to BigBurger at any future reset date, $T.$ , is:

$$
=\S100\mathrm{m}\ L I B O R_{T}-\S100\mathrm{m}(L I B O R-s p_{0})=\S100\mathrm{m}s p_{0}
$$

Hence, the net efect is that BigBurger pays the known fxed swap rate of $s p_{0}=3\%$ p.a., regardless of whether the out-turn value for LIBOR is low at $2\%$ p.a. or high at $5\%$ p.a. Of course, with the swap in place, this means that BigBurger cannot take advantage of low LIBOR loan rates in the future, should they occur. On the other hand, BigBurger only has to pay an efective interest rate on the loan of $s p_{0}=3\%$ p.a., even if LIBOR turns out to be high at $5\%$ p.a. So in July 2018 if BigBurger really does want to ‘lock in’ an efective loan rate equal to $s p_{0}=3\%$ p.a. (on the next two loan interest rate reset dates) then it will take out a ‘receive fxed-pay foating (LIBOR)’ interest rate swap with JPMorgan.

The intermediaries in a swap transaction are usually large investment banks who act as swap dealers. They are usually members of the International Swaps and Derivatives Association (ISDA) who provide some standardisation in swap agreements via the master swap agreement, which can then be adapted where necessary to accommodate most customer requirements. Dealers make profts via the bid–ask spread (on the fxed leg of the swap) and might also charge a small brokerage fee for setting up the swap.

# 1.4 HEDGING, SPECULATION, AND ARBITRAGE

Part of the reason for the success of both futures and options is that they provide opportunities for hedging, speculation, and arbitrage.

# 1.4.1 Hedgers

Examples of hedging using the forward market in foreign exchange are perhaps most common to the lay person. If a US exporter expects to receive £3,000 in 3 months, then the US exporter can buy dollars today in the forward market at the 3-month forward FX-rate, $F=1.5\left({\Phi/\mathfrak{L}}\right)$ . The key feature is that today, the US company fxes the amount of USD it will receive at $\$4,500$ , in exchange for the £3,000 it provides, in 3 months’ time.

Futures contracts if held to maturity, are like forward contracts – they fx the price that the hedger will pay or receive at maturity of the futures contract. However, it can be shown that even if the futures contract is closed out before maturity much of the risk can be hedged, but a small amount does remain (this is known as basis risk).

Options contracts provide ‘insurance’. Investors in options can protect themselves against adverse price movements in the future but they still retain the possibility of benefting from any favourable price movements. To obtain this insurance, the option’s purchaser (‘the long’) of either a call or a put has to pay the option premium, today.

For example, a US exporter to the UK can ‘insure’ (i.e. set a lower limit for) her future US dollar receipts in 3 months’ time, if today she buys a put option on sterling at a strike price of $K=2$ $\up$12$ , USD/GBP), which matures in 3 months. Suppose the put option is for ‘delivery’ of £3,000. The put option implies she will receive a minimum of $K=2$ USD/GBP by exercising her put in Chicago in 3 months’ time – so the minimum she will receive from exercising the put is $\$6,000$ (even if the quoted spot-FX rate in 3 months’ time is $S_{T}=1.5$ USD/GBP, say). But if in 3 months’ time, the spot exchange rate is $S_{T}=2.1$ USD/GBP, she can ‘walk away’ from the put option contract (i.e. not exercise the put) and exchange her £3,000 at the higher spot rate (and receive $\$6,300$ from the spot FX-dealer). For the privilege of having this ‘option’ to choose the best outcome in the future, she has to pay the put premium, at the outset.

# 1.4.2 Speculators and Leverage

We have seen that because the call option premium is small relative to the price of the underlying asset, then speculation with calls can provide a high percentage return on the ‘own capital’ used to purchase the option. In our above examples, buying a call option on stocks gave a return of $167\%$ , whereas buying the stock itself only produced a return of $10\%$ – options therefore provide leverage.

Leverage also applies to futures contracts because a speculator does not have to provide any of her own funds. Suppose on 25 January you ring up Chicago and buy a ‘June-futures’ contract (on stocks-ABC) at a price of $F_{0}=\$90$ . Assume the futures matures on 25 June. In January you do not pay any money – here we ignore (so-called) margin requirements which are small and earn a competitive interest rate, and therefore are not a cost. Suppose on 15 March, you close out your June-futures contract in Chicago by selling at the market price of $F_{1}=\$100$ . You make a cash proft of $F_{1}-F_{0}=\$10$ , on 15 March. Because the futures trade (buying then selling) does not require any ‘own funds’, the percentage return and hence leverage is infnite.

By using futures, speculators can make very large losses as well as very large gains. However, there is a diference between futures and options. In the case of futures the potential loss or gain can be very large. But when call or put options are purchased by speculators, the speculator’s loss is limited to the option premium, yet the upside can be very large.

# 1.4.3 Arbitrageurs

Arbitrage involves ‘locking in’ a riskless proft by entering into transactions in two or more markets simultaneously. Usually ‘arbitrage’ implies that the investor does not use any of his own capital when making the trades. Arbitrage plays a very important role in the determination of both futures and options prices as we shall see in later chapters. Arbitrage is often loosely referred to as the ‘law of one price’ for fnancial assets. Simply expressed, this implies that identical assets must sell for the same price. We consider a very simple example of arbitrage in Finance Blog 1.2.

# Finance Blog 1.2 Arbitrage: Dolly the Sheep

By way of an analogy consider ‘Dolly’ the sheep. You will remember that Dolly was cloned by scientists at Edinburgh University and was an exact replica of a ‘real’ Highland sheep. Dolly and real Highland sheep are identical and indistinguishable. Dolly is a form of genetic engineering or ‘synthetic’ or ‘replication’ sheep. Assume we could engineer ‘Dolly’ in Edinburgh at a cost (in terms of wages and equipment) of £200 per Dolly. So you can purchase a Dolly in Edinburgh for £200.

Suppose the current market price of real sheep being sold in the local market in the Highlands is £220. ‘Sheep arbitrageurs’ sitting in London seeing these prices on their internet screens would (ethical issues aside) buy a ‘replication’ Dolly in Edinburgh for £200 and simultaneously they would sell Dolly in the local market in the Highlands for £220 making an arbitrage (risk-free) proft of £20. (We ignore any transportation costs of getting Dolly from Edinburgh to the Highlands.)

This increase in demand for a Dolly in Edinburgh and sale of a Dolly in the Highlands (by many arbitrageurs in London doing the same trades) would mean the price of a Dolly would be bid up in Edinburgh and the price of a Dolly in the Highlands would fall – this is ‘supply and demand’ at work. Arbitrage and ‘supply and demand’ would ensure that the price of a Dolly in Edinburgh and the Highlands would quickly move to equality at say £210 for each – at which point arbitrage activity would stop – since there are now no risk-free profts to be made. Economists would say that £210 is the current equilibrium price of a Dolly.

Arbitrage ensures that the price of real Highland sheep must eventually equal the cost of producing an identical ‘Dolly replicant’. Dolly is like a ‘synthetic’ or ‘replication’ portfolio in fnancial economics. As we shall see, this is how we price many derivatives – we create a ‘synthetic’ or ‘replication’ portfolio, which has identical payofs to the derivative itself.

Larry Summers, a prominent US economist (and previous US Secretary of the Treasury) rather impishly characterised the diference between economists and traditional fnance specialists with the following analogy. He said that economists are interested in why, for example, the price of a bottle of ketchup moves up and down (e.g. because of changes in incomes, relative prices, innovation in production processes, etc.), while fnance specialists are only interested in whether a $16\mathrm{oz}$ bottle of ketchup sells for the same price as two 8 oz bottles. He’s only half right.

# 1.5 SHORT-SELLING

If an investor purchases a security (e.g. stocks) she is said to go long and if she sells a security she owns, she is said to go short. However, if she sells a security that she does not own this is known as short-selling. Hedging may involve short-selling, so we outline the main features here.

Suppose a speculator (Ms Short) thinks a particular stock will fall in price in the future but she does not own the stock. She may be able to make a proft by short-selling. Initially, she borrows the stock from her prime broker (e.g. Goldman’s) for an agreed time period. The prime broker may already hold the stock on behalf of another client in a custodial account or the broker has to ‘locate’ the stock, which may be borrowed from another bank (JPMorgan) or fund management company (Fidelity) or pension fund (Legal and General [L&G]), who hold stocks ‘on behalf of their customers’ in a custodial account. Suppose Ms Short sells Apple stock (which her broker has borrowed from L&G) for $\$100$ (and the stock is purchased by AXA insurance company). If the price falls over the next month to say $\$90$ , then she can repurchase Apple stock in the market at $\$90$ , return the stock to her broker, thus pocketing the diference of $\$10$ .

If the Apple stock pays dividends over the period of the short-sale7 then Ms Short has to pay an equivalent cash amount to her broker (which is then passed on to L&G). Of course, if the stock price rises and Ms Short has to close out, then she will make a loss (which can increase without limit). In the US you can only short-sell on an ‘uptick’ (i.e. only if the last change in price was positive).

Short-selling is risky for the prime broker (Goldman’s), as in the future Ms Short may not ‘replace’ the stocks she has borrowed and sold in the open market. So the broker requires the cash proceeds from the short-sale to be held at the brokerage frm (e.g. Goldman’s)8 and will also require an additional margin payment (of say $50\%$ of the value of the short-sale) as further ‘collateral’ (i.e. a ‘good faith’ deposit).9 Further margin calls may be made if the stock price subsequently rises. However, if the stock price subsequently falls, Ms Short’s short position is worth more and then she may be allowed to withdraw any surplus cash from her margin account.

The calculation of the (percent) rate of return from short-selling is often based on the initial receipts from the sale of the stocks.10 For example, suppose Ms Short short-sells 100 Apple stocks at $\$2$ per stock and buys them back later at $\$1.50$ . Assume the $\$200$ proceeds from the short-sale cannot be used by Ms Short (and are held as collateral by the broker, who usually pays interest on these funds).

Assume the dividend yield on the stocks is $d=5\%$ and these dividends accrue over the period Ms Short has short-sold the stocks. Any dividend payments (over the period Ms Short borrows the stocks) must be paid to L&G (via her prime broker’s account) and are equal to $\$10$ $(=5\%\times\$200)$ . If we ignore the interest and commission costs of short-selling then the return on the short sale is:

$$
\begin{array}{c}{{\mathrm{Return}={\displaystyle\frac{\mathrm{Net}\mathrm{proft}}{\mathrm{Proceedsfrom~short}\cdot\mathrm{sale}}}={\displaystyle\frac{\S200-\Phi150-\Phi10}{\S200}}}}\\ {{={\displaystyle\frac{\S40}{\S200}}=0.20\left(20\%\right)}}\end{array}
$$

$$
\begin{array}{r l}&{\mathsf{e}=\%\mathrm{Price~fall}-\%\mathrm{Dividend~yield}=(P_{0}-P_{1})/P_{0}-d=25\%-5\%=20\%}\\ &{\quad=-(\%\mathrm{Price~rise}+\%\mathrm{Dividend~yield})}\end{array}
$$

Hence, the (simplifed) return to the short-seller is simply the return to a purchaser of a stock, but with the sign reversed. Finally, note that the broker usually takes a small

(percentage) commission for organising the short-sale, sometimes referred to colloquially as a ‘haircut’ and this should also be deducted when calculating the above return.11

# 1.6 SUMMARY

• In a forward contract, the forward price is agreed today, for delivery of the underlying asset in the contract (e.g. foreign exchange, stocks-XYZ, barrels of oil), at a specifc place and specifc date in the future (maturity date). Forward contracts are usually held to maturity, when delivery of the underlying asset takes place.
• Forward contracts are over-the-counter (OTC) agreements whose terms (e.g. ‘size’, delivery date, delivery point and forward price) are negotiated between two counterparties, today.
• Futures contracts if held to maturity are very similar to forward contracts. However, futures contracts are standardised (e.g. fxed contract size, delivery dates, etc.), are traded on exchanges and the futures price fuctuates and is observable continuously on the exchange (or electronic platform).
• A buyer or seller of a futures contract has to immediately provide a ‘good faith deposit’ which is known as the initial margin (on which interest is usually paid). The initial margin is not the ‘price’ of the futures contract.
• Most futures contracts are closed out before maturity. The proft from an initial long (buy) futures position is the diference between the fnal selling price (when the contract is closed out) and the initial price paid. The proft from an initial short (sell) futures position is the diference between the selling price and the price at which you ‘buy-back’ the contract. Futures contracts are ‘contracts for diferences’.
• Futures contracts can be used for hedging or speculation. They only require a small upfront amount of capital placed with the clearing house known as the ‘margin payment’. Hence, for a speculator futures contracts provide ‘leverage’.
• Options contracts can be used to provide ‘insurance’. If you plan to purchase stocks in the future and are worried their price might rise, then by purchasing a call option today you can fx the maximum price at $K$ (the strike price) you will have to pay for the stocks in the future. But you can also take advantage of low stock prices should they occur, by

not exercising the call option and instead purchasing the stocks at the low cash-market price on the NYSE.

• If you already own stocks and you are worried that their price might fall in the future, you can buy a put option which will fx the minimum price $(=K)$ you will receive when you deliver your stocks in the futures contract and receive the strike price $K$ at maturity of the put contract. On the other hand, if stock prices rise (above $K$ ) you do not exercise the put option but sell your stock at the high cash-market price on the NYSE.
• Options can be used for speculation without having to provide much capital (own funds) since you only pay a ‘small’ option premium (i.e. ‘small’, relative to the spot (cash-market) price of the underlying asset). So options provide leverage.
• Acting as a speculator, if you think stock prices will rise (fall) in the future you would buy a call (put) option, today. The most a speculator can lose when buying calls or puts are the respective option premia. But the potential upside for calls (puts) can be very large if there is a large rise (fall) in the stock price.
• An interest rate swap allows you to switch from paying an uncertain LIBOR interest rate in the future (e.g. on a bank loan) and instead to end up paying a known fxed interest rate (over the life of the swap contract).
• Short-selling stocks allows speculators to take advantage of a future fall in stock prices, even if they do not currently own the stock – they borrow the stock from their broker and sell it, hoping to buy it back at a lower price in the future.

# EXERCISES

# Question 1

Why are futures and options contracts generically referred to as ‘derivatives’?

# Question 2

You are a US exporter (‘USam’) who will receive $\mathsf{\epsilon}10\mathsf{m}$ in 6 months’ time from the sale of Barbie dolls in Euroland. How can you hedge your foreign exchange FX risk using a forward contract?

# Question 3

As a speculator, how does going long a futures contract on a stock give you ‘leverage’ compared with using your own funds to buy the stock? Use $F_{0}=\$101$ and $S_{0}=\$100$ , with out-turn values (3 months later) of $F_{1}=\$111$ and $S_{1}=\$110$ .

# Question 4

Under what circumstances would you make a proft at maturity $T_{\mathbf{\delta}}$ , from a long position in futures contract on ‘hogs’? Assume the futures price is $F_{0}=\$100$ (per hog) and at maturity of the futures contract, the spot (cash market) price of hogs is $S_{T}=110$ .

# Question 5

You are a speculator and you think stock prices will increase. Should you buy a call or a put option?

# Question 6

If $K=150$ and the put premium is $P=5$ should you exercise the put option if the spot price at expiration is $S_{T}=148?$ What is the payof and the proft?

# Question 7

In what way is a call option to marry Vito Corleone’s daughter (Connie, in Godfather $\vec{I}$ ) in one year’s time diferent from a (1-year) futures contract? Assume the strike price is $K$ and the current price of the futures is also equal to $K.$ . Assume both contracts are held to maturity.

# Question 8

You have a (mortgage) loan for $\$200,000$ which has been in existence for 2 years and has a further 10 years to maturity. Interest on the loan is paid every year, at whatever the (one-year) interest rate is at that time (i.e. it is a foating rate loan at LIBOR). You took out this loan when interest rates were low but now you think interest rates will be permanently higher in the future. How can you use the swaps market to efectively give you a loan with a fxed interest rate over the next 10 years? (Assume it is an ‘interest only’ loan, so the principal of $\$200,000$ remains fxed and the latter is paid of using a ‘lump sum’ from your pension).

# Question 9

A bank, BigMoney, raises deposit funds at LIBOR (currently $10\%$ p.a.) in the interbank market and on-lends the funds in fxed interest loans at $11\%$ p.a. What are the risks involved and how might the bank hedge the risk using swaps?
