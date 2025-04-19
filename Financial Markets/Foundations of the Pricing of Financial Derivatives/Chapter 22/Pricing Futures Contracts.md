---
tags:
  - '#arbitrage'
  - '#contango_backwardation'
  - '#daily_settlement'
  - '#forward_contracts'
  - '#futures_contracts'
  - '#gold_futures'
  - '#marking_to_market'
  - '#natural_gas_futures'
  - '#stochastic_interest_rates'
  - '#wheat_futures'
---
# 22.2 PRICING FUTURES CONTRACTS

A futures contract is effectively a forward contract that is resettled every day. That is, at the end of the day, the clearinghouse of the exchange determines an official settlement price, which is an average of the last few trades of the day. The change in the settlement price from the previous day is then credited to the party that gained and charged to the party that lost. Thus, if the settlement price increased (decreased), the holders of long (short) positions. would be credited the gain and the holders of short (long) positions would be charged the loss. This process is called marking-to-market and, sometimes, the daily settlement. It effectively results in gains and losses being collected and charged in smaller amounts. over shorter periods of time than in the case of forward contracts, whereby the contract is completely settled at expiration. The process of settling daily reduces the credit risk. In fact, futures exchanges guarantee that no one will fail to be paid because of the default. of the opposite party. This guarantee has been absolutely fulfilled, because no party has ever lost money on any futures exchange in the world due to default of the counterparty. The exchange, through its clearinghouse, has always either collected the money or paid up itself.

# 22.2.1 Daily Settlement and Futures Prices with Constant Interest Rates

The daily settlement results in a difference in the pattern of cash flows to a holder of a futures contract in comparison to that of a holder of a forward contract. As it turns out, there are some circumstances in which this difference has no economic effect, and in most cases, it is likely to have no material impact. But let us start by seeing what the effect is, however small it might turn out to be. This work draws on Jarrow and Oldfield (1981) and Cox, Ingersoll, and Ross (1981).

Let us set up the problem by denoting the futures price at time $t$ for a contract expiring at time $T$ as $f_{t}(T)$ . Futures contracts trade on a futures exchange and are, therefore, updated throughout the trading session. Our first important result is the convergence of the futures price at expiration to the spot price. That is, a futures contract that is created an instant before expiration will be priced at the spot price, because it will immediately expire and result in delivery of the spot asset, thus,

$$
f_{T}(T)=S_{T}.
$$

Now let us take a look at how one would value a futures contract. Suppose on day $t$ , the settlement price for the previous day was. $f_{t-1}(T)$ . Now, here at the end of day. $t$ the price is $f_{t}(T)$ . The accumulated value is $f_{t}(T)-f_{t-1}(T).\mathrm{Sc}$ , at this point, an instant. before the daily settlement, the value of the futures contract is

Before the daily settlement,

$$
\nu_{t}(T)=f_{t}(T)-f_{t-1}(T).
$$

That is, the value is simply the price change from the previous settlement. As soon as the market closes, the daily settlement at day $t$ will occur. If the previous value is positive (negative), the profit will be credited (charged) to the holder of the long position, and the loss will be charged (credited) to the holder of the short position. After the daily settlement, the value reverts to zero,

After the daily settlement,

$$
\nu_{t}(T)=0.
$$

In effect, the daily settlement means that the contract is terminated and rewritten at the new settlement price. This is why we described a futures contract as a forward contract that is settled and rewritten every day.

Now, let us take a look at when forward prices would equal futures prices. Table 22.2 illustrates the pattern of cash flows from day 1 through day $T.$ the expiration.

We want to know if the original forward price,. $F_{0}(T)$ , would equal the original futures. price, $f_{0}(T)$ . First, let us step back to one day prior to expiration, in which the futures price would be $f_{t-1}(T)$ . One day later the contract will expire and effectively conduct its last. daily settlement. A forward contract created on that day will also settle one day later. Hence, the two contracts will have the same cash flow one day later; thus, the forward. and futures prices will be the same,.

One day prior to expiration,

$$
f_{T-1}(T)=F_{T-1}(T).
$$

Stepping back one further day to $T-2$ , we can show that if the interest rate on day $t$ is known on day $t-1$ , the futures price on day $t$ would equal the forward price on day $t.$ Let us assume that the interest rate,. $r$ , is constant from day to day, a common. assumption in derivative pricing theory.4 Let us construct the following strategy: Buy one forward contract at the price. $F_{T-2}(T)$ and sell $1/(1+r)$ futures at the price $f_{T-2}(T)$ . At the end of day $T-1$ , we generate no cash flow on the forward contract because it is not. settled daily and has one more day to expiration. Through its daily settlement, however,. the futures will produce a cash flow of. $\mathsf{\bar{-}}\big[f_{T-1}(T)-f_{T-2}(T)\big]$ times $1/(1+r)$ contracts. If this amount is negative, let us borrow the funds at the rate $r$ for one day. If it is pos-. itive, we invest the funds at the rate $r$ for one day. By borrowing or investing the daily. settlement cash flow, we avoid having to put up or withdraw funds on a day-to-day basis. One day later, which is expiration, the daily settlement amount at. $T-1$ plus one day's interest paid or received will be. $-\left[f_{T-1}(T)-f_{T-2}(T)\right].$ In addition, the final daily settle-. ment will be $-\big[f_{T}(T)-f_{T-1}(T)\big]$ . Adding these two amounts gives a total cash flow at. $T$ of $\left-\left[f_{T-1}(T)^{\setminus}-f_{T-2}(T)\right]-\left[f_{T}(T)-f_{T-1}(T)\right]=f_{T-2}(T)-f_{T}(T)=f_{T-2}(T)-S_{T} $ . This is the same cash flow as on a two-day forward contract. We could successively create forwards and futures further back and similarly demonstrate that the cash flows would be the same. Hence, the price of a forward contract would equal the price of the analogous futures contract. Of course, similar to forwards, futures will also reflect carrying costs and. any other potential benefits or costs of holding the asset.5

IABLE 22.2 Cash Flows from Futures and Forward Contracts


<html><body><table><tr><td>Day</td><td>FuturesCashFlow</td><td>ForwardCashFlow</td></tr><tr><td>0</td><td>0</td><td>0</td></tr><tr><td>1</td><td>f (T)-fo(T)</td><td>0</td></tr><tr><td>2</td><td>f2 (T)-fi (T)</td><td>0</td></tr><tr><td>3</td><td>f3(T)-f2(T)</td><td>0</td></tr><tr><td></td><td></td><td></td></tr><tr><td>T-2</td><td>fr-2 (T) - fr-3(T)</td><td>0</td></tr><tr><td>T-1</td><td>fT-1 (T)- fT-2 (T)</td><td>0</td></tr><tr><td>T</td><td>ST - fr-1 (T)</td><td>Sr -Fo(T)</td></tr></table></body></html>

This result, however, was possible only because the interest rate was known in advance.. In effect, we must know the entire sequence of one-day interest rates. In a world of constant. interest rates, that is certainly not a problem. If interest rates are stochastic, however, that could be a problem. Let us now see why stochastic interest rates can drive the price of the. futures contract above or below the price of the forward contract..

# 22.2.2 The Daily Settlement and Futures Prices with Stochastic Interest Rates

Consider a long position in a futures contract. If futures prices increase when interest rates increase, then gains will be realized and reinvested at higher interest rates. If futures prices increase when interest rates decrease, losses will be realized and financed at lower interest rates. Thus, when futures prices and interest rates are positively related, the daily. settlement benefits parties who choose futures contracts over forward contracts, and as a result, futures prices will be above forward prices. If futures prices are negatively related. to interest rates, then futures contracts will be hurt by the daily settlement, because gains.

will be reinvested when rates are lower and losses will be financed when rates are higher. This benefits parties who choose to take forward contracts over futures contracts. Thus, if futures prices are positively (negatively) related to interest rates, futures prices will be higher (lower) than forward prices. As you might expect, if futures prices are unrelated to interest rates, meaning essentially a zero correlation, futures and forward prices will be the same.

These points are strong statements about the relationship between futures and for-.
wards, but they are taken without consideration for credit risk. The daily settlement that.
is undertaken in futures markets essentially eliminates credit risk. Forward markets do retain some element of credit risk, but that element is minimized by the careful consider-.
ation of whether to engage in a forward contract with anyone who might default and by.
potentially requiring margin deposits and perhaps even periodically marking to market..

If we minimize these credit considerations, futures prices will essentially equal forward prices, and therefore the futures pricing model would simply be a restatement of the forward pricing model, Equation (22.3),.

$$
f_{t}(T)=S_{t}(1+r)^{\tau_{t}}.
$$

In the next section, we briefly review some anecdotal evidence related to futures pricing.

# 22.2.3 Selected Futures Contracts-Gold, Wheat, and Natural Gas

Table 22.3 presents the settlement prices for gold futures contracts traded on the CME Group exchange. Note that the pattern of futures prices with respect to maturity is monotonically increasing, a property known as contango. The pattern of futures prices with respect to maturity that is monotonically decreasing is known as backwardation.

US gold futures contracts are almost always in contango. The reason is generally positive interest rates and positive storage costs as well as the ease with which to conduct arbitrage transactions. One key insight is that the upward sloping pattern does not reflect market participants' views on the future of gold prices; rather, it reflects solely carrying costs related to the underlying instrument. Interestingly, the pattern does not occur with gold futures contracts in some other countries where it is difficult to actually engage in the required arbitrage transactions.

TABLE 22.3 Selected Gold Futures Prices


<html><body><table><tr><td>Description</td><td>Price</td></tr><tr><td>Spot (Sep)</td><td>$1,502.20</td></tr><tr><td>OctY1</td><td>$1,504.50</td></tr><tr><td>NovY1</td><td>$1,508.10</td></tr><tr><td>DecY1</td><td>$1,511.10</td></tr><tr><td>FebY2</td><td>$1,517.40</td></tr><tr><td>AprY2</td><td>$1,522.90</td></tr><tr><td>Jun Y2</td><td>$1,527.60</td></tr><tr><td></td><td></td></tr></table></body></html>

Table 22.4 presents the settlement prices for wheat futures contracts traded on the CME Group exchange. Note that the pattern of futures prices with respect to maturity is again monotonically increasing. Due to the difficulty in conducting arbitrage-related activities with wheat, this pattern of futures prices communicates different information than gold. Wheat is perishable and consumed. The pattern of US wheat futures contracts takes many different shapes over time, unlike gold contracts. For example, global harvest expectations play a key role in wheat futures prices. Thus, one key insight is that the upward sloping pattern for wheat does reflect market participants' views on the future of wheat spot prices.

Table 22.5 presents the settlement prices for natural gas futures contracts traded on the CME Group exchange. Note that the pattern of futures prices with respect to matu-. rity is neither monotonically increasing nor decreasing. US natural gas futures contracts' pattern takes many different shapes over time unlike gold contracts. As with wheat, the driving reason is that it is generally difficult to conduct the required arbitrage transactions as natural gas is volatile and difficult to store. Global natural gas production and consumption expectations also play a key role in futures prices. Natural gas is consumed in greater volumes in the summer months to generate electricity for air conditioning and in. the winter months to run furnaces or generate electricity for heating. Thus, one key insight is that the dynamic pattern for natural gas does reflect market participants' views on the future of natural gas spot prices. In particular, winter and often summer futures prices are. higher than spring and fall..

We turn now to explore options on forwards and futures contracts.

TABLE 22.4 Selected Wheat Futures Prices


<html><body><table><tr><td>Description</td><td>Price</td></tr><tr><td>Spot (Nov)</td><td>$4.744</td></tr><tr><td>DecY1</td><td>$4.744</td></tr><tr><td>MarY2</td><td>$4.790</td></tr><tr><td>MayY2</td><td>$4.814</td></tr><tr><td>JulY2</td><td>$4.840</td></tr><tr><td>SepY2</td><td>$4.914</td></tr><tr><td>DecY2</td><td>$5.036</td></tr><tr><td></td><td></td></tr></table></body></html>

TABLE 22.5 Selected Natural Gas Futures Prices.


<html><body><table><tr><td>Description</td><td>Price</td></tr><tr><td>Spot (Oct)</td><td>$2.585</td></tr><tr><td>NovY1</td><td>$2.625</td></tr><tr><td>DecY1</td><td>$2.768</td></tr><tr><td>JanY2</td><td>$2.859</td></tr><tr><td>FebY2</td><td>$2.811</td></tr><tr><td>MarY2</td><td>$2.685</td></tr><tr><td>AprY2</td><td>$2.399</td></tr><tr><td></td><td></td></tr></table></body></html>
