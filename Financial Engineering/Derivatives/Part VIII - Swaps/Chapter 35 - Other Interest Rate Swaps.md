---
tags:
  - basis_swaps
  - interest_rate_swaps
  - swap_hedging
  - variable_rate_swaps
  - zero_coupon_swaps
aliases:
  - floating-floating swap
  - non-standard swaps
  - spread-to-LIBOR swap
  - yield curve swap
key_concepts:
  - floating rate interest payments
  - hedge credit risk
  - price non-standard swaps
  - swap dealers hedge
  - value interest rate swaps
---
# Other Interest Rate Swaps  

# Aims  

• To price and value ‘non-standard’ interest rate swaps such as variable rate swaps, of-market swaps, zero-coupon swaps, swaps with variable notional principals and basis swaps.   
• The swap rate on more complex interest rate swaps can be determined by making the present value of the fxed leg of the swap equal to the (expected) present value of the foating leg (at inception of the swap) – as for plain vanilla swaps. However, the methods used in calculating these present values difer for exotic swaps.   
• To show how swap dealers hedge their interest rate swaps book using other fxed income assets such as FRAs, bonds, interest rate futures, and interest rate options.   
• To demonstrate how to hedge the credit risk of a swap position using collateral, netting and credit enhancements.  

# 35.1 SWAP DEALS  

There are a wide variety of swap contracts which can be designed to suit particular customers’ requirements. In a spread-to-LIBOR swap, the foating rate is not at LIBOR-fat but at LIBOR plus a spread. Since most foating-rate bank loans contain a spread over LIBOR, this swap can be constructed to exactly match the foating payments in a LIBOR bank loan. In an of-market swap, the fxed swap rate is set at whatever rate is chosen by the ‘customer’ (e.g. a corporate) – for example, this of-market swap rate might be chosen to exactly match the fxed rate on an existing bank loan. In a zero-coupon swap the fxed payment is not periodic but consists of one ‘lump sum’ payment at the maturity of the swap.  

Some corporates may have fxed interest rate loans where the fxed payments change over time in a predetermined way – for example, the fxed rate might be $3\%$ p.a. for the frst 10 years followed by a fxed rate of $4\%$ p.a. for a further 5 years. To match the payments in such a loan the corporate might use a swap to ‘receive fxed’ but the swap has a pre-agreed changing path for the (fxed) swap rate which matches that on the bank loan. Also, the corporate might pay foating (LIBOR-fat) in the swap, thus efectively converting her fxed rate loan (with diferent fxed rates over diferent time periods) to a variable rate loan.  

In a basis swap both parties make foating-rate interest payments but they are linked to diferent foating rates, for example 90-day LIBOR against 180-day LIBOR or against the 90-day T-bill rate. This type of swap is also referred to as a foating-foating swap. It allows a corporate to exchange one set of foating-rate payments for a slightly diferent set of foating payments. Although LIBOR and T-bill rates (for the same maturities) tend to move together, the spread can change – which gives rise to net payments in the swap.  

Another kind of basis swap is a yield curve swap. Here both parties pay foating but one might be based on a short rate (e.g. 3-month T-bill rate) and the other on the 20-year T-bond yield. If the yield curve is initially upward sloping but during the life of the swap it fattens out then this would beneft the party paying the 20-year rate and receiving the short rate.  

A yield curve swap might be useful for a Savings and Loan Association (S&L) (or bank) to ofset interest rate risk. An S&L has (mostly) short-term foating rate liabilities (e.g. deposits) and (some) foating rate long-term assets (e.g. variable rate mortgage receipts). The S&L will sufer if short rates rise relative to long rates (i.e. if the yield curve fattens) but it can ofset this risk by entering into a yield curve swap, to receive cash fows based on a short rate and pay out cash fows based on a long rate.  

Swaps may have variable notional principals. If the notional principal falls over the life of the swap this is an amortising swap. For example, if someone has foating loan payments linked to a mortgage where the principal on the ‘mortgage’ falls through time, then an amortising swap is appropriate. The converse, where the principal increases through time is known as an accreting swap. This is useful where, for example, a construction frm has building costs which increase by, say, $\$100$ each year for 5 years and it has taken out a ‘staggered LIBOR-loan’ for $\$100$ today, followed by an extra $\$100$ principal in each succeeding year, over the construction period. The construction frm can convert this ‘increasing principal’ foating-rate loan into an ‘increasing principal’ fxed rate loan by entering into an accreting swap to ‘receive-foating, pay-fxed’, on a (notional) variable principal amount.  

It is also possible to create a swap with a variable notional principal that frst increases and then decreases over the life of the swap, to match the changing principal in a bank loan held by a corporate – this is known as a roller-coaster swap. A roller-coaster swap can be useful in hedging foating rate payments on a bank loan for project fnance (e.g. for building an electricity generating station where the principal of the bank loan frst increases (to pay the construction costs) and then decreases (after cash fows from the project come on stream).  

Dif swaps or quanto swaps are cross-currency interest rate swaps. One party to the swap has cash fows determined by a foreign interest rate but these foreign cash fows are based on a notional principal in the home currency. They embed a fxed currency exchange rate in the swap deal.  

For example, a US frm might enter a swap where it receives periodic cash fows based on (fxed) Euribor swap rates but calculated on a dollar principal amount. In the swap the US frm might pay USD-LIBOR (on the same dollar principal amount). The US frm therefore avoids any currency risk. The term ‘dif swap’ arises from the fact that payments in the swap depend on the diference between interest rates in two countries. The receipt of Euribor interest in the swap could be used to pay interest on an existing Euribor bank loan. The US frm then efectively has a fxed USD loan (and no exchange rate risk).  

If you wish to enter into a swap at some time in the future at a swap rate fxed today, then a forward swap is appropriate. This is simply a forward contract on the swap rate. Now consider an option on a swap, which is known as a swaption. The swaption ‘delivers’ a (cash-market) swap at the expiration date of the option. If you choose to receive the fxed payment in the swap (and pay foating) it is called a receiver swaption. (The converse is a payer swaption.) Forward swaps and swaptions are discussed in Chapter 39.  

We use the methods outlined in the previous chapter to value a variety of ‘non-standard interest rate swaps, these include:  

• a swap with a variable notional principal   
• a spread-to-LIBOR swap   
• an of-market swap   
• a zero-coupon swap   
• a swap with a variable swap rate (for the ‘fxed’ payments).  

# 35.2 PRICING NON-STANDARD SWAPS  

# 35.2.1 Variable Notional Principal  

Assume the day-count convention for the foating leg is $m_{i}=a c t u a l d a y s_{i}/360$ and for the fxed leg it is $h_{i}=180/360$ . (We keep the subscript on $h_{i}$ because in some swaps $h_{i}=a c t u a l d a y s_{i}/(360o r365))$ . In amortising, accreting and roller-coaster swaps the notional principal $Q_{i}$ varies in a pre-specifed manner, determined at the outset of the swap. We can price this swap in the same way as we priced a plain vanilla interest rate swap, the only changes being:  

• We replace $Q$ with $Q_{i}$ , hence $C_{F L,i}=f_{i}m_{i}Q_{i}$ and $C_{X,i}=s p.h_{i}Q_{i}$ .   
• We have to value the foating leg using all the forward rates – we cannot use the ‘short method’ as we have a variable notional principal $Q_{i}$ .  

At inception of the swap the value of the foating and fxed legs are:  

$$
\begin{array}{l}{{\displaystyle V_{F L}=\sum_{i=1}^{n}C_{F L,i}d_{i}+Q_{n}d_{n}}}\\ {{\displaystyle V_{F i x}=\sum_{i=1}^{n}C_{X,i}d_{i}+Q_{n}d_{n}}}\end{array}
$$  

Hence equating the two present values and solving for the swap rate, $s p$ :  

$$
s p={\frac{\displaystyle\sum_{i=1}^{n}(f_{i}m_{i}Q_{i})d_{i}}{\displaystyle\sum_{i=1}^{n}Q_{i}h_{i}d_{i}}}
$$  

Not surprisingly, the swap rate is determined by the predetermined values of the (changing) notional principal $Q_{i}$ as well as the term structure of interest rates, refected in $d_{i}$ and $f_{i}$ . Note that a plain vanilla swap has $Q_{i}=Q$ (fxed) and then (35.3) gives the swap rate for a plain vanilla swap, as derived in Chapter 34.  

# 35.2.2 Spread-to-LIBOR Swap  

Instead of LIBOR-fat in the foating leg, the swap contract may specify that the foating leg has an interest rate of $(\mathrm{LIBOR}+b)$ , where $b$ is a spread of say 30 bps $\begin{array}{r}{{\cal b}=0.003}\end{array}$ . We assume the notional value in the swap is fxed at $Q$ . The value of the fxed leg is:  

$$
V_{F i x}(t_{0})=\sum_{i=1}^{n}C_{X,i}d_{i}+Q_{n}d_{n}=(s p^{*}Q)\sum_{i=1}^{n}h_{i}d_{i}+Q d_{n}
$$  

The foating leg can be viewed as foating payments at LIBOR-fat with a PV of $Q$ at inception, plus periodic constant payments at $b Q$ , hence:  

$$
V_{F L}(t_{0})=Q+b Q\sum_{i=1}^{n}m_{i}d_{i}
$$  

where we have assumed that the spread $b$ uses the same day-count convention as the foating payments. Equating (35.4) and (35.5), the swap rate $s p^{*}$ , which gives zero value for the ‘spread-to-LIBOR’ swap at inception, is:  

$$
s p_{n}^{*}={\frac{(1-d_{n})}{\displaystyle\sum_{i=1}^{n}h_{i}d_{i}}}+{\frac{b\displaystyle\sum_{i=1}^{n}m_{i}d_{i}}{\displaystyle\sum_{i=1}^{n}h_{i}d_{i}}}=s p_{n}+{\frac{b\displaystyle\sum_{i=1}^{n}m_{i}d_{i}}{\displaystyle\sum_{i=1}^{n}h_{i}d_{i}}}
$$  

$s p_{n}$ is the ‘at-market’ swap rate (at $t_{0.}^{\cdot\cdot}$ ) for a fxed-for-foating swap at LIBOR-fat. If you are paying fxed using the ‘at-market’ swap rate $s p_{n}$ but receiving LIBOR-fat, the value of the swap to you is zero (by construction). But if you are paying fxed at $s p_{n}$ and receiving $\mathrm{LIBOR}{+b}$ the value of this swap to you will be positive. Hence to make the value of this ‘pay-fxed, receive- $.L I B O R+b^{,}$ swap equal to zero, the fxed swap rate $s p_{n}^{*}$ you pay in this ‘spread-to-LIBOR’ swap, is greater than the ‘at-market’ swap rate $s p_{n}$ .  

# 35.2.3 Zero-coupon Swap (Against LIBOR-flat)  

In a zero-coupon swap there is a single fxed payment of $Q_{n}^{*}$ at $t_{n}$ which has present value $V_{F i x}=d_{n}Q_{n}^{*}$ . We have to determine the value for $Q_{n}^{*}$ , which makes the swap have zero value at inception of the swap.  

The foating payments are the same as in a plain vanilla swap $C_{F L,i}=f_{i}m_{i}Q$ , where the (notional) principal in the swap is Q. We know that the value of all these foating payments at $t_{0}$ is simply $V_{F L}=Q=\mathfrak{S}100\mathrm{m}$ (say). Suppose $d_{n}=0.85$ (where $d_{n}=1/[1+r_{n}(d a y s_{n}/360)])$ . Equating $V_{F i x}=V_{F L}$ we have $Q_{n}^{*}=Q/d_{n}=\S100\mathrm{m}/0.85=\S117.647\mathrm{m}$ . The zero-coupon swap rate (per $\$1$ nominal principal) is then quoted as $s p_{n}^{z e r o}=17.647\%$ .  

In other words, on a notional principal of $\$1000$ the fxed leg of the swap has to pay out a single payment of $\$123,456$ at $t_{n}$ while the foating leg receives LIBOR on each payment date. The zero-coupon swap rate is (defned as):  

$$
s p_{n}^{z e r o}=(Q^{*}/Q)-1=0.17647.
$$  

It is easy to see that $s p_{n}^{z e r o}=(1/d_{n})-1=r_{n}~d a y s_{n}/360.$ Hence, the zero-coupon swap rate is the $n$ -period LIBOR rate $r_{n}$ (p.a.) adjusted by the maturity of the swap $(=d a y s_{n}/360)$ .  

In pricing our next set of swaps, so that the swap has the same value to both parties at inception, involves an up-front payment by one of the parties in the swap.  

# 35.2.4 Off-market Swap (Against LIBOR-flat)  

Suppose the current ‘at market’ swap rate (for an $n$ -year swap) with $Q=\$1000$ is $s p=6.2\%$ , which implies that using $s p=6.2\%$ , $V_{F i x}=V_{F L}=\mathbb{\mathbb{S}}100\mathrm{m}$ , so the swap has zero value (to both parties). How do you price a swap where the fxed-rate payer wants to pay fxed at $s p^{*}=6\%$ (every period)? This is an ‘of-market’ swap. The present value of the fxed leg at $s p^{*}=6\%$ is:  

$$
V_{F i x}(a t s p^{*}=6.0\%)=Q\left[\sum_{i=1}^{n}(s p^{*}h_{i})d_{i}+d_{n}\right]
$$  

which must be less than $V_{F i x}(a t s p=6.2\%)=\S100\mathrm{m}$ . Suppose $V_{F i x}(a t s p^{*}=6\%)=\mathfrak{H}99.5\mathrm{m}$ . Then the pay-fxed party in the of-market swap will deliver an up-front payment of $\$1000$ $\$99.5m=\$90.5m$ to the swap counterparty. The ‘pay-fxed’ party in all future periods then pays fxed at $s p^{*}=6\%$ and receives LIBOR-fat.  

# 35.2.5 Swap with Changing Fixed Rates (Against LIBOR-flat)  

It is a bit strange to think of the ‘fxed rate’ in a swap not being the same fxed rate every period. But at $t=0$ someone might like to pay a known amount each period but this predetermined amount can be diferent in each period.  

Suppose the current ‘at market’ swap rate (for an $n$ -year swap) with $Q=\$1000$ and with constant payments in the fxed leg is $s p=6.2\%$ . The fxed payments are $C_{X,i}=h_{i}s p Q$ and $V_{F i x}(s p=6.2\%)=V_{F L}=\S100\mathrm{m}-\mathrm{so}$ the swap has zero value to both parties.  

The known ‘fxed payments’ in the swap with a known changing value for ${\boldsymbol{s}}{p}_{i}^{*}$ are $C_{X,i}^{*}=$ $h_{i}s p_{i}^{*}Q$ where each diferent $s p_{i}^{*}$ at each future reset date are all known at $t=0$ . The valu,e of the fxed leg is:  

$$
V_{F i x}(w i t h s p_{i}^{*})=\sum_{i=1}^{n}C_{X,i}^{*}d_{i}+Q d_{n}
$$  

The numerical value of $V_{F i x}(w i t h\ s p_{i}^{*})$ is unlikely to equal $\$1000$ and could be larger or smaller depending on the particular values chosen (at $t=0\mathrm{\dot{\Omega}}$ ) for $\boldsymbol{s p}_{i}^{*}$ . Suppose $V_{F i x}(w i t h\ s p_{i}^{*})=$ $\$99.45$ . The ‘pay-fxed at $s{p}_{i}^{*}$ would pay an up-front payment of $\$1000$ at $t=0$ to the counterparty in the swap, then in all future periods would pay the (variable but) predetermined payments $C_{X,i}^{*}=h_{i}s p_{i}^{*}Q$ (and receive LIBOR each period).  

# 35.2.6 Basis Swap  

Consider an 18-month basis swap, with resets every 180 days, where you agree to pay the (variable) T-bill rate and receive LIBOR on a notional principal of $Q=\$1000$ . This can be replicated with two plain vanilla swaps:  

Pay T-bill rate and receive-fxed $+$ pay-fxed and receive-LIBOR  

Suppose the current term structure is:  

<html><body><table><tr><td>Maturity</td><td>T-bills</td><td>LIBOR</td></tr><tr><td>t = 180/360</td><td>rTB</td><td>#</td></tr><tr><td>t = 360/360</td><td></td><td>##</td></tr><tr><td>t = 540/360</td><td>TB</td><td>学</td></tr></table></body></html>  

Pricing the two plain vanilla swaps so that they have zero value at inception gives:  

(a) Pay variable T-bill rate and receive-fxed at $s p^{T B}$ :  

$$
s p^{T B}=2\frac{1-d_{3}^{T B}}{\sum_{i=1}^{3}d_{i}^{T B}}
$$  

where1 $d_{i}^{T B}=1/(1+r_{i}^{T B}t_{i})$  

(b) Pay fxed at $s p^{L}$ and receive LIBOR  

$$
s p^{L}=2\frac{1-d_{3}^{L}}{\sum_{i=1}^{3}d_{i}^{L}}\mathrm{\quad\where\:~}d_{i}^{L}=1/(1+r_{i}^{L}t_{i})
$$  

The term structure of LIBOR rates is usually slightly above that for T-bills (e.g. by 20–30 bps) because the former carries more credit risk, hence we might fnd that $s p^{T B}=6\%$ p.a. and $s p^{L}=5.6\%$ p.a. Now it is clear that the original basis swap of ‘pay the T-bill rate and receive-LIBOR’ would be priced so that one party would:  

Pay the T-bill rate and receive $(L I B O R-0.4\%)$ .  

# 35.2.7 Mark-to-market Value of Non-standard Swaps  

After inception, all of the above swaps will generally have a positive or negative value to one of the parties in the swap. The mark-to-market value of these swaps can be calculated using the ‘forward rate method’. All we need to do at time $t>0$ is note the new spot rates (and hence discount rates) and calculate the new forward rates. The forward rates are used to determine the new foating rate payments $C_{F L,i}^{*}=f_{i}^{*}m_{i}^{*}Q_{i}$ remaining in the swap and these are discounted using the new spot rates at $t$ , t퐹o퐿,give:  

$$
V_{F L}(t)=\left[\sum_{i=t+1}^{n}C_{F L,i}^{*}d_{i}^{*}+Q_{i}~d_{n}^{*}\right]
$$  

where the sum is from the next payment date $t+1$ to $n$ . The value of the (remaining) fxed payments at the new spot rates is straightforward:  

$$
V_{F i x}(t)=\sum_{i=t+1}^{n}C_{X,i}d_{i}^{*}+Q_{i}d_{n}^{*}
$$  

where ${\cal C}_{X,i}=h_{i}s p.Q.$ The current market value of a receive-foating, pay-fxed swap at any time after inception $(t>0)$ is:  

$$
V_{s w a p}(t)=V_{F L}(t)-V_{F i x}(t)
$$  

# 35.3 HEDGING INTEREST RATE SWAPS  

A swap dealer will usually take on one side of a plain vanilla interest rate swap even if she cannot immediately fnd an ofsetting swap. This is known as ‘warehousing’. If the dealer does warehouse an interest rate swap then she is exposed to interest rate risk. One way of hedging the foating interest payments is with a series of interest rate futures contracts. Eurodollar futures can be used and a series of Eurodollar futures is known as a Eurodollar strip.  

# 35.3.1 Hedging Floating LIBOR Cash Flows Only  

After aggregating all her interest rate swap deals, assume a swap dealer (Ms Float) currently has a net position to receive-foat, pay-fxed, (in USD) which currently has positive value to the dealer. How can the swap dealer hedge against future changes in interest rates?  

At frst sight it may look as if she just has to hedge changes in LIBOR on the foating side since the fxed (coupon) payments are just that, fxed. Ms Float can hedge any single future LIBOR swap receipt by today, going long (buying) Eurodollar futures with a maturity date just after the LIBOR reset date. If interest rates fall in the future, Ms Float receives lower foating-rate cash fows from her swaps but the futures price will rise and the proft from closing out the futures ofsets her lower LIBOR swap receipts. So today, for each LIBOR reset date in the swap Ms Float goes long $N_{F}$ futures:  

$$
N_{F}=\frac{N o t i o n a l~V a l u e~o f s w a p~(\S Q)}{N o t i o n a l~p r i n c i p a l~i n~f u t u r e s~c o n t r a c t}~\left[\frac{D(s w a p)}{D(f u t u r e s)}\right]~\beta_{y}~
$$  

where $D(s w a p)=1/2$ . (say), the tenor of cash fows in the swap. If there are $k$ remaining reset dates, she goes long a total of $k.N_{F}$ futures contracts today, using $N_{F}$ contracts for each reset date – this is a strip hedge. Ms Float will then close out $N_{F}$ contracts at each future reset date. However, this is not the hedge usually undertaken by swaps dealers, who invariably hedge the present value of the swap.  

The above is fne if you just want to hedge the future foating cash fows – so, for example, the above futures hedge is correct for a company hedging cash fows from a foating rate bank loan or bank deposit. But if the swap dealer just hedges her LIBOR foating leg of the swap she is ignoring the fxed leg. Remember that although the fxed (coupon) payments in the swap are ‘fxed’ each period, their present value is not – and above we have not yet hedged the change in the present value of the fxed payments in the swap.  

# 35.3.2 Hedging the Mark-to-market Value  

The market value of the swap changes due to (a) interest rates changes and (b) the swap has fewer payment dates remaining. We now discuss a diferent type of hedge where the swap dealer chooses to hedge the present value of the swap – that is, the present value of the foating receipts minus the fxed payments. If the swap dealer hedges the mark-to-market (present) value of the swap then any changes in interest rates (over a short time horizon) will not alter the present value of the swap dealer’s position. Because the hedge is only efective over a short time horizon, the hedge position must be periodically rebalanced.  

Hedging the PV of the swap is a conceptually diferent approach to hedging only the future LIBOR cash fows in the swap. The choice between these two types of hedge depends on what you consider is the most useful hedge in the circumstances. For example, it is reasonable for a company with a foating rate loan just to hedge the upcoming foating rate payments using a strip of interest rate futures contracts – since these variable loan payments are the key cash-fow risk for the corporate. But it seems more sensible for the swap dealer to hedge changes in value for both legs of the swap. If the swap currently has a value of $\$1000$ to the swap dealer, then with the hedge in place the swap dealer’s position will still have $\$1000$ value, after a change in interest rates (over a short time horizon). Also for regulatory purposes it is the mark-to-market value that is used in determining how much ‘capital’ (e.g. retained profts and equity capital) the swap dealer has to hold against the ‘market risk’ of her swap’s book.  

Suppose you are holding a receive-foat, pay-fxed swap that currently has positive value. If over the next few days all interest rates (including forward rates) fall by 1 bp (parallel shift), the mark-to-market value of your swap position will fall. It is perhaps easiest at the outset to analyse what is going on by assuming that the PV of the foating payments remains unchanged. (Remember, as interest rates change, the PV of the foating payments stays close to $\$2$ .) As a fxed-rate payer in the swap, you are worse of after a fall in interest rates because the PV of your future fxed (coupon) payments increases – your liabilities have increased. Hence a fall in interest rates by 1 bp will result in a fall in the value of a receive-foat, pay-fxed swap.  

# 35.3.3 Delta of a Swap  

The delta of a swap (by convention) is defned as the dollar change in present value of the swap for a 1 bp increase in all interest rates (i.e. an upward parallel shift in the yield curve).  

The present value at time $t$ of the net cash fows at each future swap payment date $t_{i}$ is:  

$$
P V_{i}=(C_{F L,i}-C_{X})d_{i}
$$  

where the foating cash fow depends on the appropriate forward rate and $d_{i}$ is the discount factor (which depends on spot interest rates measured from today, $t_{-}$ ). The PV of the swap (with $n$ remaining payments) is simply the sum of these PVs:  

$$
V_{s w a p}=\sum_{i=1}^{n}{P V_{i}}
$$  

At inception the swap has zero value. Suppose the pay-fxed swap has been in existence for some time and currently has a positive market value. To calculate the swap’s delta we need to fnd the change in the present value of the swap due to a 1 bp (per annum) increase in interest rates (over a short time horizon). To do so we calculate the new present value of the swap with all interest rates 1 bp higher (using the ‘forward rate method’ for the FRN) – this is sometimes referred to as the ‘perturbation method’.2 We therefore undertake the following steps:  

1. We know the current value of the swap, $V_{s w a p}=\sum_{i=1}^{n}{P V_{i}},$   
2. Set ‘new’ spot rates $\b=$ existing spot rates plus 1 bp.   
3. Calculate new discount factors, $d_{i}^{*}$ and forward rates, $f_{i}^{*}$   
4. Calculate new foating cash fows, $C_{F L,i}^{*}=f_{i}^{*}m_{i}Q$ at each payment date and keep the   
fxed cash fows $C_{X}$ unchanged.   
5. Calculate the new net cash fows $(C_{F L,i}^{*}-C_{X})$ .   
6. Calculate the new PV of each net cash fow, $P V_{i}^{*}=(C_{F L,i}^{*}-C_{X})d_{i}^{*}$ using the new dis  
count (spot) rates.   
7. Calculate the change in PV at each payment date, $P V_{i}^{*}-P V_{i}$ .   
8. Calculate change in PV of all future cash fows, $d{\cal V}_{s w a p}=\sum_{i=1}^{n}({\cal P V}_{i}^{\ast}-{\cal P V}_{i}).$  

The (dollar) change in the value of the swap $d V_{s w a p}$ for a 1 bp increase in all spot rates is referred to as the swap’s delta (or the ‘present value of a basis point’, PVBP). A swap dealer will have a large number of interest rate swaps and it can aggregate all the fxed and foating cash fows at each payment date. The individual (net) cash fows from each swap may be positive or negative, as may their aggregated value at any payment date.  

Suppose it is 15 April-01 and (to simplify matters) assume the aggregated swaps book only has payments every 6 months, with three further payments remaining. The next aggregated payments are on 15 September-01, 15 March-02, and 15 September-02. On 15 April-01 suppose the delta’s for each of the three net cash fows are $\$10,000$ , $\$9,500$ , and $\$8,400$ (Table 35.1) – giving a total swap delta of $\Delta_{s p}=\mathfrak{F}27,900$ . Since all the deltas are positive then, if interest rates increase (fall) over the next week by 1 bp, the present value of the swap position increases (falls) by $\$27,900$ (over the next week).3  

TABLE 35.1 Hedging the PV of the swap (receive-foat, pay-fxed)   
Today is 15 April-01 Three payment dates remaining: 15 September-01, 15 March-01, 15 September-02.   


<html><body><table><tr><td></td><td>15 September-01</td><td>15 March-01</td><td>15 September-02</td></tr><tr><td>Change in PV of net cash flows, for 1 bp change,</td><td>$10,000</td><td>$9,500</td><td>$8,400</td></tr><tr><td>PV*-PV Delta of one long Eurodollar</td><td>-$25</td><td>-$25</td><td>-$25</td></tr><tr><td>futures Number of futures</td><td></td><td></td><td></td></tr><tr><td>Aggregate delta for futures</td><td>400 (= $10,000/$25) -$10,000</td><td>380 (= $9,500/$25) -$9,500</td><td>336 (= $8,400/$25) -$8,400</td></tr><tr><td>= NF× $25</td><td></td><td></td><td></td></tr></table></body></html>

Note: Today is 15 April-01. Three payment dates remaining: 15 September-01, 15 March-02, 15 September-02. Total $N_{F}$ for the hedge $=400+380+340=1,120$ .  

# 35.3.4 Hedging the Present Value of a Swaps Book  

We can hedge the (present) value of the cash fows in the swap using any fxed income assets such as bonds, interest rate futures, and interest rate options – since their market value changes as interest rates change and therefore they can be used to ofset any changes in the PV of the swaps position. By far the most popular method uses Eurodollar futures because they are liquid out to long maturities of 20–30 years.  

When interest rates increase by 1 bp (per annum), the value of a receive-foat, pay-fxed swap increases (i.e. positive delta), as the PV of the fxed payments is lower. To hedge we need to take a position in futures where a rise in interest rates leads to a loss on the futures – that is, today we take a long position in Eurodollar futures which have a ‘delta’ or ‘tick value’ of $\$25$ . Table 35.1 shows that the number of contracts needed (for each reset date) is:  

$$
N_{F}=({\mathrm{Swap}}^{*}{\mathrm{sportfolio~delta~at~each~payment~date}})/{\updownarrow}25.
$$  

Since we are only considering a potential change in interest rates over, say, 1 week, we can in principle use any interest rate futures contracts which mature after 1 week. But our rebalancing period might be longer than a week, in which case we might use longer dated Eurodollar contracts.  

Consider implementing a strip hedge on 15 April-01. You take a long position in 400 September-01, 380 March-02 and 340 September-02 contracts – a total of 1,116 long contracts. Of course we could also use other Eurodollar strategies. For example, a stack hedge involves going long 1,116 September-01 contracts or 1,116 September-02 contracts.  

If over the next few days (say) interest rates rise by 1 bp, then the (approximate) increase in the present value of the swaps position $(\$27,900)$ would be ofset by the $\$27,900$ losses on the long futures positions.4 So the mark-to-market value of the hedge position would remain constant over a ‘short’ time horizon.  

We have removed the interest rate risk on the PV of the swaps book. The swap dealer will feel happy holding less of a (regulatory) ‘capital bufer’ against the market risk of its swaps book, since it is hedged and the risk of losses from changes in the value of the swaps book is minimal (and the regulator will agree). From time to time the swap dealer will rebalance its position in 1,116 futures and calculate a new hedge position for $N_{F}$ . This is because as interest rates change and as time moves on, this changes the delta of the swaps book.  

# 35.3.5 Gamma and Convexity  

Note that as swaps are equivalent to a ‘long-short’ bond portfolio, they have a non-linear (convex) response to interest rate changes. Our swaps ‘delta hedge’ is only efective for small changes in interest rates – or equivalently the hedge is only accurate over short time horizons. So the delta-hedged position should be rebalanced frequently (as we did when hedging options positions). If we thought there would be large changes in interest rates (over a short time period) then we require an estimate of the swaps’ gamma. (This is a very similar concept to the convexity of a bond). As a Eurodollar futures contract has zero gamma we cannot use this to hedge the gamma of the swaps book.  

To gamma hedge the swaps position, we require fxed income instruments that have a non-zero gamma – we could use FRAs, cash market bonds, options on T-bonds, or caps and foors. Using FRAs has the advantage that they have a zero vega and so do not introduce the additional complication of sensitivity to changes in the volatility (standard deviation) of interest rates. To see how this might work suppose the delta and gamma of our (total) swaps book are $\Delta_{s p}=2\AA,000$ and $\Gamma_{s p}=-30$ respectively. We frst gamma hedge and then delta hedge our swap position:  

1. Take positions in FRAs (and/or bonds) with a portfolio gamma $\Gamma_{B}=+30$ , which then ofsets the gamma of the swaps book. Suppose the FRAs used to obtain a zero gamma have a portfolio delta of $\Delta_{B}=-500$ .  

2. The new delta for the ‘swaps plus FRAs’ is $+1,500$ $(=2,000-500)$ . So if interest rates rise, the value of our current portfolio (i.e. swaps $+\mathrm{FRAs}^{\prime}$ ) also rises.   
3. Now take positions in Eurodollar futures to ofset this ‘new delta’. We go long 60 $(=1,500/25)$ Eurodollar futures. If interest rates rise there is a fall in value of our Eurodollar futures position and we close out at a loss, which balances the gain on our ‘swaps plus FRAs’.  

The mark-to-market swaps position would then be largely protected from both large and small changes in interest rates. While swap dealers delta-hedge their swaps position with futures, they often do not gamma hedge and are therefore subject to some price risk on their swaps book, if there are large changes in interest rates over a short time period.  

# 35.3.6 Allocation of Cash Flows to Standard Payment Dates  

In the above example we assumed all cash fows from the swaps occurred at specifc fxed dates, 6 months apart. This is unrealistic, as swap dealers will have net cash fows in their swaps book on almost every day of the year. We therefore have a problem in aggregating cash fows, as our swaps do not have cash fows on exactly the same payment dates. Swap cash fows that fall between ‘standard’ payment dates need to be allocated to ‘standard time buckets’ to make the above calculations manageable.  

Suppose it is 15 February $(t=0)$ and the ‘standard’ payment dates we have chosen (arbitrarily) are at $t_{1}$ (15 June) and $t_{2}$ (15 December). A future known cash fow in the swap $C_{t}$ falls between these two standard payment dates $(t_{1}<t<t_{2})$ – for example on 10 October.  

How should we allocate $C_{t}$ which accrues on 10 October, so that we end up with $C_{1}$ allocated to $t_{1}$ (15 June) and $C_{2}$ allocated to $t_{2}$ (15 December)? We use an allocation method that ensures the following:  

1. PV of the allocated cash fows $C_{1},C_{2}$ equals the PV of the actual cash fow $C_{t}$ :  

$$
\begin{array}{c}{{V_{t}=V_{1}+V_{2}}}\\ {{C_{t}e^{-r_{t}t}=C_{1}e^{-r_{1}t_{1}}+C_{2}e^{-r_{2}t_{2}}}}\end{array}
$$  

where (continuously compounded) interest rates are measured from today $t=0$ (15 February, Figure 35.1).  

2. The change in PV of the allocated cash fows $C_{1},C_{2}$ equals the change in PV of the actual cash fow $C_{t}$ (for a parallel shift in the yield curve):  

$$
\begin{array}{c}{d V_{t}=d V_{1}+d V_{2}=(\partial V_{1}/\partial r_{1})d r_{1}+(\partial V_{2}/\partial r_{2})d r_{2}}\\ {(t\ C_{t}e^{-r_{t}t})d r=[t_{1}(C_{1}\ e^{-r_{1}t_{1}})+t_{2}(C_{2}e^{-r_{2}t_{2}})]d r}\end{array}
$$  

![](a4ba4a78fb85e42665f222b70374c4bb39546e73db02088cc16f7cf2e4796e45.jpg)  
FIGURE 35.1 Allocation of cash fows  

where $\partial V_{i}/\partial r_{i}=\partial(e^{-r_{i}t_{i}}C_{i})/\partial r_{i}=-t_{i}(e^{-r_{i}t_{i}}C_{i})$ , (for $i=1,2{\it\Psi}$ ) and $d r_{i}=d r$ for a parallel shift in the yield curve.5 Given current spot yields and the actual cash fow $C_{t}$ , Equations (35.18) and (35.19) can be solved for the two unknowns, $(C_{1},\ C_{2})$ – the dollar amounts to allocate to each standard ‘time-bucket’ at $t_{1}$ and $t_{2}$ . The coupons $C_{t}$ include all cash fows in the swaps book which fall on 10 October. This allocation process has to be repeated for each cash fow that falls between any two standard payment dates.  

# 35.4 CREDIT RISK  

Hedging credit risk in the swap’s book is a key issue for a swap dealer. In a swap between a dealer-D and company-A only one party will face default risk at any one time. This is because at time $t>0$ if the value of the swap to the dealer is $V_{D}>0$ , then $V_{A}=-V_{D}<0$ . It is only if $V_{D}>0$ and company-A defaults that there is a problem for the swap dealer. On the other hand if the swap dealer defaults when $V_{D}>0$ , then company-A is not harmed since the value of the swap to company-A is negative $(V_{A}<0)$ ). In this case company-A could simply discontinue its swap payments, although in practice it may not do so because of general reputation efects in the market.  

As the value of the swap changes over the life of the swap then either party can in principle be subject to default risk at some time during the life of the swap. However, because the principal in an interest rate swap is not actually exchanged, the default risk in an interest rate swap is less than the default risk of holding a portfolio of bonds – where the principal payments do infuence the market value of the bond portfolio.  

Credit risks in a fxed-for-foating swap are di\$cult to assess but these risks are often managed by using so-called credit enhancements. The most common method to limit credit risk is to pledge some sort of collateral, such as a line of credit from a bank or securities (e.g. T-bonds) which are held ‘in trust’ by a third party. For example, if one party undergoes a downgrade in its Standard and Poor’s or Moody’s credit rating, the collateral can be increased.  

Alternatively, marking-to-market occurs when periodically the swap’s value is calculated and the party with a negative swap value pays the counterparty this amount in cash. The swap rate then has to be reset to give a zero current value for the swap, based on current interest rates. The new swap rate determines the fxed payments in the swap until the next ‘mark-to-market’ date, when the procedure is repeated. Clearly this procedure is similar to margin payments in a futures contract.  

Netting is a fairly simple form of credit enhancement. If at $t>0$ the swap dealer’s position with company-Z is $+\$50$ and on another swap contract with company-Z it is minus $\$40$ then they can agree that the outstanding net position for the swap dealer is $\$10$ . Hence if company-Z defaults, the swap dealer is only exposed to $\$10$ credit risk rather than $\$50$ .  

However, it must be pointed out that in the event of bankruptcy by company-Z, it is not always clear that the bankruptcy courts will legally accept such a deal. It is worth noting that in the UK the House of Lords deemed that UK Local Authorities (i.e. equivalent to US Municipal Authorities), acted ultra vires (i.e. beyond the scope of authority) in entering into swap contracts and these contracts then became null and void – even though Local Authorities had the funds to pay the losses on their swaps positions. Total losses from vanilla interest rate swap defaults have historically been very low (e.g. less than $1/_{2}\%$ of the principal value of all swaps entered into). This is probably because swap deals tend to involve large well-capitalised organisations with high credit ratings and a ‘favourable reputation’ to preserve.  

# 35.5 SUMMARY  

• We can adapt the techniques used for plain vanilla fxed-for-foating interest rate swaps, to price and value more complex interest rate swaps.   
• The swap rate is calculated assuming the swap must have zero value (to both parties) at inception – otherwise the swap would not take place. The swap rate is calculated by making the value of the fxed leg of the swap equal to the value of the foating leg, at inception of the swap.   
• After the swap has been initiated the value of the swap may be positive or negative (to one of the parties).   
• Complex interest rate swaps such as a spread-to-LIBOR swap, an of-market swap, a zero-coupon swap, a swap with a time varying swap rate (for the ‘fxed’ payments) and a swap with a variable notional principal, can all be priced by using a replication bond portfolio (i.e. a fxed rate bond and an FRN) to represent the cash fows in the swap.  

• Hedging the market risk of swaps is usually done by calculating the delta of the swaps book (for standard time buckets) and using interest rate futures to delta hedge the interest rate risk. If the swap dealer is worried about large changes in interest rates then she can also hedge the gamma of her swaps book using FRAs, bonds, or (fxed income) options (although using options also introduces vega risk). After gamma hedging, the swaps dealer can then use interest rate futures to hedge the swap’s delta.  

• Credit risk of a swap can be mitigated using collateral, netting, and credit enhancements.  

# EXERCISES  

# Question 1  

Suppose a plain vanilla interest rate ‘at-market’ swap (which has zero value at inception) has a swap rate of $s p=6\%$ . You want a ‘receive-fxed, pay LIBOR’ swap at an ‘of-market’ fxed swap rate of $6.1\%$ . What will happen when you enter the swap and what will determine your future fxed payments?  

# Question 2  

Suppose a plain vanilla fxed-for-foating (LIBOR) ‘at-market’ swap (which has zero value at inception) has a swap rate of $6\%$ p.a. You want a ‘spread-to-LIBOR’ swap where you receive $\mathrm{LIBOR}{+2\%}$ and pay fxed. Will you pay more or less than $6\%$ p.a. fxed? What alternative arrangement might happen when you enter the swap?  

# Question 3  

A bank pays 30-day LIBOR- $1\%$ on its deposits and receives 360-day LIBOR from its bank loans. How might it use a yield curve swap to hedge its interest rate risk over the next 2 years?  

# Question 4  

Why does it make sense for a swap dealer to hedge the market-to-market value of her (interest rate) swaps book rather than hedge just the future foating rate payments?  

# Question 5  

What is the delta of a (interest rate) swaps book?  

# Question 6  

You have delta-hedged your (interest rate) swaps book on Monday and are going to reassess the hedge in a week’s time. On Monday, have you eliminated all market risk and if not how might you improve your hedged positon?  

# Question 7  

When is a swap dealer subject to credit risk (due to a default of the swap counterparty)?  