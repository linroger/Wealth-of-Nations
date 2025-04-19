---
tags:
  - arbitrage_trading
  - basis_trading
  - delivery_option
  - futures_contracts
  - implied_repo_rate
aliases:
  - Basis and Repo
  - Futures Basis
key_concepts:
  - arbitrage trading opportunities
  - basis and futures prices
  - cheapest-to-deliver bond
  - no-arbitrage futures price
  - short future delivery option
---

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
