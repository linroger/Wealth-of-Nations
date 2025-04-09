# 3.9 FUTURES: EUROCURRENCY CONTRACTS  

Forward loans do not trade in the OTC market because FRAs are much more cost-effective Eurocurrency futures are another attractive alternative. In this section, we discuss Eurocurrency futures using the Eurodollar (ED) futures as an example and then compare it with FRA contracts. This comparison illustrates some interesting aspects of successful contract design in finance.  

FRA contracts involve exchanges of interest payments associated with a floating and a fixed-. rate loan. The Eurodollar futures contracts trade future loans indirectly. The settlement will be in cash and the futures contract will again result only in an exchange of interest rate payments. However, there are some differences with the FRA contracts..  

Eurocurrency futures trade the forward loans (deposits) shown in Figure 3.10 as homogenized contracts. These contracts deal with loans and deposits in Euromarkets, as suggested by their name.. The buyer of the Eurodollar futures contract is a potential depositor of 3-month Eurodollars and. will lock in a future deposit rate.  

Eurocurrency futures contracts do not deliver the deposit itself. At expiration date $t_{1}$ the contract is cash settled. Suppose we denote the price of the futures contract quoted in the market by $Q_{t_{0}}$ . Then the buyer of a 3-month Eurodollar contract "promises" to deposit. $100(1-\tilde{F}_{t_{0}}\frac{1}{4})$ dollars at expiration date $t_{1}$ and receive 100 in 3 months. The implied annual interest rate on this loan is then calculated by the formula  

$$
\tilde{F}_{t_{0}}=\frac{100.00-Q_{t_{0}}}{100}
$$  

This means that the price quotations are related to forward rates through the formula  

$$
Q_{t_{0}}=100.00(1-\tilde{F}_{t_{0}})
$$  

However, there are important differences with forward loans. The interest rate convention used for forward loans is equivalent to a money market yield. For example, to calculate the time $t_{1}$ present value at time $t_{0}$ we let  

$$
P V(t_{0},t_{1},t_{2})=\frac{100}{(1+F_{t_{0}}\delta)}
$$  

Futures contracts, on the other hand, use a convention similar to discount rates to calculate the time $t_{1}$ value of the forward loan  

$$
\begin{array}{r}{\tilde{\mathbf{PV}}(t_{0},t_{1},t_{2})=100(1-\tilde{F}_{t_{0}}\delta)}\end{array}
$$  

If we want the amount traded to be the same:  

$$
\mathrm{PV}(t_{0},t_{1},t_{2})=\mathrm{P\tilde{V}}(t_{0},t_{1},t_{2})
$$  

the two forward rates on the right-hand side of formulas (3.58) and (3.59) cannot be identical. Of course, there are many other reasons for the right-hand side and left-hand side in formula (3.60) not to be the same. Futures markets have mark-to-market; FRA markets, in general, do not. With markto-market, gains and losses occur daily, and these daily cash flows may be correlated with the overnight funding rate. Thus, the forward rates obtained from FRA markets need to be adjusted to get the forward rate in the Eurodollar futures, and vice versa.  

# EXAMPLE  

Suppose at time $t_{0}$ , futures markets quote a price  

$$
Q_{t_{0}}=95.76
$$  

for a Eurodollar contract that expires on the third Wednesday of December 2020. This would mean two things. First, the implied forward rate for that period is given by:.  

$$
F_{t_{0}}=\frac{100.00-95.76}{100}=0.0424
$$  

Second, the contract involves a position on the delivery of  

$$
100\bigg(1-0.04240\frac{1}{4}\bigg)=98.94\
$$  

dollars on the third Wednesday of December 2020.  

At expiry, these funds will never be deposited explicitly. Instead, the contract will be. cash settled. For example, if on expiration the exchange has set the delivery settlement price at $Q_{t_{1}}=96.0$ , this would imply a forward rate  

$$
F_{t_{1}}={\frac{100-96.0}{100}}=0.04
$$  

and a settlement  

$$
100{\left(1-0.04{\frac{1}{4}}\right)}=99.00
$$  

Thus, the buyer of the original contract will be compensated as if he or she is making a deposit of 98.94 and receiving a loan of 99.00. The net gain is.  

$$
99.00-98.94=0.06\mathrm{per}100\mathrm{dollars}
$$  

This gain can be explained as follows. When the original position was taken, the (forward) rate for the future 3-month deposit was. $4.24\%$ . Then at settlement this rate declined to. $4.0\%$  

Actually, the above example is a simplification of reality as the gains would never be received as a lump sum at the expiry due to marking-to-market. The mark-to-market adjustments would lead to a gradual accumulation of this sum in the buyer's account. The gains will earn some interest as well. This creates another complication. Mark-to-market gains losses may be correlated with daily interest rate movements applied to these gains (losses).27  

# 3.9.1 OTHER PARAMETERS  

There are some other important parameters of futures contracts. Instead of discussing these in detail, we prefer to report contract descriptions directly. The following table describes this for the CME Eurodollar contract.28  

<html><body><table><tr><td>Deliverymonths</td><td>:March,June,September,December (for10years)</td></tr><tr><td>Delivery (Expiry) day</td><td>:ThirdWednesdayof deliverymonth</td></tr><tr><td>Last trading day</td><td>:11.ooTwobusinessdaysbeforeexpiration</td></tr><tr><td>Minimumtick</td><td>:0.0025 (for spot-month contract)</td></tr><tr><td>"Tickvalue”</td><td>：USD6.25fornearestmonth,otherwiseUSD12.50</td></tr><tr><td>Settlementrule</td><td>:ICELIBORonthesettlementdate</td></tr></table></body></html>  

The design and the conventions adopted in the Eurodollar contract may seem a bit odd to the reader, but the contract is a successful one. First of all, quoting. $Q_{t_{0}}$ instead of the forward rate $\tilde{F}_{t_{0}}$ makes the contract similar to buying and selling a futures contract on T-bills. This simplifies related hedging and arbitrage strategies. Second, as mentioned earlier, the contract is settled in. cash. This way, the functions of securing a loan and locking in an interest rate are successfully. separated.  

Third, the convention of using a linear formula to represent the relationship between $Q_{t_{0}}$ and $\tilde{F}_{t_{0}}$ is also a point to note. Suppose the underlying time $t_{1}$ deposit is defined by the following equation  

$$
D(t_{0},t_{1},t_{2})=100(1-\tilde{F}_{t_{0}}\delta)
$$  

A small variation of the forward rate $\tilde{F}_{t_{0}}$ will result in a constant variation in $\boldsymbol{D}\left(t_{0},t_{1},t_{2}\right)$  

$$
\frac{\partial D(t_{0},t_{1},t_{2})}{\partial\tilde{F}_{t_{0}}}=-\delta100=-25
$$  

Thus, the sensitivity of the position with respect to the underlying interest rate risk is constant, and the product is truly linear with respect to $\tilde{F}_{t_{0}}^{\parallel}$  

# 3.9.1.1 The "TED spread"  

The difference between the interest rates on 3-month Treasury Bills (T-Bills) and 3-month Eurodollar (ED) futures is called the TED spread.29 T-bill (T-Note) rates provide a measure of the US government's short-term (medium-term) borrowing costs. Eurodollar futures relate to shortterm private sector borrowing costs while T-bills are considered risk free (for a country like the United States, but not all countries as the GFC has demonstrated). Thus the "TED spread" has credit risk elements in it.30  

The TED spread average from 1986 to 2014 is around 62 bps.31 On October 10, 2008, the TED spread reached 458 bps as liquidity in the interbank lending market dried up and lenders' perception of the default on interbank loans (counterparty risk) spiked. This reading eclipsed the level of 278 bps reached on October 28, 1987. Figure 3.17 plots the TED spread against the 3-month USD LIBOR and T-BILL rates from January 2, 1986 until April 17, 2014.  

![](ad2b3170e12a25c5461f9733b4a6656e0ac8a8eac7b674f6c888083f30acac8b.jpg)  

# FIGURE 3.17  

TED spread versus 3-month USD LIBOR and T-Bill.  

Traders form strips of Eurodollar futures and trade them against T-Bills of similar maturity. A similar spread can be put together using Treasury Notes (T-notes) and Eurodollars as well. Given the different ways of quoting yields, calculation of the spread involves some technical adjustments. T-Notes use bond equivalent yields whereas Eurodollars are quoted similar to discount rate basis. The calculation of the TED spread requires putting together strips of futures while adjusting for these differences. There are several technical points that arise along the way.  

Once the TED spread is calculated, traders put on trades to benefit from changes in the yield curve slope and in private sector credit risk. For example, traders would long the TED spread if they expected the yield spread to widen. In the opposite case, they would short the TED spread and would. thus benefit from the narrowing of the yield spread. Experienced fixed income relative value traders are wary of being short the TED spread, however, due to the occasionally extreme downside..  

# 3.9.2 COMPARING FRAs AND EURODOLLAR FUTURES  

A brief comparison of FRAs with Eurocurrency futures may be useful. (i) Being OTC contracts, FRAs are more flexible instruments, since Eurodollar futures trade in terms of preset homogeneous contracts. (ii) FRAs have the advantage of confidentiality. There is no requirement that the FRA terms be announced. The terms of a Eurocurrency contract are known. (ii) As discussed in Chapter 2, until recently there were no margin requirements for FRAs and the mark-to-market requirements are less strict. With FRAs, money changes hands only at the settlement date.. Eurocurrency futures come with margin requirements as well as with mark-to-market requirements. (iv) FRAs have counterparty risk, whereas the credit risk of Eurocurrency futures contracts is insignificant. (v) FRAs are quoted on an interest rate basis while Eurodollar futures are quoted on a price basis. Thus a trader who sells an FRA will hedge this position by selling a Eurodollar contract as well. (vi) Finally, an interesting difference occurs with respect to fungibility. Eurocurrency contracts are fungible, in the sense that contracts with the same expiration can be netted against each other even if they are entered into at different times and for different purposes. FRA contracts cannot be netted against each other even with respect to the same counterparty, unless the two sides have a specific agreement.  

# 3.9.2.1 Convexity differences  

Besides these structural differences, FRAs and Eurocurrency futures have different convexities. The pricing equation for Eurocurrency futures is linear in $\tilde{F}_{t_{0}}$ , whereas the market-traded FRAs have a pricing equation that is nonlinear in the corresponding LIBOR rate. We will see that this requires convexity adjustments, which is one reason why we used different symbols to denote the two forward rates.  

# 3.9.3 HEDGING FRAs WITH EUROCURRENCY FUTURES  

For short-dated contracts, convexity and other differences may be negligible, and we may ask the following question. Putting convexity differences aside, can we hedge an FRA position with futures, and vice versa?  

It is best to answer this question using an example. The example also illustrates some realworld complications associated with this hedge.  

# EXAMPLE  

Suppose we are given the following Eurodollar futures prices on June 17, 2002:  

September price (delivery date: September 16) 96.500 (implied rate $=3.500,$ December price (delivery date: December 16) 96.250 (implied rate $=3.750),$ March price (delivery date: March 17) 96.000 (implied rate $=4.000$  

A trader would like to sell a $(3\times6)$ FRA on June 17, with a notional amount of USD100,o00,000. How can the deal be hedged using these futures contracts?  

Note first that according to the value and settlement date conventions, the FRA will run for the period September 19-December 19 and will encompass 92 days. It will settle against the LIBOR fixed on September 17. The September futures contract, on the other hand, will settle against the LIBOR fixed on September 16 and is quoted on a 30/360 basis. Thus, the implied forward rates will not be identical for this reason as well.  

Let $f$ be the FRA rate and $\in$ be the differences between this rate and the forward rate implied by the futures contract. Using formula (3.41), the FRA settlement, with notional value of 100 million USD, may be written as  

$$
\frac{100m((0.035+\in)-\mathrm{Libor})_{360}^{92}}{\left(1+\mathrm{Libor}\frac{92}{360}\right)}
$$  

Note that this settlement is discounted to September 19 and will be received once the relevant LIBOR rate becomes known. Ignoring mark-to-market and other effects, a futures contract covering similar periods will settle at.  

$$
\alpha\biggl(1~m(0.0350-\mathrm{Libor}){\frac{90}{360}}\biggr)
$$  

Note at least two differences. First, the contract has a nominal value of UsD1 million. Second, 1 month is, by convention, taken as 30 days, while in the case of FRA it was the actual number of days. The $\alpha$ is the number of contracts that has to be chosen so that the. FRA position is correctly hedged.  

The trader has to choose $\alpha$ such that the two settlement amounts are as close as possible. This way, by taking opposite positions in these contracts, the trader will hedge his or her risks.  

# 3.9.3.1 Some technical points  

The process of hedging is an approximation that may face several technical and practical difficulties. To illustrate them we look at the preceding example once again.  

1. Suppose we tried to hedge (or price) a strip of FRAs rather than having a single FRA be. adjusted to contract using a strip of available futures contracts. Then the strip of FRAs will have to deal with increasing notional amounts. Given that futures contracts have fixed notional. amounts, contract numbers need to be adjusted instead.  

2. As indicated, a 3-month period in futures markets is 90 days, whereas FRA contracts count the actual number of days in the corresponding 3-month period.   
3. Given the convexity differences in the pricing formulas, the forward rates implied by the two. contracts are not the same and, depending on LIBOR volatility, the difference may be large or small.   
4. There may be differences of 1 or 2 days in the fixing of the LIBOR rates in the two contracts.  

These technical differences relate to this particular example, but they are indicative of mos hedging and pricing activity.  

# 3.1O REAL-WORLD COMPLICATIONS  

Up to this point, the discussion ignored some real-life complications. We made the following simplifications. (i) We ignored bid-ask spreads. (ii) Credit risk was assumed away. (iii) We ignored the fact that the fixing date in an FRA is, in general, different from the settlement date. In fact, this is another date involved in the FRA contract. Let us now discuss these issues.  

# 3.10.1 BID-ASK SPREADS  

We begin with bid-ask spreads. The issue will be illustrated using a bond market construction. When we replicate a forward loan via the bond market, we buy a $B(t_{0},t_{1})$ bond and short-sell a $B$ $(t_{0},t_{2})$ bond. Thus, we have to use ask prices for $B(t_{0},t_{1})$ and bid prices for $B(t_{0},t_{2})$ . This means that the asking price for a forward interest rate will be  

$$
1+F_{\mathrm{t_{0}}}^{\mathrm{ask}}\delta=\frac{B(t_{0},t_{1})^{\mathrm{ask}}}{B(t_{0},t_{2})^{\mathrm{bid}}}
$$  

Similarly, when the client sells an FRA, he or she has to use the bid price of the dealers and brokers. Again, going through the bond markets we can get  

$$
1+F_{\mathrm{t_{0}}}^{\mathrm{bid}}\delta=\frac{B(t_{0},t_{1})^{\mathrm{bid}}}{B(t_{0},t_{2})^{\mathrm{ask}}}
$$  

This means that  

$$
F_{\mathrm{t_{0}}}^{\mathrm{bid}}<F_{t_{0}}^{\mathrm{ask}}
$$  

The same bid-ask spread can also be created from the money market synthetic using the bid-ask spreads in the money markets.  

$$
1+F_{\mathrm{t_{0}}}^{\mathrm{ask}}\delta=\frac{1+L_{t_{0}}^{1\mathrm{bid}}\delta^{1}}{1+L_{t_{0}}^{2\mathrm{ask}}\delta^{2}}
$$  

Clearly, we again have  

$$
F_{t_{0}}^{\mathrm{bid}}<F_{t_{0}}^{\mathrm{ask}}
$$  

Thus, pricing will normally yield two-way prices.  

In market practice, FRA bid-ask spreads are not obtained in the manner shown here. The bid-. ask quotes on the FRA rate are calculated by first obtaining a rate from the corresponding LIBORs and then adding a spread to both sides of it. Many practitioners also use the more liquid. Eurocurrency futures to "make"' markets.  

# 3.10.2 AN ASYMMETRY  

There is another aspect to using FRAs for hedging purposes. The net return and net cost from an interest rate position will be asymmetric since, whether you buy (pay fixed) or sell (receive fixed), an FRA always settles against LIBOR. But LIBOR is an offer (asking) rate, and this introduces an asymmetry.  

We begin with a hedging of floating borrowing costs. When a company hedges a floating borrowing cost, both interest rates from the cash and the hedge will be LIBOR based. This means that:  

The company pays LIBOR $^+$ margin to the bank that it borrows funds from. The company pays the fixed FRA rate to the FRA counterparty for hedging this floating cost against which the company receives LIBOR from the FRA counterparty.  

Adding all receipts and payments, the net borrowing cost becomes FRA ra $t e+m$ argin. Now consider what happens when a company hedges, say, a 3-month floating receipt. The releant rate for the cash position is Libid, the bid rate for placing funds with the Euromarkets.  

But an FRA always settles always against LIBOR. So the picture will change to:  

Company receives Libid, assuming a zero margin.   
Company receives FRA rate.   
Company pays LIBOR.   
Thus, the net return to the company will become FRA-(LIBOR-Libid).  
