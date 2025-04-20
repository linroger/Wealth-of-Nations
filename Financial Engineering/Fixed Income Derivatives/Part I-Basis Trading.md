---
tags:
  - basis_trading
  - bond_futures
  - cash_and_carry
  - forward_pricing
  - repo_market
aliases:
  - Cash and Carry Trading
  - Government Bond Basis
key_concepts:
  - 'Basis: spot vs futures price'
  - Cheapest-to-deliver bond
  - Forward and futures pricing
  - Open repo market essential
  - Trading cash bonds and futures
---

# Basis Trading
# 1 The Government Bond Basis

Basis trading, also known as  cash and carry  trading, refers to the activity of simultaneously trading cash bonds and the related bond futures contract. The basis  is the difference between the price of a cash market asset (in this book we consider only bonds as the underlying asset) and its price as implied in the futures markets. An open repo market is essential for the smooth operation of basis trading. Most futures exchanges offer at least one bond futures contract. Major exchanges such as CBOT offer contracts along the entire yield curve; others such as LIFFE provide a market in contracts on bonds denominated in a range of major currencies.

So, the  basis  of a futures contract is the difference between the spot price of an asset and its price for future delivery as implied by the price of a futures contract written on the asset. Futures contracts are exchange-traded standardised instruments, so they are a form of what is termed a  forward  instrument, a contract that describes the forward delivery of an asset at a price agreed today. The pricing of forwards and futures follows similar principles but, as we shall see, contains signiﬁcant detail differences between the two. The simultaneous trading of futures contracts written on government bonds and the bonds themselves, basis trading, is an important part of the government repo markets; in this, and the two subsequent chapters, we review the essential elements of this type of trading. We begin with basic concepts of forward pricing, before looking at the determinants of the basis, hedging using bond futures, trading the basis and an introduction to trading strategy. We also look at the concept of the  cheapest-to-deliver  bond, and the two ways in which this is measured: the net basis and the  implied repo rate . As ever, readers are directed to the bibliography, particularly the book by Burghardt  et al  (1994), which is an excellent reference work. It reads very accessibly and contains insights useful for all bond market participants.

We begin with the concepts of forward and futures pricing, and futures contracts. This is essential background enabling us to discuss the implied repo rate and basis trading in the next chapter. The repo desk plays a crucial role in basis trading and, just like forward pricing principles, an appreciation of the repo function is also key to understanding the bond basis. First we discuss some basic concepts in futures pricing and then look at the concept of the bond basis.

# 1.1 An introduction to forward pricing

# 1.1.1 Introduction

Let’s ﬁrst look at a qualitative way of considering the forward bond basis, connected with the coupon and running cost on cash bonds. This approach reads more accessibly for those who wish a more speciﬁc application to forward pricing on bond assets.
An investor assessing whether an asset is worth purchasing spot or forward must consider two issues: whether there is an income stream associated with the asset, in which case this would be foregone if the asset was purchased forward; and if there is any holding costs associated with the asset if it is purchased spot. The forward price on a bond must reﬂect these same considerations, so a buyer will consider the effect of income foregone and  carry  costs and assess the relative gain of spot versus forward purchase. In real terms then, we are comparing the income stream of the bond coupon against the interest rate on funds borrowed to purchase the bond.

An investor who is long a cash bond will receive coupon income, and this is accrued on a daily basis. This is a purely accounting convention and has no   bearing to the current interest rate or the current price of the bond. An investor who purchases a bond forward is forgoing the income during the time to delivery, and this factor should presumably be incorporated into the forward price. What of the funding (carry) cost involved? This can be calculated from the current money market rate provided the term of the funding is known with certainty. So if we now consider a three-month forward contract on a bond against the current spot price of the same bond, the investor must assess:

j the coupon income that would be received during the three-month period; j the interest charge on funds borrowed during the three-month period.

Let us say that the difference between these two values was exactly 1.00. For the forward contract to be a worthwhile purchase, it would have to be at least 1.00 lower in price than the spot price. This is known as the forward discount. Otherwise the investor is better off buying the bond for spot delivery. However if the price is much lower than 1.00, investors will only buy forward (while cash bond holders would sell their holdings and repurchase forward). This would force the forward price back into line to its  fair value . The forward price discount is known as the  basis . The basis exists in all markets where there is a choice available between spot and forward delivery, and not just in ﬁnancial derivatives. For bonds the basis can be assessed by reference to the current price of the underlying asset, the income stream (coupon), the time to maturity of the forward contract and the current level of interest rates.
# 1.1.2 Illustrating the forward bond basis

Now let us look at an illustration, using the September 2000 long gilt contract. We use the coupon income from the cheapest-to-deliver (CTD) bond, the   $5.75\%$   2009 gilt. We haven’t discussed the concept of the CTD yet, however ignore the CTD element for now, and assume a constant money market borrowing rate (the repo rate) during the three months of the futures contract from 29 June 2000 to 27 September 2000.

Intuitively we would expect the basis to move towards zero, as the contract approached maturity. After all, what is the price of something for delivery now if not the spot price? First we consider the yield of the bond against the yield of the futures contract. This is illustrated in Figure 1.1. There is slight convergence towards the end; however, if we plot the basis itself, this does converge to zero as expected. This is shown in Figure 1.2. As the contract approaches maturity, the basis becomes more and more sensitive to slight changes in bond price or ﬁnancing rates, hence the exaggerated spike. For instance if short-term repo rates decrease, while the coupon income on the bond remains unchanged, an investor would be faced with a lower level of foregone return as a result of lower ﬁnancing costs. This makes it more attrac-tive for an investor to buy the bond spot delivery, and so the basis will rise as demand for the forward (or future, to be precise) declines.

Essentially, when the repo rate is sign i cant ly below the bond yield, the basis will be high. If the repo rate then rises the basis will fall, and this indicates the

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/665d3a5f8add66a4fdb33b2aeded83b5095597450399d2e0cab3c1633926b456.jpg)
Figure 1.1:  Yields of bond and futures contract compared. Source: LIFFE and Bloomberg
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/76bd4e87a4a1b56f4329d4964496881dde49c62a226a9d21a9db8d4827b34ff6.jpg)
Figure 1.2:  Convergence of basis towards zero. Source: LIFFE and Bloomberg

smaller interest-rate differential between the repo rate and the bond yield. If the repo rate rises to a point where it is above the bond yield, the basis will turn negative. In fact this occurred brieﬂy during the later stages of the life of the September 2000 gilt future as shown above. A negative basis indicates that the price for forward delivery exceeds that for spot delivery.

To reiterate then, the forward basis quantiﬁes the relationship between the   income generated by the underlying asset and the costs incurred by owning it. As we are concerned with bond futures, spec i call y the basis will reﬂect the relationship between the underlying bond’s coupon stream and the repo ﬁnancing rate if holding the bond. Forward contracts for bonds exhibit the basis. Futures contracts, which are standardised forward contracts traded on an organised exchange, are priced on the same principles as forwards and so therefore also exhibit the basis. The next section considers forward pricing in a more formal way.

# 1.2 Forwards and futures valuation

Let us now take a more rigorous look at forward valuation. To begin our discussion of derivative instruments, we discuss the valuation and analysis of forward and futures contracts; here, we develop basic valuation concepts. The discussion follows, with permission, the approach described in Rubinstein (1999), as shown in Section 2.2 of that text.
# 1.2.1 Introduction

A forward contract is an agreement between two parties in which the buyer contracts to purchase from the seller a speciﬁed asset, for delivery at a future date, at a price agreed today. The terms are set so that the present value of the contract is zero. For the forthcoming analysis we use the following notation:

$P$  is the current price of the underlying asset, also known as the  spot price;  $P_{T}$  is the price of the underlying asset at the time of delivery;  $X$  is the delivery price of the forward contract;  $T$  is the term to maturity of the contract in years, also referred to as the time-to-delivery;  $r$  is the risk-free interest rate;  $R$  is the return of the payout or its  yield ;  $F$  is the current price of the forward contract.

The payoff of a forward contract is therefore given by

$$
P_{T}-X
$$

with  $X$   set at the start so that the present value of    $(P_{T}-X)$   is zero. The payout yield is calculated by obtaining the percentage of the spot price that is paid out on expiry.

# 1.2.2 Forwards

When a forward contract is written, its delivery price is set so that the present value of the payout is zero. This means that the forward price    $F$   is then the price on delivery which would make the present value of the payout, on the delivery date, equal to zero. That is, at the start  $F=X,$  . This is the case on  on day 1 of the contract  $X$  however. From then until the contract expiry the value of  is ﬁxed, but the forward price  $F$   will ﬂuctuate continuously until delivery. It is the behaviour of this forward price that we wish to examine. For instance, generally as the spot price of the underlying increases, so the price of a forward contract written on the asset also increases; and vice versa. At this stage, it is important to remember that the forward price of a contract is not the same as the value of the contract, and the terms of the agreement are set so that at inception the value is zero. The relationship given above is used to show that an equation can be derived which relates  $F$   to  $\textstyle P,\,T,\,r$   and  $R$  .

Consider ﬁrst the proﬁt/loss proﬁle for a forward contract. This is shown in Figure 1.3. The price of the forward can be shown to be related to the underlying variables as

$$
\boldsymbol{F}=\boldsymbol{S}(\boldsymbol{r}/R)^{T},
$$

and for the one-year contract highlighted in Figure 1.3 is 52.5, where the parameters are    $S\!=\!50$  ,  $r\!=\!1.05$   and    $R\!=\!1.00$  .
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/61deabdaf0954614e4aef8e6e319aa55dc28802dd8ff034a8e12dd57af12cbd4.jpg)
Figure 1.3:  Forward contract proﬁt/loss proﬁle

# 1.2.3 Futures

Forward  contracts are tailor-made instruments designed to meet speciﬁc individual requirements.  Futures  contracts, on the other hand, are standardized contracts that are traded on recognized futures exchanges. Apart from this, the signiﬁcant difference between them, and the feature that inﬂuences differences between forward and futures prices, is that proﬁts or losses that are gained or suffered in futures trading are paid out at the end of the day. This does not occur with forwards. The majority of trading in futures contracts are always closed-out, that is, the position is netted out to zero before the expiry of the contract. If a position is run into the delivery month, depending on the terms and conditions of the particular exchange, the party that is long future may be delivered into. Settlement is by physical delivery in the case of commodity futures or in cash in the case of certain ﬁnancial futures. Bond futures are ﬁnancial futures where any bond that is in the  delivery basket  for that contract will be delivered to the long future. With both physical and ﬁnancial futures, only a very small percentage of contracts are actually delivered into as the majority of trading is undertaken for hedging and speculative purposes.

With futures contracts, as all previous trading proﬁts and losses have been settled, on the day of expiry only the additional change from the previous day needs to be accounted for. With a forward contract all loss or gain is rolled up until the expiry day and handed over as a total amount on this day.
# 1.2.4 Forwards and futures

# Cash ﬂow differences

We can now look at the cash ﬂow treatment of the two contracts in greater detail.  $F$  This is illustrated in Table 1.1, which uses    to denote the price of the futures contract as well. The table shows the payoff schedule at the end of each trading day for the two instruments; assume that they have identical terms. With the forward there is no cash ﬂow on intermediate dates, whereas with the futures contract there is. As with the forward contract, the price of the future ﬁxes the present value of the futures contract at zero. Each day the change in price, which at the end of the day is  marked-to-market  at the  close  price, will have resulted in   either a proﬁt or gain, which is handed over or received each day as appropriate. The process of daily settlement of price movements means that the nominal delivery price can be reset each day so that the present value of the contract is always zero. This means that the future and nominal delivery prices of a futures contract are the same at the end of each trading day.

We see in Table 1.1 that there are no cash ﬂows changing hands between counter parties to a forward contract. The price of a futures contract is reset each day; after day 1 this means it is reset from  $F$   to  $F_{1}$  . The amount    $(F_{1}-F)$   if positive, is handed over by the short future to the long future. If this amount is negative, it is paid by the long future to the short. On the expiry day    $T$   of the contract the long future will receive a settlement amount equal to    $P_{T}-F_{T-1}$   which expresses the relationship between the price of the future and the price of the underlying asset.

Table 1.1:  Cash ﬂow process for forwards and futures contracts
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/ebdff43f8b70a515953a53dbbd627b8f41e849a6f9fd986e124d00dd62e39a28.jpg)
As signiﬁcant, the daily cash ﬂows transferred when holding a futures contract cancel each other out, so that on expiry the value of the contract is (at this stage) identical to that for a forward, that is    $(P_{T}-F)$  .

With exchange-traded contracts all market participants are deemed to conduct their trading with a central counter party, the exchange’s clearing house. This eliminates counter party risk in all transactions, and the clearing house is able to guarantee each bargain because all participants are required to contribute to its clearing fund. This is by the process of  margin , by which each participant deposits an  initial margin  and then, as its proﬁts or losses are recorded, deposits further variation margin  on a daily basis. The marking-to-market of futures contracts is an essential part of this margin process. A good description of the exchange clearing process is contained in Galitz (1995).

This is the key difference between future and forward contracts. If holding a futures position that is recording a daily proﬁt, the receipt of this proﬁt on a daily basis is advantageous because the funds can be reinvested while the position is still maintained. This is not available with a forward. Equally, losses are suffered on a daily basis that are not suffered by the holder of a loss-making forward position.

# 1.2.5 Relationship between forward and future price

Continuing with the analysis shown in Rubinstein (1999), we wish to illustrate that under certain speciﬁed assumptions, the price of futures and forwards written with identical terms must be the same.

This can be shown in the following way. Consider two trading strategies of identical term to maturity and written on the same underlying asset; one strategy uses forward contracts while the other uses futures. Both strategies require no initial investment and are  self-ﬁnancing . The assumptions are:

j the absence of risk-free arbitrage opportunities; j the existence of an economist’s perfect market; j certainty of returns.

Under these conditions, it can be shown that the forward and future price must be identical. In this analysis the return    $r$   is the daily return (or instantaneous money market rate) and    $T$   is the maturity term in days. Let’s look further at the strategies. For the strategy employing forwards, we buy    $r^{T}$    forward contracts. The start forward price is    $F=X$   but of course there is no cash outlay at the start, and the payoff on expiry is

$$
r^{T}(P_{T}-F)
$$

The futures strategy is more involved, due to the daily margin cash ﬂows that are received or paid during the term of the trade. On day 1 we buy  $r$   contracts each priced at  $F.$  . After the close we receive    $F_{1}-F$  . The position is closed-out and the cash received is invested at the daily rate  $r$   up to the expiry date. The return on this  $r^{T-1}$    cash is   which means that on expiry we will receive an amount of
$$
r(F_{1}-F)r^{T-1}
$$

The next day we purchase    $r^{2}$    futures contracts at the price of    $F_{1}$   and at the close the cash ﬂow received of    $F_{2}-F_{1}$   is invested at the close of trading at    $r^{T-2}$  . Again we will receive on expiry a sum equal to

$$
r^{2}(F_{2}-F_{1})r^{T-2}
$$

This process is repeated until the expiry date, which we assume to be the delivery date. What is the net effect of following this strategy? We will receive on the expiry date a set of maturing cash ﬂows that have been invested daily from the end of day 1. The cash sums will be

$$
r^{T}(F_{1}-F)+r^{T}(F_{2}-F_{1})+r^{T}(F_{3}-F_{2})+\cdot\cdot\cdot+r^{T}(P_{T}-F_{T-1})
$$

which nets to

$$
r^{T}(P_{T}-F)
$$

which is also the payoff from the forward contract strategy. Both strategies have a zero cash outlay and are self-ﬁnancing. The key point is that if indeed we are saying that

$$
r^{T}(P_{T}-F)_{f o r w a r d}{=r^{T}(P_{T}-F)_{f u t u r e}}
$$

for the assumption of no arbitrage to hold, then    $F_{f o r w a r d}=F_{f u t u r e}$  .

# 1.2.6 The forward-spot parity

We can use the forward strategy to imply the forward price provided we know the current price of the underlying and the money market interest rate. A numerical example of the forward strategy is given at Figure 1.4, with the same parameters given earlier. We assume no-arbitrage and a perfect friction less market.

What Figure 1.4 is saying is that it is possible to replicate the payoff proﬁle we observed in Figure 1.3 by a portfolio composed of one unit of the underlying asset, the purchase of which is ﬁnanced by borrowing a sum that is equal to the present value of the forward price. This borrowing is repaid on maturity and is equal to  $(F/1.05)\times1.05$   $F.$   which is in fact   . In the absence of arbitrage opportunity the cost of forming the portfolio will be identical to that of the forward itself. However, we have set the current cost of the forward contract at zero, which gives us

$$
-50+F/1.05=0
$$

We solve this expression to obtain    $F$   and this is 52.50.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/d9a6b0bf7a58b18e61a33b1618182411477f2bdd4970f8d6a92aa40b366ec4ed.jpg)
Figure 1.4:  Forward strategy.

The price of the forward contract is 52.50, although the present value of the forward contract when it is written is zero. Following Rubinstein, we prove this in Figure 1.5.

What Figure 1.5 states is that the payoff proﬁle for the forward can be replicated precisely by setting up a portfolio that holds    $R^{-T}$  units of the underlying asset, which is funded through borrowing a sum equal to the present value of the forward price. This borrowing is repaid at maturity, this amount being equal to

$$
\left({F r}^{-T}\right)\times r^{T}=F
$$

The portfolio has an identical payoff proﬁle (by design) to the forward, this being  $(P_{T}-F)$  . In a no-arbitrage environment, the cost of setting up the portfolio must be equal to the current price of the forward, as they have identical payoffs and if one was cheaper than the other, there would be a risk-free proﬁt for a trader who

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9636f805c0218470d936826980eb0a850588bae716d2b0b5e6f7d677afae6f58.jpg)
Figure 1.5:  Algebraic proof of forward price
bought the cheap instrument and shorted the dear one. However, we set the current cost of the forward (its present value) as zero, which means the cost of constructing the duplicating portfolio must therefore be zero as well. This gives us

$$
-P R^{-T}+F r^{-T}=0
$$

which allows us to solve for the forward price    $F.$  .

The signiﬁcant aspect for the buyer of a forward contract is that the payoff of the forward is identical to that of a portfolio containing an equivalent amount of the underlying asset, which has been constructed using borrowed funds. The portfolio is known as the  replicating portfolio . The price of the forward contract is a function of the current underlying spot price, the risk-free or money market interest rate, the payoff and the maturity of the contract. To recap then the forward-spot parity states that

$$
F=P(r/R)^{T}
$$

It can be shown that neither of the possibilities    $F>P(r/R)^{T}$    or    $F<P(r/R)^{T}$    will hold unless arbitrage possibilities are admitted. The only possibility is (1.4), at which the futures price is  fair value .

# 1.2.7 The basis and implied repo rate

For later analysis, we introduce now some terms used in the futures markets.

The difference between the price of a futures contract and the current underlying spot price is known as the  basis . For bond futures contracts, which are written not on a speciﬁc bond but a  notional  bond that can in fact be represented by any bond that ﬁts within the contract terms, the size of the basis is given by (1.5):

$$
B a s i s=P_{b o n d}-(P_{f u t}\times C F)
$$

where the basis is the  gross basis  and    $C F$   is the  conversion factor  for the bond in question. All delivery-eligible bonds are said to be in the  delivery basket . The   conversion factor equalizes each deliverable bond to the futures price. The size of the gross basis represents the cost of carry associated with the bond from today to the delivery date. The bond with the lowest basis associated with it is known as the cheapest-to-deliver  bond. The magnitude of the basis changes continuously and this uncertainty is termed  basis risk.  Generally the basis declines over time as the maturity of the contract approaches, and converges to zero on the expiry date. The sign i can ce of basis risk is greatest for market participants who use futures contracts for hedging positions held in the underlying asset. The basis is positive or negative according to the type of market in question, and is a function of issues such as  cost of carry . When the basis is positive, that is    $F>P$  , the situation is described as a  contango , and is common in precious metals markets. A negative basis    $P<F$   is described as  backward ation  and is common in oil contracts and foreign currency markets.
The hedging of futures and the underlying asset requires a keen observation of the basis. To hedge a position in a futures contract, one could run an opposite position in the underlying. However, running such a position incurs the cost of carry referred to above, which depending on the nature of the asset, may include storage costs, opportunity cost of interest foregone, funding costs of holding the asset and so on. The futures price may be analyzed in terms of the forward-spot parity relationship and the risk-free interest rate. If we say that the risk-free rate is

$$
r-1
$$

and the forward-spot parity is

$$
F=P(r/R)^{T}
$$

we can set

$$
r-1=R(F/P)^{1/T}{-1}
$$

which must hold because of the no-arbitrage assumption.

This interest rate is known as the  implied repo rate , because it is similar to a repurchase agreement carried out with the futures market. Generally, a relatively high implied repo rate is indicative of high futures prices, and the same for low implied repo rates. The rates can be used to compare contracts with each other, when these have different terms to maturity and even underlying assets. The implied repo rate for the contract is more stable than the basis; as maturity approaches the level of the rate becomes very sensitive to changes in the futures price, spot price and (by deﬁnition) time to maturity.

# 1.3 The bond basis: basic concepts

# 1.3.1 Introduction

The previous section introduced the no-arbitrage forward pricing principle and the concept of the basis. We will look at this again later. So we know that the price of an asset, including a bond, that is agreed today for immediate delivery is known
as its  spot  price. In essence the forward price of an asset, agreed today for delivery at some speciﬁed future date, is based on the spot price and the cost or income of foregoing delivery until the future date. If an asset carries an income stream, withholding delivery until, say, three months in the future would present an opportunity cost to an investor in the asset, so the prospective investor would require a discount on the spot price as the price of dealing in a forward. However, if an asset comes with a holding cost, for example storage costs, then an investor might expect to pay a premium on the spot price, as it would not be incurring the holding costs that are otherwise associated with the asset.

Commodities such as wheat or petroleum are good examples of assets whose forward delivery is associated with a holding cost. For a commodity whose price is agreed today but for which delivery is taken at a forward date, economic logic dictates that the futures price must exceed the spot price. That is, a commodity basis is usually negative. Financial assets such as bonds have zero storage costs, as they are held in electronic form in a clearing system such as CREST, the settlement 10   system for United Kingdom gilts; moreover they provide an income stream that would offset the cost of ﬁnancing a bond holding until a future date. Under most circumstances when the yield curve is positively sloping, the holding of a bond position until delivery at a future date will generate a net income to the holder. For these and other reasons it is common for the bond basis to be positive, as the futures price is usually below the spot price.

As we shall see shortly, bond futures contracts do not specify a particular bond, rather a generic or  notional  bond. The actual bond that is delivered against an expired futures contract is the one that makes the cost of delivering it as low as possible. The bond that is selected is known as the cheapest-to-deliver. Considerable research has been undertaken into the concept of the  cheapest-todeliver  (CTD) bond. In fact, certain commodity contracts also trade with an underlying CTD. Burghardt ( ibid ) points out that wheat is not an homogenous product, as wheat from one part of the country exhibits different characteristics to wheat from another part of the country, and may have to be transported a longer distance (hence at greater cost) to delivery. Therefore a wheat contract is also priced based on the designated cheapest-to-deliver. There is no physical location factor with government bonds, but futures contracts specify that any bond may be delivered that falls into the required maturity period.
In this section we look at the basic concepts, necessary for an understanding of the bond basis, and introduce all the key topics. Basis trading itself is the simultaneous trading of cash bond and the bond futures contract, an arbitrage trade   that seeks to exploit any mis-pricing of the future against the cash or vice versa. In liquid and transparent markets such mis-pricing is rare, of small magnitude and very short-lived. The arb it rage ur will therefore also try to make a gain from the difference between the costs of holding (or shorting) a bond against that of delivering (or taking delivery of) it at the futures expiry date; essentially, then, the difference between the bond’s running yield and its repo ﬁnancing cost. We’ll save the trading principles for the next chapter. First let us introduce basic terminology.

# 1.3.2 Futures contract spec i cations

When speaking of bond futures contracts people generally think of the US Treasury bond contract, the Bund contract or the long Gilt contract, but then it does depend in which market one is working in or researching. The contract spec i cations for these contracts are given in Table 1.2, the two US contracts as traded on CBOT and the two European contracts as traded on LIFFE.

Remember that a futures contract is a standardised forward contract, traded on an organised exchange. So the bond futures contracts described in Table 1.2 represent a forward trade in the underlying cash bond. Only a small minority of the futures contracts traded are actually held through to delivery (unlike the case for say, agricultural commodity contracts), but if one does hold a long position at any time in the delivery month, there is a possibility that one will be delivered into.

The notional coupon in the contract spec i cation has relevance in that it is the basis of the calculation of each bond’s  price factor  or  conversion factor ; otherwise it has no bearing on understanding the price behaviour of the futures contract. Remember the contract is based on a  notional  bond, as there will be more than one bond that is eligible for delivery into the contract. The set of deliverable bonds is known as the  delivery basket . Therefore the futures price is not based on one particular bond, but acts rather like a hybrid of all the bonds in the basket (see Burghardt, page 4). What can we say about Table 1.2? For instance, exchanges specify minimum price movements, which is 0.01 for European contracts and 1/32nd for the US contracts.

Every bond in the delivery basket will have its own  conversion factor , which is intended to compensate for the coupon and timing differences of deliverable bonds. The exchange publishes tables of conversion factors in advance of a contract starting to trade, and these remain ﬁxed for the life of the contract. These numbers will be smaller than 1.0 for bonds having coupons less than the notional coupon for the bond in the contract, and greater than 1.0 otherwise.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/2b0059173337ee061b8861e348f979b3dde059e59c3c64d802578fe64a8f13aa.jpg)
Notes All times are local. The notional coupon of the Treasury bond, while deprecated as a concept by some writers, is  $6\%$  . It was changed from  $8\%$   from the March 2000 contract onwards.

Table 1.2:  Selected futures contract spec i cations
The deﬁnition of the gilt contract detailed in Table 1.2 calls for the delivery of a UK gilt with an effective maturity of between  $8\%$   to 13 years and a  $7\%$   notional coupon. We emphasise that the notional coupon should not be an object of a trader’s or investor’s focus. It exists simply because there would be problems if the deﬁnition of deliverable gilts were restricted solely to those with a coupon of exactly  $7\%$  . At times there may be no bonds having this precise coupon. Where there was one or more such bonds, the size of the futures market in relation to the size of the bond issue would expose the market to price manipulation. To avoid this, futures exchanges design contracts in such a way as to prevent anyone dominating the market. In the case of the Long Gilt and most similar contracts this is achieved by allowing the delivery of  any  bond with a sufﬁcient maturity, as we have noted. The holder of a long position in futures would prefer to receive a high-coupon bond with signiﬁcant accrued interest, while those short of the future would favour delivering a cheaper low-coupon bond shortly after the coupon date. This conﬂict of interest is resolved by adjusting the  invoice amount,  the amount paid in exchange for the bond, to account for coupon rate and timing of the bond actually delivered.

Equation (1.7) gives this invoice amount.

$$
I n v_{a m t}=\left(P_{f u t}\times C F\right)+A I
$$

where

$I n\nu_{a m t}$  is the invoice amount;  $P_{f u t}$  is the futures price;  $C F$  is the conversion factor;  $A I$  is the accrued interest.

We will consider invoice and settlement amounts again later.

# 1.3.3 The conversion factor

So, we know that a bond futures contract represents any bond whose maturity date falls in the period described in the contract spec i cations. During the delivery month, and up to the expiry date, the party that is short the future has the option on which bond to deliver and on what day in the month to deliver it. Let us consider the long Gilt contract on LIFFE. If we assume the person that is short the future delivers on the expiry date, for each contract they must deliver to the exchange’s clearing house £100,000 nominal of a notional   $7\%$   gilt of between   $8\%$    and 13 years’ maturity. Of course no such speciﬁc bond exists, so the seller delivers a bond from within the delivery basket. However if the seller delivers a bond of say,   $6\%$   coupon and 9 years maturity, intuitively we see that the value of this bond is lower than a  $7\%$   bond of 13 years maturity. While the short future may well think, ‘‘ﬁne by me’’, the long future will most certainly think not. There would be the same aggrieved feelings, just reversed, if the seller was required to deliver a bond of   $8\%$   coupon. To equalise all bonds, irrespective of which actual bond is delivered, the futures exchange assigns a  conversion factor  to each bond in the delivery basket. This serves to make the delivery acceptable to both parties. Conversion factors are used in the invoice process to calculate the value of the delivered bond that is equal to that speciﬁed by the contract. In some texts the conversion factor is known as the  price factor . The concept of the conversion factor was developed by CBOT in the 1970s.
Table 1.3 shows the conversion factors for all gilts that were eligible for delivery as of 30 August 2001 for the September 2001 to September 2002 contracts. Notice how the conversion factors exhibit the ‘‘pull to par’’, decreasing towards 1.00 for those with a coupon above the notional  $7\%$   and increasing towards 1.00 for bonds with a coupon below  $7\%$  . The passage of time also shows bonds falling out of the delivery basket, and the introduction of a new issue into the basket, the   $5\%$   gilt maturing 7 March 2012.

The yield obtainable on bonds that have different coupons but identical maturities can be equalised by adjusting the price for each bond. This principle is used to calculate the conversion factors for different bonds. The conversion factor for a bond is the price per £1 (or per  $\S1,\in1$  , and so on) at which the bond would give a yield equal to the yield of the notional coupon speciﬁed in the futures contract. This is  $7\%$   in the case of the long gilt contract,  $6\%$   for the Treasury long bond, and so on. In other words the conversion factor for each bond is the price such that every bond would provide an investor with the same yield if purchased; or, the price at which a deliverable bond would trade if its gross redemption yield was   $7\%$   (or   $6\%$  , and so on). The yield calculation is rounded to whole quarters, given the delivery month cycle of futures. Futures exchanges calculate conversion factors effective either on the exact delivery date, where a single date is deﬁned, or (as at LIFFE) on the ﬁrst day of the delivery month if delivery can take place at any time during the delivery month.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a79131a61fd3a9967ab24e934d99f5622e4d40f1f70481dd2031a934fb6c749e.jpg)
Table 1.3:  Conversion factors for deliverable gilts, Dec00 to Mar02 long gilt contracts. Source: LIFFE.
The conversion factor is assigned by the exchange to each bond in the delivery basket at the start of trading of each contract. It remains constant throughout the life of the contract. A particular bond that remains in the delivery basket over a length of time will have different conversion factors for successive contracts. For example the  $9\%$   UK Treasury maturing on 13 October 2008 had conversion factors of 1.1454317, 1.1429955 and 1.1407155 for the LIFFE long gilt contracts that matured in June, September and December 1998 respectively.

Other things being equal, bonds with a higher coupon will have larger conversion factors than those with lower coupons. For bonds with the same coupon, maturity has an inﬂuence, though this is slightly less obvious. For bonds with coupons below the notional rate deﬁned in the contract description, the conversion factor is smaller for bonds with a longer maturity. The opposite is true for bonds carrying coupons in excess of the notional coupon rate, for which the conversion factor will be larger the longer the maturity. This effect arises from the mathematics of ﬁxed-interest securities. Bonds with coupon below current market yields will trade at a discount. This discount is larger the longer the maturity, because it is a disadvantage to hold a bond paying a coupon lower than current market rates, and this disadvantage is greater the longer the period to the bond maturing. Conversely, bonds with coupons above current market yields trade at a premium which will be greater the longer the maturity.

To help calculate the  invoice price  of a bond on delivery, we multiply the price of the ﬁnal settlement price of the futures contract with its conversion factor. This gives us the  converted price . The price payable by the long future on delivery of the bond is the invoice price, and this is the futures settlement price plus accrued interest. This was shown in simple fashion as (1.1). The actual invoice price, calculated once the actual bond being delivered is known, is given by

$$
P_{I n v}=\left(M_{f u t}\times P_{f u t s e t t}\times C F\right)+A I
$$

where

$P_{I n\nu}$  is the invoice price;  $M_{f u t}$  is the nominal value of the delivered bonds as speciﬁed in the contract; P futsett is the futures settlement price.

# Invoice amount

When the bond is delivered, the long pays the short an invoice amount:

$$
I n v o i c e d=(E D S P/100\times C F\times\mathrm{Normal})+A I
$$

The settlement price (or  exchange delivery settlement price , EDSP) is the trading price per £100 nominal for the futures contract on the last day of trading, and is conﬁrmed by the Exchange. The invoice amount includes
accrued interest because the futures contract is traded at a  clean  price and does not include accrued interest.

# Example 1.1: Calculating the invoice price

A futures contract settles at 102.50. The contract speciﬁes £100,000 nominal of the underlying bond. The delivered bond has a conversion factor of 1.14579 and accrued interest of 0.73973. The settlement price is equal to   $1.025\%$   of the nominal value (par value). The invoice price is calculated as

$$
\begin{array}{l c}{P_{I n\nu}=(100,000\times1.025\times1.14579)+0.73973}\\ {\qquad=117,443+0.73973}\end{array}
$$

For the Treasury long bond the conversion factor is calculated using (1.10),

$$
C F=\frac{1}{1.03^{t/6}}\left[\frac{C}{2}+\frac{C}{0.06}\left(1-\frac{1}{1.03^{2N}}\right)+\frac{1}{1.03^{2N}}\right]
$$

where

$N$  is the complete years to maturity as at the delivery month;

$t$  is the number of months in excess of the whole    $N$   (rounded  down  to whole quarters).

The LIFFE conversion factor for the long gilt is reproduced in Appendix 1.1. The formula is actually the same, beginners are invited to explain that this is indeed so. To illustrate (1.10), if a deliverable Treasury bond has a maturity of 19 years and 5 months,  $t$   is 3 because the 5 months is rounded down to one quarter or 3 months. Hence if the maturity is 19 years and 9 months,    $t$   is 6.

It is worth summa rising what we know so far about conversion factors:

j conversion factors remain constant for a bond from the moment they are assigned to the expiry of the contract;

13   j conversion factors are different for each bond and for each contract; from Table 1.3, which relates to the long gilt contract and its notional coupon of  $7\%$  , we see that conversion factors for bonds with coupons higher than   $7\%$  diminish in value for each successive contract month, while those for bonds with coupons lower than  $7\%$   rise in value for successive contract months. This reﬂects the ‘‘pull to par’’ effect, which for bonds with the higher coupon is falling from a premium and for bonds with the lower coupon is rising from a discount;
j the conversion factor is used to calculate the invoice price of a bond that is delivered into a futures contract; j bonds with coupons greater than the notional coupon of the futures contract have a conversion factor higher than 1, while bonds with coupons lower than the notional coupon have a conversion factor lower than 1.

The conversion factor is not a hedge ratio, as has been strongly emphasised by both   Burghardt and Galitz, and should not be used as such. Certain textbooks and market practitioners have suggested that using the ratio of two bonds’ conversion factors can be an effective hedge ratio, for hedging a bond position, rather than the traditional approach of using the ratio of basis point values. This is fallacious and will lead to serious errors. The conversion factor of a bond is inﬂuenced primarily by its coupon, whereas the modiﬁed duration of a bond (from which is derived the BPV) is a function mainly of its term to maturity. Hence it is not correct to substitute them. If an investor was hedging a position in a long-dated bond of low coupon, and the current CTD bond was a short-dated bond of high coupon, the volatility ratio calculated using the respective conversion factors would be lower than unity. However, using respective BPVs would result in a volatility ratio higher than one. This example illustrates how using a ratio of conversion factors can result in serious hedging errors, and this approach must not be adopted.

Using conversion factors provides an effective system for making all deliverable bonds perfect substitutes for one another. The system is not perfect of course. Conversion factors are calculated to equalise returns at a single uniform yield, the notional coupon rate speciﬁed in the contract spec i cation. In practice though bonds trade at different yields, resulting in the yield curve. Hence despite the use of conversion factors, bonds will not be precisely ‘‘equal’’ at the time of delivery. Some bonds will be relatively more expensive, some cheaper; one particular bond will be the  cheapest-to-deliver  bond. The cheapest-to-deliver (CTD) bond is an important concept in the pricing of bond futures contracts.

# 1.3.4 The bond basis

Basis trading arises from the difference between the current clean price of a bond and the (implied) forward clean price at which the bond is bought through the purchase of a futures contract. The difference between these two prices is known as the  gross basis . This is the bond basis to which the market refers, the difference between the bond’s spot cash price and the price implied by the current price of the futures contract. The latter is given by multiplying the futures price by the relevant bond’s conversion factor.

The formula for calculating the gross basis is therefore:

$$
B a s i s=P_{b o n d}-\left(P_{f u t}\times C F\right)
$$
 '
From (1.11) we might think that if we sell a futures contract short, in effect this guarantees an ability to deliver the bond at the futures delivery date and receive a known price for the bond. However, the price payable for the bond at delivery is based on the future’s ﬁnal settlement price, and not the trading price of the future at any time beforehand, and so this thinking is erroneous.

In the Treasury market both cash and futures prices are quoted as points and ticks (32nds) per  $\S100$   nominal value, and if necessary as half-ticks or 64ths. A 64th price is indicated by   $^{\mathrm{a+}}$  .

The gross basis can be explained essentially as the difference between the running yield on the bond and the current repo (money market) rate. However, a residual factor exists due to the delivery option implicit in the design of the futures contract and to the daily marking-to-market of the contract, both of which are more difﬁcult to quantify. This residual amount is known as the  net basis . Net basis is the gross basis adjusted for net carry. Net carry is the actual coupon income and re-investment less borrowing expense, which is at the security’s actual repo or money market ﬁnancing rate.

Figure 1.6 is the Bloomberg page DLV of the deliverable bonds for the June 2000 long gilt contract, and shows the conversion factors and gross basis value for each bond in the basket.

# Example 1.2: The gross basis

Consider the following market details, all relating to one instantaneous point in time:

Settlement date 16 March 2000 Futures delivery date 30 June 2000 Days to delivery 106 Bond price (UKT  $9\%$   2011) 131.4610 Accrued interest 1.5780822 Accrued to delivery 4.1917808 Futures price (M0 LIFFE long gilt) 112.98 Conversion factor 1.1525705 Cash market repo rate  $6.24\%$

We can calculate the gross basis that would apply in a hypothetical cash-andcarry trade, where there is a simultaneous purchase of the bond and sale of the futures contract as shown below.

bond purchase    outflow of funds:   $131.461+1.5781=133.0390822$   $(112.98\times1.1525705)+4.192=134.409196$  future sale    inflow of funds:

The gross basis is   $131.4610-(112.98\times1.1525705)$   or 1.24358491.
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/98fb8e6583575614f2a5a74384c74d83c2a66850b1eefc0221f3f05b05540555.jpg)
Figure 1.6:  Delivery basket for Jun00 long gilt, Bloomberg page DLV, 15 March 2000.      Bloomberg L.P. Reproduced with permission

# 1.3.5 The net basis

We’ve seen from the previous section that gross basis measures the carry on a bond that applies during the life of the futures contract. Because of other factors associated with the delivery into a futures contract, principally that delivery is at the option of the short future, the gross basis is not the actual carry that would be incurred if a trader put on a cash versus futures trade. This is measured by the  net basis . The net basis causes much confusion amongst market participants, but it is a straightforward concept. Burghardt states that the net basis is the difference   between a bond’s basis and its total carry to delivery. Plona describes net basis as the difference between the  implied repo rate  and the general collateral repo rate. We consider the implied repo rate (IRR) in the next section.

Both descriptions are good ways in which to consider net basis. Essentially the net basis is the gross basis adjusted for net carry. Net carry is the actual coupon income (and any re-investment income) minus borrowing expense, which is at the security’s actual repo (money market) rate. The net basis is therefore the true ‘‘economic basis’’ and measures the net gain from a simultaneous position in the cash bond and the futures contract. A positive value represents a  loss  or net cost to the long cash/short futures position, and the net basis is the expected  proﬁt  for the short cash/long futures position (where the actual repo rate used is the reverse repo rate). The opposite is true for negative net basis values.
The net basis is calculated on the assumption that a basis trade is conducted by the arb it rage ur borrowing funds to purchase the cheapest-to-deliver bond, ﬁnancing it in the repo market, and shorting the futures contract. It measures the maximum  loss  that would be suffered by holding this position until the contract expiry date. The net basis should be negative as a loss measure; a positive   net basis indicates the potential proﬁt from such a trade. On the other hand, a negative net basis theoretically indicates the potential proﬁt from a short bond/ long futures position.

To calculate the net basis, we need to make an assumption about the ﬁnancing   rates that would apply to a basis trade. This centres on the repo rate that is applicable to the cash bond element of the trade. Analysts use one of two methods:

j Using the speciﬁc repo rate for the cash bond, ﬁxed to the maturity date. This is a logical approach, as it provides an accurate measure of the ﬁnancing cost associated with running a long position in the bond, and then delivering it into the futures exchange. Calculating net basis under this method provides a measure of the value of the delivery option; j Using the overnight GC repo rate, assuming therefore that the bond position is ﬁnanced on a daily basis. Assuming that the overnight rate will be maintained more or less over the term of the trade is risky.

The box illustrates calculation of the net basis.

# Example 1.3: The net basis

Consider this calculation for the June 1998 long gilt future contract. At this time the ‘‘special ex’’ rule applies to delivery of bonds into the contract, something that no longer applied with the removal of special ex-trading in August 1998.

Trade date 24 April 1998 Settlement date 25 April 1998 M8 long gilt future price 109.65625 CTD bond   $(8\%$   Treasury 2007) 106.34375 Accrued interest 2.30548 Accrued to delivery 3.4232882
Dirty price 108.64932 1 Conversion factor (8 = 2 %  2007) 0.9674064 Repo rate 6.36 %

The converted price of the bond (that is, through the futures contract) is:

$109.65625\times0.9674064=106.08216.$

The market clean price is 106.34375, therefore the gross basis is:

$$
106.34375-106.08216=0.26159.
$$

Due to the special-ex rule in this case, the last day for delivery of   $8\%$   Treasury 2007 into the futures contract is 12 June. This makes the term 48 days. The total price paid including accrued interest will be 108.64923. To ﬁnance that using repo for 48 days until 12 June will cost £0.9087243. The holder of the gilt will however earn 48 days’ accrued interest of £1.1178082. Therefore, buying the bond direct gives the owner an income advantage of £0.2090839.

The difference between the gross basis and this income advantage is  $£0.216159-£0.2090839)$  , that is £0.0525. It therefore represents the gain by buying the gilt using the futures contract rather than buying directly in the market.

Of course the long gilt contract gives the futures seller the right to deliver any of the gilts in the delivery basket and on any day of the delivery month. If the CTD is bought through a futures contract the buyer may ﬁnd that because of market movements, a different gilt is delivered. The futures short in effect holds an option which decreases the value of the futures contract to the long.

For this reason the  net  basis is usually positive. The futures contract is also marked-to-market which means that the gain or loss on the contract is spread over the life of the contract, in contrast to a forward contract. This effect is small but will again lead to the net basis differing from zero.

The net basis is given by

$N e t B a s i s=(108.64923\times(1+6.36\times(48/36500)))$   ð ð 109 : 65625 6 0 : 9674064 Þ þ  3 : 423882 Þ ¼  109 : 5579543    109 : 50544625  $=0.05250805$  :

# 1.3.6 The implied repo rate

In a basis trade the rate implied by the strategy is known as a repo rate because it is equivalent to a  repurchase  agreement with the futures market. In effect the short future lends money to the futures market: the short future agrees to buy a bond with a simultaneous provision to sell it back to the market at a predetermined price and to receive a rate of interest on his money, the repo rate. It is the  implied repo rate  because it is an expected repo rate gain if the trade was carried out. In some literature it is suggested as a complex and obscure calculation, in fact the implied repo rate (IRR) is very straightforward to calculate. It is the theoretical return from a basis trade of long cash bond against short future, with the bond delivered into the future on expiry.
The IRR is a measure of return from a basis trade. Consider the cash ﬂows involved when one is long bond/short future. We have:

j a cash outﬂow from purchasing the bond; j a cash inﬂow on delivery into the future, including the accrued interest to the delivery date; j the cash borrowed to ﬁnance the trade.

We simply therefore wish to have the percentage return of the investment over the borrowing cost. That is,

$$
\mathrm{IRR}=\frac{\left(\left(P_{f u t s}\times C F\right)+A I_{d e l}\right)-\left(P_{b o n d}+A I\right)}{P_{b o n d}+A I}\times\frac{M}{D a y s}
$$

$M$  where  is the day-base, either 360 or 365 and  Days  is the term of the trade. There 19   is no need to remember this version though, Burghardt simpliﬁes it to

$$
\mathrm{IRR}=\left(\frac{P_{i n v o i c e}-P_{b o n d}}{P_{b o n d}}\right)\times\left(\frac{360}{n}\right)
$$

which is identical to (1.12), with    $n$   for the number of days to delivery, and all prices still include accrued interest, at the time of the trade (bond) or to delivery (future). The formula written as (1.13) is easy to explain. The invoice price is the futures invoice price, the amount from the delivery on expiry. Of course the actual invoice price is a function of the ﬁnal futures settlement price, but we adjust the current futures price with the conversion factor to allow for this.

Note that Bloomberg quotes the formula in still more simpliﬁed fashion, as

$$
\mathrm{IRR}=\left(\frac{P_{F u t s I n v o i c e}}{P_{b o n d}}-1\right)\times\left(\frac{360}{n}\right)
$$

with the 360-day base associated with the US Treasury market.

Both (1.12) and (1.13) assume that no coupon is paid during the trade. If a coupon is paid during the trade, it is considered as being reinvested, and the cash ﬂow total must therefore include both the coupon and the reinvestment income generated. The reinvest-ment rate used in the market is one of the following:
j the implied repo rate; j the bond’s yield-to-maturity. This is described as being consistent with the bond yield calculation itself, which assumes reinvestment of coupon at the bond yield; j the overnight repo rate, and rolled over. This is justiﬁed on the basis that traders in fact do not reinvest the coupon but use the funds to reduce funding costs.

The ﬁrst two are assumed to apply to maturity, while the second must be calculated at the prevailing rate each day. If the reinvestment rate is assumed to be the IRR, it is the rate that results in

$$
P_{b o n d}\times\Big(1+\mathrm{{IRR}}\Big(\frac{n}{M}\Big)\Big)=P_{I n v o i c e}+\Bigg(\frac{C}{2}\Bigg)\times\Big(1+\mathrm{{IRR}}\Big(\frac{n_{2}}{M}\Big)\Big)
$$

where    $n_{2}$   is the number of days between the coupon payment and the futures expiry (delivery) date. Expression (1.15) is then rearranged for the implied repo rate, to give us

$$
\mathrm{IRR}={\frac{\left(P_{I n v o i c e}+{\frac{C}{2}}-P_{b o n d}\right)\times M}{\left(P_{b o n d}\times n\right)-\left({\frac{C}{2}}\times n_{2}\right)}}
$$

The deliverable bond that has the highest implied repo rate is the  cheapest-todeliver  bond or CTD. We see from (1.16) that the IRR is a function of the bond price, the value of which is compared to the forward price for the bond implied by futures price. As such the status of CTD bond reﬂects the bond’s price (in other words its yield). If the yield of a bond within the delivery basket moves suf cie ntl y vis-a\`-vis the other deliverable bonds, it may become the CTD bond. A change in the cheapest bond is an important development and any such change should be anticipated in advance by good traders.

The bond with the highest implied repo rate will, almost invariably, have the lowest net basis. On rare occasions this will not be observed. When two bonds each have implied repo rates that are very similar, it is sometimes the case that the bond with the (slightly) lower implied repo rate has a (slightly) lower net basis.

The CTD bond is just that: it is the cheapest bond to deliver into the futures contract in terms of running costs. The short future has the delivery option, and will elect to deliver the CTD bond unless there is a reason it cannot, in which case it will deliver the next cheapest at greater cost to itself. Assuming that a basis trade is put on with the CTD bond against the future, if the CTD changes then the position becomes useless and will be unwound at great loss. The CTD bond is what the market will treat as the actual underlying bond of the futures contract, and it is closely observed. Pricing theory informs us that the futures price will track the CTD bond price; in fact it is the other way around, with the liquidity and transparency of the futures contract and its price meaning that the CTD bond price tracks that of the future. Under the terms of the long gilt contract, the CTD gilt can be delivered on any business day of the delivery month, but in practice only one of two days are ever used to make delivery: the ﬁrst (business) day of the delivery month or the last (delivery) day of the month. If the current yield on the CTD gilt exceeds the money market repo rate, the bond will be delivered on the last business day of the month, because the short future earns more by holding on to the bond than by delivering it and investing the proceeds in the money market; otherwise the bond will be delivered on the ﬁrst business day of the delivery month. Until very recently a gilt that was eligible for trading  special ex-dividend  on any day of the delivery month was not eligible for delivery into that gilt contract. However, from August 1998 the provision for special ex-dividend trading was removed from gilts, so this consideration no longer applies. Other gilts that are not   eligible for delivery are index-linked, partly paid or convertible gilts. For gilts the IRR for all deliverable bonds can be calculated using (1.12) in the normal way. However if a bond goes ex-dividend between trade date and delivery date, a modi cation is required in which the interest accrued is negative during the exdividend period.
# Example 1.4: The implied repo rate

Another way of looking at the concept of the cheapest-to-deliver bond is in terms of the implied repo rate. The CTD bond is the bond that gives the highest implied repo rate (IRR) to the short from a cash-and-carry trade, that is a strategy of buying the bond (with borrowed funds) in the cash market and selling it forward into the futures market. The bond is funded in the repo market, and by selling it forward the trade is in effect a repo with the futures market, hence  implied  repo rate.

To illustrate we calculate the IRR for the  $9\%$   Treasury 2008, a UK gilt, at the time that the ‘‘front month’’ contract was the December 1998 contract. The price of the gilt is 129.0834. The December 1998 long gilt futures contract is trading at 114.50. The date is 1 October. The money market rate on this date is  $7.25\%$   $9\%$   $6.972\%$  . As the current (or  running ) yield on the  2008, at   is lower
than the money market rate, it will be delivered at the beginning of December (that is, in 61 days from now). To identify the CTD bond we would need to calculate the IRR for all eligible bonds. We use the conversion factor for the bond which is 1.140715, calculated and given out by LIFFE before the futures contract began trading.

The cash outﬂow in a cash-and-carry trade is:

bond dirty price 129.0834 interest cost (1 October – 1 December)  $129.0834\times(0.0725\times(61/365))$  Total outﬂow 130.6474.

The bond (whose price includes 171 days’ accrued interest on 1 October) has to be ﬁnanced at the money market rate of  $7.25\%$   for the 61 days between 1 October and 1 December, when the bond (if it is still the CTD) is delivered into the futures market.

The cash inﬂow per £100 nominal as a result of this trade is:

Implied clean price of bond on 1 December  $114.50\times1.1407155$  (futures price on 1 October multiplied by conversion factor)

Accrued interest (1 October – 1 December)  $\textdollar{\Sigma}9\times(61/365)$  Total inﬂow 132.11603

The implied price of the bond on 1 December equals the futures price on 1 October multiplied by the conversion factor for the bond. Because the futures price is quoted clean, accrued interest has to be added to obtain the implied dirty price on 1 December.

This cash-and-carry trade which operates for 61 days from 1 October to 1 December generates a rate of return or  implied repo rate  of:

$$
\mathrm{IRR}=\left({\frac{132.11603-130.6474}{130.6474}}\right)\times{\frac{365}{61}}\times100
$$

# Example 1.5: Calculating gross basis, net basis and implied repo rate

The gross basis is the difference between the actual price of the bond and the forward price of the bond as implied by the price of the futures contract, and represents the carrying cost of the bond. This is the actual difference between the coupon gain and re-investment minus the carry costs (which is at the actual money market repo rate). A positive net basis represents the loss that would result from a long cash/short futures position, and therefore the theoretical gain from a short cash/long futures trade, where the actual repo rate is the reverse repo rate transacted when covering the short cash position.
The implied repo rate is the theoretical return from a long cash/short futures trade, assuming that the trader is short the number of futures equal to the bond’s conversion factor for each £100,000 nominal of bonds held. Any coupon payments are assumed to be reinvested at the implied repo rate.

Earlier in this book we presented the formulae for gross basis and implied repo rate. The net basis is given by:

$$
\mathrm{Net~basis}=(P_{b o n d}\times(1+r\times D e l/36500))-\left(\left(P_{f u t}\times C F\right)+A I_{d e l}\right)
$$

where

$P_{b o n d}$  is the bond dirty price;  $r$  is the actual repo rate (expressed as per cent  $\times\;100.$  );  $D e l$  is the days to delivery;  $P_{f u t}$  is the futures price;  $C F$  is the bond’s conversion factor;  $A I_{d e l}$  is the bond’s accrued interest to delivery.

For net basis calculations in Treasury or euro markets the appropriate 360-day basis is used.

The calculations are for the CTD bond for the long gilt contract, which was the  $6\%$   2010 gilt. We use mid prices for the bond. The trade is buying the cash and simultaneously selling the future. Note that gilts accrue on actual/ actual basis and there were 184 days in the interest period 25 May–25 November 2001. The accrued interest calculation is therefore (80/  $184\times(6.25\times0.5))$   for the ﬁrst date and   $(126/184\,\times\,(6.25\,\times\,0.5))$  ) for the delivery date.

Settlement date 13 August 2001 Futures price 115.94  $6\%$   Treasury 25/11/10 price 110.20 Conversion factor 0.9494956 Repo rate  $4.90\%$

# Calculations

Cash out on 13/8/2001 110.20 plus accrued 80 days  $=111.558696$  Cash in on 28/9/021 (  $115.94\;\times\;0.9494956)$  ) plus  $=110.08452$  accrued + 2.139946 (46 days later)  $=112.2244659$

# Gross basis
# Net basis

ð 111 : 558696 6 ð 1  þ  4 : 90 6 46 = 36500 ÞÞ   112 : 2244659 ¼  0 : 0231432

# Implied repo rate

$$
\begin{array}{r l r}{(112.2244659/111.558696-1)\times;(365/46)\times;100}&{{}\quad}&{=4.735390\%}\end{array}
$$

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f47ffcb8ed90a432be9c75ec07b6120a6b7a857f365f4a668ff65237067a5a7e.jpg)
Figure 1.7:  Bloomberg YA page for   $6\%$   2010 gilt, showing accrued interest for value 13 August 2001.      Bloomberg L.P. Reproduced with permission

These calculations are conﬁrmed by looking at the Bloomberg screens YA and DLV for value on 13 August 2001, as shown in Figures 1.7 and 1.8 respectively. Figure 1.7 is selected for the   $6\%$   2010 gilt and Figure 1.8 is selected for the front month contract at the time, the Sep01 gilt future. Figure 1.9 shows the change in CTD bond status between the   $6\%$   2010 gilt and the  $9\%$   2011 gilt, the second cheapest bond at the time of the analysis, with changes in the futures price. The change of CTD status with changes in the implied repo rate is shown in Figure 1.10. Both are Bloomberg page HCG.

Page DLV on Bloomberg lists deliverable bonds for any selected futures contract. Bonds are listed in order of declining  implied repo rate ; the user can select in increasing or decreasing order of implied repo rate, basis, yield, maturity, coupon or duration. The user can also select the price source for the
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/62f97ab377900a755680002fba3067cbfaf0d3b20a1037ffa87b9f4bf5cc4644.jpg)

Figure 1.8:  Bloomberg DLV page for Sep01 (U1) gilt contract, showing gross basis, net basis and IRR for trade date 12 August 2001.    Bloomberg L.P. Reproduced with permission

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/093053bf30e013d0c93deb9ad77a568099f28254268766a58a4d54c64e643f8e.jpg)

#

Figure 1.9:  Bloomberg HCG page for Sep01 (U1) gilt contract, showing CTD bond history up to 12 August 2001 with changes in futures price.    Bloomberg L.P. Reproduced with permission
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/78e71895e5d967178c4aa370cab7077b8943ea9f9af91c402d2eadc75aacb76d.jpg)
Figure 1.10:  Bloomberg HCG page for Sep01 (U1) gilt contract, showing CTD bond history up to 12 August 2001, with changes in implied repo rate.      Bloomberg L.P. Reproduced with permission

bonds (in our example set at ‘‘Bloomberg Generic’’ rather than any speciﬁc bank or market maker) and the current cash repo rate.

# 1.4 Selecting the cheapest-to-deliver bond

As we’ve discussed just now there are two competing deﬁnitions for identifying the bond that is the cheapest-to-deliver issue, and they almost always, but not always, identify the same issue as ‘‘cheapest’’. The general rule is that the issue with the highest implied repo rate, and/or the issue with the lowest net basis is the CTD bond. Most academic literature uses the ﬁrst deﬁnition, whereas market practitioners often argue that the net basis method should be used since it measures the actual proﬁt and loss for an actual cash-and-carry trade.

It is up to the individual trader to decide which method to use as the basis for analysis. For example, Bloomberg terminals use the IRR method. The just i cation for this is that many market participants accept that the IRR method is appropriate to the cash-and-carry investor seeking maximum return per dollar invested. The main area of disagreement regards those cases where an arb it rage ur ﬁnances (repos) the cash side of the trade and the net basis measures their resulting proﬁt or loss. In a Bloomberg analysis this net basis is presented as percentage points of par (the same units as price), although some practitioners express it as p&l per million bonds. It is primarily because the net basis is per par amount rather than per pound invested that the two methods occasionally identify different ‘‘cheapest’’ issues. Note that in practice net basis will always be a loss, otherwise traders would arbitrage an inﬁnite amount of any issue with a proﬁtable net basis. Therefore the basis method identiﬁes the issue which has the  smallest loss  per million pounds nominal as the cheapest issue.
The only reason a trader is willing to accept this guaranteed loss is that they don’t intend to follow through exactly with this trade to maturity. Being long of the basis, that is short futures, essentially gives the trader numerous delivery and trading options; the cost of these is the net basis that the trader pays. In effect the trader is buying options for the cost of the net basis. The number of options they buy is indicated by the  conversion factor  since that is the hedge factor for the cheapest issue. Therefore the cost per option is the net basis divided by the conversion factor. When ranked by net basis per contract (that is, divided by the conversion factor), the cheapest by this method invariably agrees with the IRR method.

# 1.5 Trading the basis

# 1.5.1 The basis position

Basis trading or cash-and-carry trading is an arbitrage-driven activity that involves the simultaneous trading of cash bonds and exchange-traded bond futures contracts. Traders speak of going ‘‘long the basis’’ or of ‘‘buying the basis’’ when they buy the bond and sell the future. The equivalent number of futures contracts to trade per 100,000 nominal value of cash bond is given by the conversion factor. The opposite position, buying the future and selling the cash bond, is known as ‘‘selling the basis’’ or ‘‘going short the basis’’. Someone who is long the basis has bought the basis itself (hence the expression!) and will therefore proﬁt if the basis increases, that is, the price of the bond increases relative to the price of the futures   contract. A trader who has sold the basis will gain if the basis decreases, that is the price of the bond falls relative to the futures contract price.

Ideally each side of the position will be executed simultaneously, and most derivatives exchanges have a basis trading facility that enables a party to undertake this. Certain government bond primary dealers will quote a price in the basis as well. If this is not possible, the trade can be put on separately, known as ‘‘legging into the trade’’ as each leg is carried out at different times. To do this, generally the cash bond position is put on ﬁrst and then the futures position, as the latter is more liquid and transparent. Whichever way round the trade is effected though, this method carries with it some risk, as the price of the leg yet to   be traded can move against you, complicating the completion of the trade. If this happens there is a danger that the second leg is put on one or two ticks offside, and straight away the trade starts off at a loss. This should be avoided if at all possible. There is also a bid-offer spread to take into account, for both cash and future positions.
The arb it rage ur hopes to generate proﬁt from a basis trade, and this will be achieved from changes in the basis itself and/or gains from the funding or carry. If the net funding cost is positive, then this will add to any proﬁt or reduce losses arising from changes in the basis. This is where the repo rate comes in. The trader may elect to fund the bond position, whether long or short, in overnight repo but generally the best approach is to ﬁx a term repo, with expiry date matching the date at which the trader hopes to unwind the trade. This may be to the contract expiry date or before. If short the basis, it is vital that the repo desk is aware if there is any chance that the bond goes special, as this could prove costly unless the repo is ﬁxed to the trade maturity. There is also a bid-offer spread to consider with the repo rate, and while this is usually quite small for GC repo, say as little as 3 basis points, it may be wider for speciﬁcs, from 10 to 20 basis points.

In the next chapter we consider further issues in trading the basis.

# A summary of the basic position

# Cash-and-carry trading

In this trade, we undertake simultaneous transactions in:

j buying the cash bond; j selling the bond futures contract.

The trader buys the cheapest-to-deliver bond, the ﬁnancing of which is ﬁxed in the repo market (trader pays the repo rate). The trader believes that the bond is cheaper in the cash market than its forward price implied by the price of the futures contract. On the expiry date of the futures contract, any bond in the deliverable basket is eligible for delivery, but (assuming no change in CTD status) the trader will deliver the bond they are long of. The trader’s potential gain arises from the mis-pricing of the bond in the cash market.

# Reverse cash-and-carry trading

In this trade we undertake simultaneous transactions by:

j selling the CTD bond in the cash market, and covering the position by entering into reverse repo (the trader receives the repo rate);
j buying the equivalent number of futures contracts.

For the reverse basis trade to generate proﬁt there can be no change in the CTD status of the bond; if another bond becomes the CTD at contract expiry, a loss will result. On futures expiry, the trader is delivered into the bond in which they have a short position, and this also enables them to close-out the repo trade. Theoretical proﬁt is generated because the invoice price paid for the bond is lower than the price received at the start of the trade in the cash market, once funding costs have been taken into account.

# Appendices

# Appendix 1.1: The LIFFE long gilt conversion factor

Here we describe the process used for the calculation of the  conversion factor  or price factor  for deliverable bonds of the long gilt contract. The contract speciﬁes a bond of maturity  $8\%–13$   years and a notional coupon of   $7\%$  . For each bond that is eligible to be in the delivery basket, the conversion factor is given by the following expression:    $P(7)/100$   where the numerator    $P(7)$   is equal to the price per £100 nominal of the deliverable gilt at which it has a gross redemption yield of   $7\%$  , calculated as at the ﬁrst day of the delivery month, less the accrued interest on the bond on that day. This calculation uses the formula given at (1.17) and the expression used to calculate accrued interest. The analysis is adapted, with permission, from LIFFE’s technical document.

The numerator    $P(7)$   is given by (1.17):

$$
P(7)={\frac{1}{1.035^{t/s}}}\left(c_{1}+{\frac{c_{2}}{1.035}}+{\frac{C}{0.07}}\left({\frac{1}{1.035}}-{\frac{1}{1.035^{n}}}\right)+{\frac{100}{1.035^{n}}}\right)-A I
$$

# where

$c_{1}$  is the cash ﬂow due on the following quasi-coupon date, per £100 nominal of the gilt.    $c_{1}$   will be zero if the ﬁrst day of the delivery month occurs in the ex-dividend period or if the gilt has a long ﬁrst coupon period and the ﬁrst day of the delivery month occurs in the ﬁrst full coupon period.    $c_{1}$   will be less than    $C/2$   if the ﬁrst day of the delivery month falls in a short ﬁrst coupon period.    $c_{1}$   will be greater than    $C/2$   if the ﬁrst day of the delivery month falls in a long ﬁrst coupon period and the ﬁrst day of the delivery month occurs in the second full coupon period;  $c_{2}$  is the cash ﬂow due on the next but one quasi-coupon date, per £100 nominal of the gilt.    $c_{2}$   will be greater than    $C/2$   if the ﬁrst day of the delivery month falls in a long ﬁrst coupon period and in the ﬁrst full coupon period. In all other cases,  $c_{2}\!=\!C/2$  ;
$C$  is the annual coupon of the gilt, per £100 nominal;  $t$  is the number of calendar days from and including the ﬁrst day of the delivery month up to but excluding the next quasi-coupon date;  $s$  is the number of calendar days in the full coupon period in which the ﬁrst day of the delivery month occurs;  $n$  is the number of full coupon periods between the following quasi-coupon date and the redemption date; AI is the accrued interest per £100 nominal of the gilt.

The accrued interest used in the formula above is given according to the following procedures.

j If the ﬁrst day of the delivery month occurs in a standard coupon period, and the ﬁrst day of the delivery month occurs on or before the ex-dividend date, then

$$
A I=\frac{t}{s}\times\frac{C}{2}
$$

j If the ﬁrst day of the delivery month occurs in a standard coupon period, and the ﬁrst day of the delivery month occurs after the ex-dividend date, then:

$$
A I=\left({\frac{t}{s}}-1\right)\times{\frac{C}{2}}
$$

where

$t$  is the number of calendar days from and including the last coupon date up to but excluding the ﬁrst day of the delivery month;  $s$  is the number of calendar days in the full coupon period in which the ﬁrst day of the delivery month occurs.

j If the ﬁrst day of the delivery month occurs in a short ﬁrst coupon period, and the ﬁrst day of the delivery month occurs on or before the ex-dividend date, then

$$
A I={\frac{t^{*}}{s}}\times{\frac{C}{2}}
$$

j If the ﬁrst day of the delivery month occurs in a short ﬁrst coupon period, and the ﬁrst day of the delivery month occurs after the ex-dividend date, then

$$
A I=\left({\frac{t^{*}-n}{s}}\right)\times{\frac{C}{2}}
$$

where
$t^{*}$  is the number of calendar days from and including the issue date up to but excluding the ﬁrst day of the delivery month;  $n$  is the number of calendar days from and including the issue date up to but excluding the next quasi-coupon date.

j If the ﬁrst day of the delivery month occurs in a long ﬁrst coupon period, and during the ﬁrst full coupon period, then

$$
A I=\frac{u}{s_{\mathrm{l}}}\times\frac{C}{2}
$$

j If the ﬁrst day of the delivery month occurs in a long ﬁrst coupon period, and during the second full coupon period and on or before the ex-dividend date, then

$$
A I=\left(\frac{p_{1}}{s_{1}}+\frac{p_{2}}{s_{2}}\right)\times\frac{C}{2}
$$

j If the ﬁrst day of the delivery month occurs in a long ﬁrst coupon period, and during the second full coupon period and after the ex-dividend date, then

$$
A I=\left({\frac{p_{2}}{s_{2}}}-1\right)\times{\frac{C}{2}}
$$

where

$u$  is the number of calendar days from and including the issue date up to but excluding the ﬁrst day of the delivery month;  $s_{1}$  is the number of calendar days in the full coupon period in which the issue date occurs;  $s_{2}$  is the number of days in the next full coupon period after the full coupon period in which the issue date occurs;  $p_{1}$  is the number of calendar days from and including the issue date up to but excluding the next quasi-coupon date;  $p_{2}$  is the number of calendar days from and including the quasi-coupon date after the issue date up to but excluding the ﬁrst day of the delivery month, which falls in the next full coupon period after the full coupon period in which the issue date occurs.
# Basis Trading and the Implied Repo Rate 

In this chapter we look in more detail at some fundamentals behind the basis, including the factors that drive its behaviour, and we also consider implications of the short future’s delivery option. There is also, in an appendix at the back of this book, recent delivery history for the LIFFE long gilt future, for illustrative purposes and to observe delivery patterns.

# 2.1 Analysing the basis

Having discussed, in the previous chapter, the theoretical foundation behind futures prices, it is nevertheless the case that they move out of sync with the noarbitrage price and present arbitrage trading opportunities. A review of the US Treasury or the gilt bond basis relative to the bond carry would show that the basis has frequently been greater than the carry, and this would indicate mis-pricing in   the futures contracts. The anomalies in pricing are due to a number of factors, the principal one of which is that the short future has the option of delivery. That is, the short picks which bond to deliver from the basket, and the time at which it is delivered. The long future simply accepts the bond that is delivered. It is this inequality that is the option element of the contract.

We will take a look at this, but ﬁrst let’s consider the principle behind noarbitrage delivery.

# 2 2.1.1 No-arbitrage futures price

At the expiration of a futures contract, as the exchange delivery settlement price is being determined, there should be no opportunity for a market participant to generate an arbitrage proﬁt by buying bonds and selling futures; by deﬁnition, because on the last day of trading there is no uncertainty with regard to the carry costs of the bond to delivery. In fact certain exchanges arrange it so that the time between the last trading day and date for delivery is identical to the settlement   process in the cash market. On the last day, someone buying cash bonds will receive value on the same day, and with the same accrued interest, as a long future being delivered into. Thus carry cost is no longer an uncertainty and the price of the futures contract in theory must equate that of the cash bond. In other words, the basis is zero at this point.
Consider Figure 2.2, the delivery basket for the December 2001 long gilt contract. The bonds have been priced so that they all yield   $7\%$  , the notional coupon. Under these conditions, only one futures price will satisfy the noarbitrage principle. As carry is not an issue on expiry, the no-arbitrage condition is met provided there is a zero basis for one of the deliverable bonds and no negative basis for any of the other bonds. For instance, at a futures price of 100.09, following the price factor conversion the equivalent bond price would be below the market price of the  $8\%$   Treasury 2013 (the cheapest-to-deliver bond at this level) and thus maintain a positive basis. However, for the  $6.25\%$   Treasury 2010 bond, this futures price would be equivalent to a converted bond price of 95.1443. The market price of this bond is lower than this, at 94.9685. In theory a trader can buy the bond at this price, sell the futures contract at 100.09 and realise a trading gain of 0.1758 (the difference between the two prices). This is the arbitrage proﬁt. So the initial suggested price for the futures contract is too high. At a price of 100.06 the future no longer presents an opportunity for proﬁt if buying the basis; however, in theory, selling the basis against the  $9\%$   2011 bond still generates proﬁt. The long future must accept delivery of any of the bonds in the basket however, and will not be delivered this bond. So the adjusted futures price is too low.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0c317b843da4f8ec645738a36676be3f31bafd3d6ce3380dc4802d2cbdf4905d.jpg)
Figure 2.1:  Dec01 long gilt delivery basket as at 17 September 2001.    Bloomberg L.P. Reproduced with permission
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b084a5fde270603903f9883579e4c5a766ac65c3c69fa8311a22ab3e544f19fc.jpg)
Figure 2.2:  Dec01 long gilt delivery basket with yields all set at  $7\%$  .    Bloomberg L.P. Reproduced with permission

Hence we know that the arbitrage-free futures price lies between these two levels. In fact we obtain the no-arbitrage price by dividing the bonds’ market prices by their respective conversion factor. These are shown in Table 2.1. The prices in Table 2.1 are the futures prices at which there exists a zero basis for that particular underlying bond. We can determine this relationship easily from the deﬁnition of the basis, as shown below:

$$
\begin{array}{r}{B a s i s=P_{b o n d}-\left(P_{f u t}\times C F\right)}\\ {P_{b o n d}=B a s i s+\left(P_{f u t}\times C F\right)}\end{array}
$$

If we set the basis at zero, we obtain

$$
P_{f u t}=\frac{P_{b o n d}}{C F}
$$

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/0de8ddacebd2865a47bcdee7b8f0615f7782f9389b2bb2eed09d5a8c47d54ec7.jpg)
Table 2.1:  December 2001 long gilt delivery basket, price at  $7\%$   notional yield level, and zero-basis futures price
which illustrates how the deliverable bond price divided by its conversion factor is equal to the zero-basis futures price.

Taking this further, the futures price that would ensure that all the deliverable bonds have a basis that is either zero, or greater than zero, is the lowest possible zero-basis futures price. The price cannot exceed this otherwise there would be an arbitrage opportunity. If we calculate the zero-basis futures price at different yield levels, we will observe that when yields lie above the contract notional coupon, generally the shortest-dated bond carries the lowest zero-basis futures price. If yields lie below the notional coupon, frequently the longest-dated bond carries the lowest zero-basis futures price, and so is the CTD bond. This has been observed empirically by a number of authors, and formalised by Benninga (2001), for   instance. The observation reﬂects a bias in the conversion factor. We illustrate this bias in Figure 2.3, for the shortest-dated and longest-dated deliverable bonds for the June 2000 long gilt future. It shows where the futures price meets for both bonds is at the contract notional coupon of  $7\%$  , this being known as the  inﬂection point . The conversion factor bias determines which bond is the cheapest-todeliver bond, based on yield levels of bonds in the basket and their position relative to the contract notional coupon.

The relative bias of the conversion factor is a function of the duration property of the bonds. For further information on this see Meisner and La bus ze w ski (1984) and Arak  et al  (1986).

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/5f8538e5b00f839916cfe8f78955b3091ce189b1b5afa1f77d464dfc823a1908.jpg)
Figure 2.3:  Illustrating bias in the conversion factor, June 2000 long gilt future
# 2.1.2 Options embedded in bond futures contracts

In the US Treasury bond contract, the short future has the following options with regard to delivery:

j the  wild card  or  time to deliver  option; j the  quality option .

The short future may deliver during any business day of the delivery month, although the administrative process involved takes place over three days. The ﬁrst day is the  position day , the ﬁrst day on which the short declares an intent to deliver. The ﬁrst possible day that this can occur is the second-to-last business day before the ﬁrst day of the delivery month. There is an important advantage to the short future on this day: at 14:00 hours that day the exchange settlement price and hence the invoice amount to be received by the short are ﬁxed. However, the short does not have to announce an intent to deliver until 20:00 hours on that day. During the six hours after the settlement price, if interest rates rise and the bond price falls, the short will earn the difference between the actual price received for the bond, which is the EDSP set at 14:00, and the price that they will have to pay to acquire the bond. Equally if the bond is in the short’s possession, the price received for the short future delivery will be higher than the market price of the bond. The second day is the  notice of intention day , and during this day the exchange clearing house identiﬁes the short and long parties to each other. The third day is the  delivery day ; during this day the short future must deliver the bond to the clearing house. The long future pays the invoice amount based on the settlement price ﬁxed on the position day.

The short future has an option of when to exercise the  time to deliver  option from the penultimate business day prior to the start of the delivery month up to the last business day of the delivery month, known as the  last trading day . At 14:00 hours on that day the ﬁnal settlement price is determined, which stays constant to the end of the month. The short future is left with one more wild card at this point, known as the  end-of-the-month  option. Assuming that the short has not declared an intent to deliver until now, the settlement price for the contract is now irrevocably ﬁxed. At this point the short still has ﬁve more days before having to declare an intention. In this case the possibility still exists for proﬁt generation if, for example, the trader purchases the bond at the settlement price and holds it to delivery, earning the accrued interest. This will generate a carry proﬁt if the bond’s running yield is higher than its speciﬁc repo offer rate.

The last option advantage of the short future is the quality option. This is the option to deliver any of the bonds within the delivery basket. As we have seen the bonds can vary widely in coupon and maturity, and hence yield, and despite the conversion factor equal is ation there is a bias in this factor that means at yield levels above the notional coupon, long-dated bonds are the cheapest, and vice versa if yields are below the notional level. The quality option also presents the long future with potential problems if there is a change in yields sufﬁcient to change the CTD from one bond to another. If this comes as a surprise to the basis trader, it can be potentially very serious.
The delivery options available to the short future carry value, and this is reﬂected in the difference between the gross basis and the net basis. In theory the value of the delivery options, when added to the price of the futures contract, should equal the value of the bond together with the carry.

# 2.2 Bond delivery factors

# 2.2.1 The cheapest-to-deliver

The deliverable bond is of course the cheapest-to-deliver bond. This is not, as a junior trader once suggested to the author, the bond with the lowest market price (although it might well be). The CTD bond is the one that maximises the return to the arb it rage ur engaging in buying the basis, that is, buying the bond and simultaneously selling the future, holding the bond to expiry and then delivering it into the futures contract. Some market practitioners use the implied repo rate to identify the CTD, while others prefer the net basis method. We assess both now.

Essentially a good approximation for the CTD is to compare the basis for a bond with its total carry costs to delivery. The difference between the two is the net basis. However, this method may produce incorrect CTD rankings when the net basis values for two bonds are very close. When this happens the net basis for the bond that is actually the cheapest is higher than another bond in the basket, despite the fact that it is the cheapest. This happens because since the net basis method measures cheapness by comparing net basis to the dirty price of the bond, and this price is related to coupon size, maturity and given yield levels, the actual running cost is sometimes not captured. This can produce a lower net basis for a bond that is not actually the cheapest. For this reason the most accurate method by which to identify the CTD is to pick the bond with the highest implied repo rate. From the previous chapter we saw that the IRR is the hypothetical return achieved by going long the basis and running this position to expiry. It is in effect a repo agreement with the futures market, and the calculation fully accounts for the bond’s purchase price. The IRR method is recommended by academic writers because of the way that it is calculated; to reiterate from Chapter 1:

$$
\mathrm{IRR}=\left(\frac{P_{i n v o i c e}}{P_{b o n d}}-1\right)\times\left(\frac{M}{n}\right)
$$

where

P invoice is the invoice price;  $P_{b o n d}$  is the cash bond purchase price;  $M$  is the day base (365 or 360);  $n$  is the days to delivery.
From (2.4) we see that the bond currently trading at a price that results in the highest ratio of futures invoice price to the purchase price will have the highest implied repo rate. In other words, the bond with the lowest purchase price  relative to its invoice price  is the CTD bond.

Nevertheless net basis is still popular amongst traders because it identiﬁes the actual loss (when negative) from the basis trade, and as such is a more quantitative measure.

# 2.2.2 Selecting delivery time

Another advantage of the IRR measure is that it clearly indicates the time that the short future should deliver the bond. Consider Table 2.2 for the December 2000 long gilt contract.

This shows the implied repo rates for delivery on the ﬁrst day of the delivery month and the last day of the month. For all of the bonds the IRR for delivery on the last day is higher than that for delivery on the ﬁrst day. It is apparent that the (theoretical) return from a long basis trade would be higher if the delivery date was delayed to the last possible moment, and so in this case the short future would elect to deliver on the last business day.

In fact our illustration is a peculiar one, because the gilt yield curve was inverted at this time. In a positively-sloped yield curve environment, higher IRRs will result for longer-term trades and the decision of the short over when to deliver is an obvious one. The other reason why the short future would prefer to delay delivery is because early delivery eliminates the value of the option element that the short future possesses. It is a bit like early exercise of an American option eliminating the option’s time value. In a negative yield curve environment the decision is not so clear cut, although early delivery still removes the short’s option advantage. However the market repo rate would need to be considerably higher than the IRRs to justify early delivery, and this was not the case here. Where the market repo rate is higher, the short future will be running a carry cost each day the basis position is maintained, so this will suggest early delivery.

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c1ca46897fb4657fc05b3477268f2a3e635909f60dd6b550035df21bb2384e84.jpg)
Table 2.2:  Identifying the cheapest-to-deliver and the optimum delivery time, December 2000 long gilt basket. Source: LIFFE, JPMorgan Chase Bank
In theory there should only be two days when the short future delivers: the start or end of the delivery month; but changes in the yield curve, a particular bond yield level, and market repo rates may make it necessary to deliver on dates in between. Consider Table 2.3, which shows the delivery pattern for the September 1996 and December 1998 long gilt contract on LIFFE. In September 1996 the gilt yield curve was conventional and positively sloping, and apart from a small handful of deliveries just prior, all deliveries were made on the last eligible day of the month. In December 1998 however, the yield curve was negatively sloping, and this is reﬂected in the pattern of deliveries. It would appear that some market participants had confused ideas, and although in general bonds were delivered early in the month, some deliveries were still being made right in to the middle of the month. This despite the fact the delivery parties would be experiencing negative carry each day they did not deliver. Essentially, this would have been a cost to all those that did not deliver on the ﬁrst day.

For readers’ interest we list the delivery histories from March 1996 long gilt contract through to the June 2001 contract, in the Appendix to this book.

Table 2.3:  Bond delivery patterns for two gilt futures contracts, reﬂecting the shape of the yield curve at time of delivery
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/cac8e85ca206a6604b7225e85dd36feb51c9d8796e639d758c5213b1ff32ed09.jpg)
# 2.2.3 Changes in CTD status

A bond may be replaced as CTD if there are changes in relative yield levels of deliverable bonds, if the shape of the yield curve changes or if speciﬁc repo rates turn special for certain bonds and not others. Benninga (2001) amongst others has identiﬁed the following general rules:

j where the yield level is below the notional coupon level, the bond with the lowest duration will be the CTD. If the yield level is higher than the notional, the bond with the highest duration will be the CTD; j where bonds have roughly identical durations, the bond with the highest yield will be the CTD.

Bond yields are relative however, and the bonds in the basket will trade at different yield levels. A large  relative  shift can bring about a change in CTD status, while overall yields remain roughly at the same level. A more signiﬁcant yield shift or change in the shape of the curve can also have this effect. The yield on any particular bond is market-determined, and is a function of a number of factors, such as its liquidity, benchmark status, and so on. If there are two or more bonds in the delivery basket with approximately identical duration values, the bond with the higher yield would have the lower converted price, and therefore would be the CTD bond.

5   Remember that duration is an approximate measure of the percentage change in the price of a bond for a  $1\%$   change in the bond’s yield. For a given change in yield then, the prices of bonds of higher-duration will change by a greater amount than lower-duration bonds. This is worth bearing in mind because it is behind the bias in the conversion factor introduced in the previous section. Let’s reiterate this here. A contract’s conversion factors are the approximate prices at which deliverable bonds yield the notional yield level. For the Treasury long bond then, all conversion factors are approximately neutral at a yield level of  $6\%$  . If every bond in the delivery basket was trading at   $6\%$   yield, their converted prices (the price at this yield, divided by the relevant conversion factor) should be equal to 100, or close to 100. At this yield level then, the short future is in theory in different as to which bond to deliver. However, at yield levels above or below the notional level of  $6\%$  , duration of the deliverable bonds becomes relevant.

At yields below   $6\%$  , as yields fall the rise in price of a lower-duration bond is relatively lower than the price rise of a higher-duration bond. Thus, the lowduration bond becomes the CTD bond. As yields rise above   $6\%$  , the higherduration bond experiences a smaller fall in price than the lower-duration bond, and it becomes the CTD bond.
# Appendices

# Appendix 2.1: General rules of the CTD bond

Beninnga (1997) has suggested some general rules in a non-ﬂat yield curve environment that may be taken to be a general model for basis trading. His study analysed the character of the CTD bond under four different scenarios, as part of a test of the following circumstances. When the term structure is ﬂat, the CTD bond is the one with:

j the highest duration if the market interest rate is higher than the notional coupon; j the lowest duration if the market interest rate is lower than the notional coupon.

Benninga suggests that under certain scenarios, notably when:

j the market yield is higher than the notional coupon and there are no deliverable bonds with a coupon lower than the notional coupon, and when the market yield is higher than the notional coupon, and j there are no deliverable bonds with a coupon higher than the notional,

the duration rule does not always apply. The conclusions of his analysis are that:

j the CTD bond invariably has the highest coupon of the deliverable bonds, where the market yield is lower than the notional coupon, otherwise it has the lowest coupon of the deliverable bonds. The analysis assumes that the bonds possess positive convexity, but the results are not dependent on the shape of the yield curve; j when market rates are lower than the notional coupon, the maturity of the CTD is the shortest of all deliverable bonds; again, if the market rate lies above the notional coupon, the CTD bond will have the longest maturity if it also has a coupon greater than the notional coupon. If the coupon of the CTD bond is lower than the notional coupon, Benningna concludes that the CTD will have neither the longest or the shortest maturity in the delivery basket.

Certain anecdotal observation appears to conﬁrm these generalities.

# Appendix 2.2: A general model of the CTD bond

The price today (or at time 0) of a bond is generally given by (2.5):

$$
P=\int_{0}^{T}C e^{-r t}\,\mathrm{d}t+100e^{-r T}
$$

where    $C$   is the bond cash ﬂow and    $T$   is the bond maturity date.
The discount factor at time    $t$   for one unit of cash at time  $s\geq t$   when the time    $t$  spot interest-rate is  $r$   is given by  $e^{-r t}$  . The value of the conversion factor for a bond with maturity    $T$   and coupon    $C$   delivered at time    $F_{,}$   the expiry date of the futures contract, is given by (2.6):

$$
\begin{array}{l l}{C F=\int_{0}^{T-F}C e^{-c s}\,\mathrm{d}s+e^{-c(T-F)}}\\ {\quad=\displaystyle\frac{C e^{-c s}}{-c}\big\vert_{0}^{T-F}+e^{-c(T-F)}=\displaystyle\frac{C\big(1-e^{-c(T-F)}\big)}{-c}+e^{-c(T-F)}}\end{array}
$$

where    $c$   is the notional coupon of the futures contract.

# Selected bibliography and references

Arak, M., Goodman, L., Ross, S., ‘‘The Cheapest to Deliver Bond on the Treasury Bond Futures Contract’’,  Advances in Futures and Options Research 1 , 1986, pp. 49–74

Benninga, S.,  Financial Modeling , MIT, 1997, Chapter 18 Kolb, R.,  Understanding Futures Markets , Kolb Publishing 1994, Chapter 9 Meisner, J., La bus ze w ski, J., ‘‘Treasury Bond Futures Delivery Bias’’,  Journal of Futures Markets , Winter 1984, pp. 569–572

# Selected bibliography and references
Benninga, S., Weiner, Z., ‘‘An Investigation of Cheapest-to-Deliver on Treasury Bond Futures Contracts’’,  Journal of Computational Finance 2 , 1999, pp. 39–56 Boyle, P., ‘‘The Quality Option and the Timing Option in Futures Contracts’’, Journal of Finance 44 , 1989, pp. 101–113 Burghardt, G.,  et al ,  The Treasury Bond Basis , revised edition, Irwin 1994 Galitz, L.,  Financial Engineering , revised edition, FT Pitman, 1995, Chapter 8 Fabozzi, F.,  Treasury Securities and Derivatives , FJF Associates, 1998 Fabozzi, F.,  Bond Portfolio Management , 2nd edition, FJF Associates, 2001, Chapters 6, 17 Plona, C.,  The European Bond Basis , McGraw-Hill 1997 Rubinstein, M.,  Rubinstein on Derivatives , RISK Books, 1999 Jonas, S., ‘‘The change in the cheapest-to-deliver in Bond and Note Futures’’, in Dattatreya, R., (ed.),  Fixed Income Analytics , McGraw-Hill 1991 Van Deventer, D., Imai, K.,  Financial Risk Analytics: A Term Structure Model Approach for Banking, Insurance and Investment Management , Irwin 1997, page 11
