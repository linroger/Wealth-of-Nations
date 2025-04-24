---
tags:
  - currency_swaps
  - foreign_exchange
  - fxed_fxed
  - interest_rates
  - usd_euro
aliases:
  - Currency Swap
  - Fixed-Fixed Currency Swap
  - USD-Euro Swap
key_concepts:
  - Euro liability
  - USD loan
  - fixed interest rate
  - foreign exchange exposure
  - plain vanilla currency swap
---
# Currency Swaps  

# Aims  

• To examine the reasons for undertaking a plain vanilla currency swap of fxed-USD for fxed-Euros.   
• To show how a fxed-fxed USD-Euro currency swap can be replicated with a fxed rate bond in USD and a fxed rate bond in Euros.   
• To demonstrate how swap rates in USD and Euros are determined in the fxed-fxed currency swap.   
• To show how to value a ‘fxed-fxed’ USD-Euro currency swap at any time $t$ after inception, using a replication portfolio of (a) a USD bond and Euro bond or (b) by considering the swap as a strip of FX-forward contracts.   
• To show why currency swaps change in value over time.  

# 36.1 USES  

A plain vanilla currency swap involves two parties exchanging cash fows denominated in diferent currencies. One reason for undertaking a swap might be that a US frm (‘UncleSam’) with a subsidiary in Euroland selling hamburgers, might wish to borrow $\mathsf{\epsilon}_{\mathrm{i}00\mathrm{m}}$ at a fxed interest rate and eventually pay of the euro interest and principal with revenues from sales of its hamburgers in Euroland. This reduces the foreign exchange exposure of UncleSam as its payments on the Euroland debt are matched by receipts in euros.1  

However, it might be relatively expensive for UncleSam to raise euro fnance from its correspondent euro bank (Société Générale, say), as it might not be ‘well established’ in this ‘foreign’ loan market. But, if UncleSam raises fnance (relatively) cheaply using a fxed-rate USD loan (from its US correspondent bank, Citibank), it could then go to a swap dealer (Goldman) and agree to receive (fxed) USD interest and pay (fxed) Euro interest in the swap. Considering UncleSam’s USD loan and the ‘receive-USD pay-Euros’ swap, efectively UncleSam now has a Euro liability (which can be paid of from the Euro receipts earned by its Euroland subsidiary).  

‘UncleSam’ ultimately wants to borrow in euros but fnds it cheaper to initially borrow in US dollars and then agree a currency swap to receive US dollars and pay euros.  

Note that unlike interest rate swaps where the principal is ‘notional’ and is not exchanged either at the beginning or the end of the swap, this is not the case for currency swaps, where the principal amounts are exchanged at the outset and at the end of the swap.  

# 36.1.1 Fixed-Fixed Currency Swap  

The currency swap enables UncleSam to achieve its desired outcome. Let’s see how this works out in detail. Suppose the current spot exchange rate is $\$1.4$ per euro and UncleSam requires $\mathsf{\epsilon}_{\mathrm{i}00\mathrm{m}}$ to fnance its expansion in Euroland. UncleSam borrows $\$1400$ from Citibank in New York (or it issues $\$1400$ of US bonds) at a fxed USD interest rate of $5.36\%$ . The swap dealer Goldman then agrees to pay UncleSam the USD-swap rate of $5.36\%$ in exchange for receiving the Euro-swap rate of $4.46\%$ from UncleSam. The swap involves the following stages.  

# At $\pmb{t}=\mathbf{0}$ (Figure 36.1)  

• UncleSam borrows $\$1400$ from Citibank in New York at a USD interest rate of $5.36\%$ and passes this $\$1400$ to the swap dealer Goldman, who in return gives UncleSam $\mathsf{\epsilon}_{\mathrm{{l00m}}}$ . (UncleSam uses this to invest in its Euroland hamburger subsidiary.)  

# At $\pmb{t}>\mathbf{0}$ (Figure 36.2)  

• UncleSam’s revenues from its Euroland subsidiary are used to pay Goldman \$4.46m p.a. ( $4.46\%$ of $\mathsf{\epsilon}_{\mathrm{{l00m}}}\mathrm{{,}}$ ) over the life of the swap.   
• Goldman pays $\$7.845$ p.a. $5.36\%$ of $\$140\mathrm{m}$ ) in the swap to UncleSam, who then uses this to pay interest on its USD loan to Citibank.  

![](4a5fccae58e42449f78e2f4007c3339a0f2632b63b152a16dce5d4d93ea283e2.jpg)  
FIGURE 36.1 Principal cash fows at initiation of currency swap  

The current spot rate is 1.4 USD per Euro.  

![](0d208a02e9163ffac856733da0ce7786de8f34ad2e54e04426aaf2016bf267ec.jpg)  
FIGURE 36.2 Cash fows in a currency swap  

# At maturity of the bank loan/swap  

• UncleSam pays $(\mathsf{E100m+}\mathsf{E4.46m})$ to Goldman (from revenues earned in Euroland). • Goldman pays $(\$140m+\$7.84m)$ to UncleSam, who uses it to pay of the loan principal plus the last interest payment to Citibank.  

Even though UncleSam initially borrows USD nevertheless after the swap, it is as if UncleSam has a Euro loan. This synthetic Euro loan may be at a lower interest rate than if UncleSam directly borrows in Euros from Société Générale (say).  

In fact, an exchange of fxed cash fows in a foreign currency, for fxed cash fows in the home currency is not very common but it is useful to analyse this case. Example 36.1 illustrates how you can ‘create’ a fxed-fxed currency swap from two liquid fxed-for-foating swaps in two diferent currencies.  

# EXAMPLE 36.1  

# Creating a Fixed-Fixed Currency Swap in Practice  

A fxed-fxed currency swap is usually ‘created’ from two other fxed-for-foating swaps. For example, a ‘pay-Euro fxed, receive-USD fxed’ currency swap can be constructed from:  

(continued)  

(continued)  

(i) a ‘pay-Euro fxed, receive-USD LIBOR’ swap and  

(ii) a ‘receive-USD fxed, pay-USD LIBOR swap.  

The usual swap convention is to quote a fxed swap rate in the foreign currency against foating (LIBOR) in the home currency. For example, for a US company (UncleSam) this might be Euro fxed-swap rate against USD-LIBOR. Less often, both sides of the currency swap might be foating – this is a basis currency swap.  

# 36.1.2 Swap as a Strip of Forward Contracts  

UncleSam’s receive-USD, pay-Euros currency swap could also be achieved by UncleSam entering into a strip of FX-forward contracts to pay euros and receive US dollars each year, at whatever today’s current quoted forward FX rates happen to be, $F_{1},F_{2}$ . The cash fows each year will be exchanged at these diferent forward FX rates. This approach provides a useful method of pricing and valuing the swap – as we see later.  

From the swap dealer’s viewpoint, the swap has Goldman paying USD-fxed and receiving cash fows in euros. Goldman will have many currency swaps on its books in diferent currencies and it is unlikely that it can fnd matching counterparties to all these diferent swaps. But Goldman can hedge all its swap net cash fows in any (one) currency, by using currency futures contracts, to ofset any adverse future changes in spot exchange rates. (It can also use interest rate futures to hedge any interest rate risk, which afects the market value of the swap.) However, the largest risk to the swap dealer in a currency swap tends to come from volatile exchange rates rather than changing interest rates.  

# 36.2 PRICING A FIXED-FIXED CURRENCY SWAP  

UncleSam is receiving (fxed) USD cash fows in the swap and paying (fxed) Euro cash fows, at each payment date. How do we price this currency swap, that is, determine the fxed swap rate in US dolalrs and the swap rate in euros? Surprisingly, the two swap rates in the fxed-fxed currency swap are given by the two swap rates for plain vanilla interest rate swaps in each of the two countries (with the same tenor and maturity). Because the argument is a bit detailed note that the result we are looking for is as follows:  

If the current (at-market) swap rate in a plain vanilla fxed-for-LIBOR interest rate swap in the US is $s p^{\S}$ and $s p^{\varepsilon}$ is the equivalent rate for a Euro-zone plain vanilla interest rate swap, then these two swap rates are the correct swap rates for the fxed-fxed currency swap, US dollars for euros.  

In other words, if we know the (fxed-for-foating) interest rate swap rates in the two countries we do not have to make a separate calculation of the fxed-fxed currency swap rates. Let’s see why the two swap rates for the fxed-fxed currency swap are the same as the two interest rate swap rates, in each of the two countries.  

At the outset of the currency swap the notional principals are exchanged. UncleSam exchanges $Q^{\varepsilon}=\mathsf{E100m}$ for $Q^{\S}=\$1400$ (from Goldman, the swap dealer) at the current exchange rate ${\cal E}_{0}=1.4~\S/\epsilon.$ – today, this is worth the same to both parties (i.e. UncleSam and Goldman), since $Q^{\S}=Q^{\varepsilon}E_{0}=\S140\mathrm{m}$ .  

Table 36.1 shows the current USD spot interest rates (quoted on 15 March-01) from which we can calculate (in the usual way) the swap rate for a 3-year vanilla fxed-for-foating interest rate swap in USD and this is found to be $s p^{\S}=5.35\%$ p.a. (per $\$1$ notional principal). Given this swap rate, we know that the current value of all the future USD-LIBOR foating cash fows equal all future fxed-USD cash fows. Hence, given $s p^{\S}=5.35\%$ all future fxed USD cash fows in a USD vanilla interest rate swap with a principal of $Q^{\S}=\S140\mathrm{m}$ are worth $\$1400$ today.  

Similarly, given the Euroland yield curve on 15 March-01, the Euro swap rate for a vanilla fxed-for-foating Euro interest rate swap is $s p^{\varepsilon}=4.46\%$ (per \$1 notional principal) – Table 36.2.  

Hence, given $s p^{\varepsilon}=4.46\%$ all future fxed Euro cash fows in a Euro vanilla interest rate swap with a principal of $Q^{\varepsilon}=\mathsf{E100m}$ are worth $\mathsf{\epsilon}_{\mathrm{t100m}}$ today. But $\mathsf{\epsilon}_{\mathrm{t100m}}$ today is worth $E_{0}Q^{\varepsilon}=\mathfrak{H}140\mathrm{m}$ today. Suppose we use the two current ‘at-market’ swap rates $(s p^{\S}=5.35\%$ , $s p^{\varepsilon}=4.46\%)$ from the vanilla interest rate swaps in the US and the Euro-zone as the two swap rates in a fxed-fxed currency swap. Then the present value of all the future Euro fxed cash fows in the currency swap is $\mathsf{\epsilon}_{\mathrm{{l00m}}}$ , which today is equivalent to $\mathrm{US}\$140\mathrm{m}$ . But the latter is the same as the present value of all the future USD fxed cash fows in the currency swap. Hence, if the two swap rates in the fxed-fxed currency swap are quoted as $s p^{\S}=5.35\%$ and $s p^{\varepsilon}=4.46\%$ you would willingly enter the fxed-fxed currency swap, because the net value of the swap in US dollars (or euros) is zero.  

TABLE 36.1 Swap rate for vanilla USD interest rate swap   


<html><body><table><tr><td colspan="4">Notional principal</td></tr><tr><td colspan="2">Days in year (swap convention) Days in 1st reset period (for 1st floating coupon)</td><td colspan="2">360 184</td></tr><tr><td colspan="2">LIBOR at last reset period (for 1st floating coupon)</td><td colspan="2">5.15%</td></tr><tr><td>Date</td><td>Days </td><td>Cumulative days</td><td>Spot rates LIBOR</td></tr><tr><td>15-Mar-01</td><td></td><td></td><td>LIBOR</td></tr><tr><td>15-Sep-01</td><td>184</td><td>184</td><td>0.9744</td></tr><tr><td>15-Mar-02</td><td>181</td><td>365</td><td>5.15 5.27</td></tr><tr><td>15-Sep-02</td><td>184</td><td>549</td><td>5.36</td></tr><tr><td>15-Mar-03</td><td>181</td><td>730</td><td>5.45</td></tr><tr><td>15-Sep-03</td><td>184</td><td>914</td><td>0.9005 0.8767</td></tr><tr><td>15-Mar-04</td><td>182</td><td>1096</td><td>0.8532</td></tr><tr><td></td><td></td><td></td><td>Swap rate = 0.0536</td></tr></table></body></html>  

TABLE 36.2 Swap rate for vanilla Euro interest rate swap   


<html><body><table><tr><td colspan="2">Notional principal Days in year (swap convention)</td><td colspan="2">1m 360 184 4.15%</td></tr><tr><td colspan="2">Days in 1st reset period (for 1st floating coupon) LIBOR at last reset period (for 1st floating coupon)</td></tr><tr><td>Date Days</td><td>Cumulative days</td><td>Spot rates</td><td>Discount factor</td></tr><tr><td>15-Mar-01</td><td></td><td>LIBOR</td><td>LIBOR</td></tr><tr><td>15-Sep-01</td><td>184</td><td>4.15</td><td>0.9792</td></tr><tr><td>15-Mar-02</td><td>181</td><td>184 365</td><td>0.9585</td></tr><tr><td>15-Sep-02</td><td>184</td><td>549</td><td>4.27 4.36</td></tr><tr><td>15-Mar-03</td><td>181</td><td>730</td><td>0.9377 4.45</td></tr><tr><td>15-Sep-03</td><td>184</td><td>914</td><td>0.9172 4.54 0.8966</td></tr><tr><td>15-Mar-04</td><td>182</td><td>1096</td><td>4.65 0.8760</td></tr><tr><td></td><td></td><td></td><td>Swap rate = 0.0446</td></tr></table></body></html>  

# 36.3 VALUING A FIXED-FIXED CURRENCY SWAP  

# 36.3.1 Currency Swap as a Bond Portfolio  

The cash fows in the swap are shown in Figure 36.3. From ‘UncleSam’s’ perspective the swap is equivalent to a synthetic position consisting of:  

Long a fxed rate dollar denominated bond and short a fxed rate Euro denominated bond  

Receives \$’ fxed and pays €’ fxed  

The swap has zero value at inception. But the value of the swap at some time $t>0$ depends on the value of the two fxed rate bonds. Consider valuing the swap at $t$ before the frst payment  

![](905c7de9fd593c27ebfbff77c905dde1105c983c170472bcf549934973ae22e7.jpg)  
FIGURE 36.3 Value of currency swap at t  

date $(t_{0}<t<t_{1})$ . The value (in USDs) of the ‘receive-fxed USD, pay-fxed Euro’ swap at time $t$ is:  

$$
V_{s p}^{\mathfrak{s}}(t)=V_{F i x}^{\mathfrak{s}}(t)-E_{t}\ V_{F i x}^{\varepsilon}(t)
$$  

where $E_{t}$ is the spot FX rate (USD per Euro) at time $t$ and  

$$
\begin{array}{l}{{\displaystyle V_{F i x}^{\$*}=C^{\S}\sum_{i=1}^{n}d_{i}^{\S}+Q^{\S}d_{n}^{\ S}}}\\ {{\displaystyle V_{F i x}^{\varepsilon}=C^{\varepsilon}\sum_{i=1}^{n}d_{i}^{\varepsilon}+Q^{\varepsilon}d_{n}^{\varepsilon}}}\end{array}
$$  

where $d_{i}$ are the discount factors (in the two countries). Assume $h^{\mathbb{S}}=h^{\varepsilon}=180/360$ and $s p_{0}^{\S}=$ $5.36\%$ and $s p_{0}^{\varepsilon}=4.46\%$ , both of which were fxed at inception on 15 March-01. At $t=0$ the future fxed cash fows in USD and Euros are:  

$$
\begin{array}{r l}&{C^{\Phi}=(s p_{0}^{\mathfrak{H}}.h^{\mathfrak{H}}Q^{\mathfrak{H}})=0.0536\ \left(180/360\right)\ \mathfrak{H}140\mathrm{m}=\mathfrak{H}3.752\mathrm{m}}\\ &{C^{\varepsilon}=(s p_{0}^{\varepsilon}.h^{\varepsilon}Q^{\varepsilon})=0.0446\ \left(180/360\right)\ \in100\mathrm{m}=\mathfrak{t}2.23\mathrm{m}}\end{array}
$$  

The value of the swap to UncleSam will change if either USD-LIBOR or Euro-LIBOR interest rates change or the spot exchange rate changes. In the swap UncleSam has (fxed) future payments in euros, so a rise in the euro exchange rate against the US dollar will involve UncleSam paying out more USD and hence the USD value of the swap to UncleSam will fall (see Equation 36.1). However, a rise in euro interest rates will reduce the PV of UncleSam’s euro payments (Equation 36.3) and hence increase the swap’s USD value to UncleSam (Equation 36.1). Finally, if USD-LIBOR rates rise this will reduce the PV of the USD cash infows and the value of the swap to UncleSam will fall. (The change in the value of the swap to the swap dealer is the opposite of that to UncleSam.)  

The swap has zero value at inception on 15 March-01 and it terminates on 15 March-04. Suppose we want to value the swap to UncleSam on 15 September 02, when there are three payments left on 15 March-03, 15 September-03, and 15 March-04. Note that spot interest rates in the two countries and the spot-FX rate will be diferent on 15 September-02, than at inception of the swap at $t=0$ .  

To simplify our calculations we assume that on 15 September the USD-LIBOR curve is fat at $5.5\%$ and the Euro-LIBOR curve is fat at $4.5\%$ (both continuously compounded) and the euro has appreciated from $1.4(\$/£)$ to $E_{t}=1.5(\S/£)$ . We also assume the number of days between payment dates is exactly $^1/_{2}$ year, so the new discount rates are $d_{i}=\exp(-r_{i}.t_{i})$ where $t_{i}={^{1}}/_{2}$ , 1 and 3/2.2  

$$
\begin{array}{r l}&{V_{F i x}^{\S}(t)=\S3.752\mathrm{m}\left[e^{-0.055(1/2)}+e^{-0.055(1)}+e^{-0.055(3/2)}\right]+\S140\mathrm{m}e^{-0.055(3/2)}}\\ &{\qquad=\S3.752\mathrm{m}\left[0.9729+0.9465+0.9208\right]+\S140\mathrm{m}[0.9208]}\\ &{\qquad=\S139.5684\mathrm{m}}\end{array}
$$  

$$
\begin{array}{r l}&{V_{F i x}^{\varepsilon}(t)=\mathsf{t}2.23\mathsf{m}\left[e^{-0.045(1/2)}+e^{-0.045(1)}+e^{-0.045(3/2)}\right]+\mathsf{t}100\mathsf{m}e^{-0.045(3/2)}}\\ &{\qquad=\mathsf{t}2.23\mathsf{m}\left[0.9778+0.9560+0.9347\right]+\mathsf{t}100\mathsf{m}\left[0.9347\right]}\\ &{\qquad=\mathsf{t}99.8668\mathsf{m}}\end{array}
$$  

$$
V_{s p}(t)=V_{F i x}^{\ast}(t)-E_{t}\enspace V_{F i x}^{\varepsilon}(t)=-\mathbb{\S}10.2317\mathrm{m}
$$  

Because of the rise in the euro since the initiation of the swap, the value of the swap to UncleSam has fallen because the value of the fxed cash payments UncleSam has to make in euros, require higher dollar payments.  

# 36.3.2 Currency Swap as a Strip of Forward Contracts  

‘UncleSam’ receives annual USD receipts of $\$3.752\mathrm{m}$ and the principal of $\$1400$ at the end of the swap and pays out $\epsilon2.23\mathrm{{m}}$ annually with a repayment of principal of $\mathsf{\epsilon}_{\mathrm{i00m}}$ at the termination of the swap. This is a series of forward contracts, to receive USD and pay Euros at each reset date $t_{i}$ . The value of one of these forward cash fows in USDs is:  

$$
\mathrm{USD}=(C^{\mathfrak{F}}-F_{i}\ C^{\varepsilon})
$$  

where $F_{i}$ is the USD-Euro forward rate quoted on 15 September-02 for delivery at time $t_{i}$ (6, 12, and 18 months ahead). In addition, the two principals $Q^{\varepsilon}=\mathsf{E100m}$ and $Q^{\varepsilon}=\$1400$ are exchanged at maturity of the swap. The forward FX rates today (at time $t$ ) for delivery at horizons $t_{i}$ are:  

$$
F_{i}=E_{t}~e^{(r^{\S}-r^{\varepsilon})t_{i}}
$$  

The USD cash fows in (36.7) accruing at times $t_{i}$ must be discounted back to time $t$ , using USD risk-free rates, so each net cash fow has a present value in USD of:  

$$
\mathrm{USD}=(C^{\S}-F_{i}C^{\varepsilon})e^{-r^{\S}t_{i}}
$$  

The spot rate on 15 September-02 is $E_{t}=1.5(\S/\epsilon)$ , interest rates are $r^{\S}=5.5\%$ and $r^{\varepsilon}=4.5\%$ so forward FX-rates on 15 September-02 are $F_{1}=1.507519$ $(=1.5e^{0.01(1/2)})$ , $F_{2}=$ 1.515075 $(=1.5e^{0.01(1)})$ and $F_{3}=1.522670$ $(=1.5e^{0.01(3/2)})$ The value of the ‘receive-USD, pay-Euros’ swap is given by the sum of the terms in (36.9) discounted at the USD interest rate $r^{\S}=5.5\%,$ :  

$$
\begin{array}{r}{[\S3.752\mathrm{m}-F_{1}\in2.23\mathrm{m}]e^{-0.055(1/2)}=\S379,647}\\ {[\S3.752\mathrm{m}-F_{2}\in2.23\mathrm{m}]e^{-0.055(1)}=\S353,401}\\ {[\S3.752\mathrm{m}-F_{3}\in2.23\mathrm{m}]e^{-0.055(3/2)}=\S328,219}\end{array}
$$  

$$
[\S140\mathrm{m}-F_{3}\in100\mathrm{m})]e^{-0.055(3/2)}=-\S11,295,594
$$  

$$
\mathrm{Total}=-\$10,234,327
$$  

So the receive-USD pay-Euros swap on 15 September-02 has a value to ‘UncleSam’ of minus $\$10,231,702$ , which is the same as that found by considering the swap as a long-short bond position (see Appendix 36.B for an algebraic proof). Note that the change in value of the swap is mainly due to the change in the (present) value of the fnal payments of principal after the change in the exchange rate from $1.4(\mathbb{S}/\epsilon)$ on 15 March-01 to $1.5(\S/\epsilon)$ , on 15 September-02. This large change in value would not occur in a plain vanilla interest rate swap because the principals are not exchanged (and its value does not depend on the exchange rate).  

# 36.4 SUMMARY  

• A plain vanilla ‘fxed-fxed’ currency swap involves the exchange of principals in two diferent currencies at the beginning and end of the swap and an exchange of foreign cash fows (Euros) for domestic cash fows (USD), over the life of the swap. • A currency swap must have zero value at inception – this is how we price the swap. We ensure that the swap rate in domestic currency (USD) and the swap rate in the foreign currency (Euros) give a zero value (in USD or Euros) at inception for the currency swap.  

• The two swap rates in a fxed-fxed currency swap are the same as the swap rates on fxed-for-foating vanilla interest rate swaps in the respective countries.   
• Cash fows in a fxed-fxed currency swap are equivalent to taking a long and short position in a domestic and foreign bond, respectively. This ‘synthetic swap’ enables one to calculate the value of a currency swap during the remaining life of the swap. Equivalently, the swap can be viewed as a strip of forward-FX contracts. Both methods give the same market value for the swap, at any time after inception.   
• Changes in interest rates in either country but especially changes in the exchange rate, lead to a change in the (mark-to-market) value of a currency swap.   
• Swap dealers (usually banks) take on one side of a swap contract and they will try and match the cash fows incurred, with other swap counterparties.   
• If the swap dealer cannot immediately fnd a matching counterparty to a currency swap she can hedge her net position in any currency. She can use currency futures contracts to hedge exchange rate risk and interest rate futures to hedge the interest rate risk in the two countries (which change the present value of the swap). The main risk to a swap dealer who does not have a matched swaps book in each currency comes from volatile exchange rates.  

# APPENDIX 36.A: PRICING A CURRENCY SWAP  

Consider a currency swap to pay-fxed USD and receive-fxed Euros. How do we price this currency swap? Surprisingly, the swap rates for the fxed-fxed currency swap are equal to the swap rates for plain vanilla interest rate swaps in the two countries:  

If the current (at-market) swap rate in a plain vanilla fxed-for-LIBOR interest rate swap in the US is $s p^{\S}$ and $s p^{\varepsilon}$ is the equivalent rate for the Euro-zone interest rate swap, then these swap rates will correctly price a fxed-fxed currency swap.  

The notation which follows may look a little complex but all we are doing is calculating the present values for a fxed interest rate bond in USD and in Euros. The (present) value of the USD-leg and Euro-leg of a fxed-fxed currency swap (in their respective currencies) are:  

$$
\begin{array}{l}{{\displaystyle V_{F i x}^{\S}=\sum_{i=1}^{n}C_{i}^{\S}d_{i}^{\S}+Q^{\S}d_{n}^{\ S}}}\\ {{\displaystyle V_{F i x}^{\varepsilon}=\sum_{i=1}^{n}C_{i}^{\varepsilon}d_{i}^{\varepsilon}+Q^{\varepsilon}d_{n}^{\varepsilon}}}\end{array}
$$  

The USD coupon payment is $C_{i}^{\mathfrak{S}}=(s p^{\mathfrak{S}}.h_{i}^{\mathfrak{S}}Q^{\mathfrak{S}})$ , where $h_{i}^{\mathfrak{F}}=$ day-count convention for the fxed-leg and the discount factor is $d_{i}^{\Phi}=\dot{1}/[1+r_{i}^{\Phi}.t_{i}^{\Phi}]$ , based on the USD-LIBOR rate, $r_{i}^{\mathbb{S}}=L I B O R_{i}^{\mathbb{S}}$ and $t_{i}^{\S}=d a y s_{i}^{\S}/360$ is the actual number of days from 0 to $t_{i}$ . These defnitions also apply to the Euro side of the swap which is based on the Euro-LIBOR term structure. At inception we know that the two present values in the currency swap must be equal (expressed in a common currency, here USD), otherwise the swap would not take place:  

$$
V_{F i x}^{\mathfrak{F}}=Q^{\mathfrak{s}}\left[s p^{\mathfrak{s}}\sum_{i=1}^{n}h_{i}^{\mathfrak{s}}d_{i}^{\mathfrak{s}}+d_{n}^{\mathfrak{s}}\right]=E_{0}V_{F i x}^{\varepsilon}=E_{0}.Q^{\varepsilon}\left[s p^{\varepsilon}\sum_{i=1}^{n}h_{i}^{\varepsilon}d_{i}^{\varepsilon}+d_{n}^{\varepsilon}\right]
$$  

where $E_{0}$ is the USD-Euro spot exchange rate at inception of the swap. At the outset of the swap the notional principals are exchanged. Suppose the US frm wants to initially have $Q^{\varepsilon}=$ $\mathsf{\epsilon}_{\mathrm{{l00m}}}$ funds available (e.g. to invest in a new plant in Europe) and the current exchange rate is $E_{0}=1.4(\S/£)$ so the US frm initially borrows $Q^{\mathfrak{s}}=Q^{\varepsilon}.E_{0}=\mathfrak{s}140\mathrm{m}$ (from Citibank, say). Substituting $Q^{\S}=Q^{\varepsilon}.E_{0}$ in (36.A.3) we fnd that for the value of the swap to be zero we require:  

$$
s p^{\S}\sum_{i=1}^{n}h_{i}^{\S}d_{i}^{\S}+d_{n}^{\S}=s p^{\varepsilon}\sum_{i=1}^{n}h_{i}^{\varepsilon}d_{i}^{\varepsilon}+d_{n}^{\varepsilon}
$$  

The next bit of the argument is quite subtle and requires us to remember the formulas for vanilla interest rate swaps (i.e. fxed-for-foating) for each ‘country’ taken in turn. The left-hand side of (36.A.4) is the present value of cash fows from the fxed-leg of a vanilla fxed-for-foating interest rate swap in the US (per $\$1$ notional principal), with a current at-market swap rate of $s p^{\S}$ . The value of the fxed leg in this swap must equal the value of the foating USD-LIBOR leg which we know equals $\$1$ . So the left-hand side of (36.A.4) is equal to $\$1$ . Hence a US vanilla interest rate swap with a principal of $Q^{\S}=\$1400$ has a present value of $\$1400$ .  

The right-hand side of (36.A.4) are cash fows from the fxed leg of a vanilla fxed-for-foating interest rate swap in the Euro-zone (per \$1 notional principal) with a swap rate of $s p^{\varepsilon}$ and we know that this fxed leg has a present value of \$1. Hence a Euro interest rate swap with a principal of $Q^{\varepsilon}=\mathsf{E}100\mathsf{m}$ would have a present value of $\mathsf{\epsilon}_{\mathrm{{l00m}}}$ . But $\mathsf{\epsilon}_{\mathrm{i}00\mathrm{m}}$ today is worth $E_{0}Q^{\varepsilon}=\mathfrak{H}140\mathrm{m}$ .  

Hence, as long as we use the current at-market swap rates on vanilla interest rate swaps in the US and the Euro-zone and use these same swap rates in the fxed-fxed currency swap, both parties will enter the currency swap because the (present) value of the USD fxed leg of $\$1400$ equals the present value of the Euro leg of $\$140\mathrm{m}(=E_{0}Q^{\varepsilon})$ .  

Hence, the at-market vanilla interest swap rates $s p^{\S}$ and $s p^{\varepsilon}$ make the value of the two legs of the currency swap equal (in USD terms) and hence correctly price the fxed-fxed currency swap. However, if one party wants to use a diferent swap rate to $s p^{\S}$ or $s p^{\varepsilon}$ in the cexucrrheancgyesowfacpatshena $V_{F i x}^{\Phi}-E_{0}V_{F i x}^{\varepsilon}$ twhoeulcdurnroetnbcey zsewroa.pTghievrenwb ethdei evnecteo $V_{F i x}^{\mathfrak{S}}-E_{0}V_{F i x}^{\varepsilon}$ $s p^{\S}$ $s p^{\varepsilon}$ counterparties.  

# APPENDIX 36.B: VALUATION OF A CURRENCY SWAP  

We show that two diferent synthetic portfolios can be used to value a fxed-fxed currency swap: (i) a bond portfolio and (ii) a strip of forward FX contracts. Both give the same value for the swap.  

Suppose a US (domestic) swap dealer has a ‘receive-USD, pay-Euro’ swap, which has been in existence for some time and we are valuing the swap at time t. The swap rates in the two currencies were determined at $t=0$ and these determine the remaining fxed payments and we assume there are $n$ payments remaining.  

# Currency Swap as a Synthetic Bond Portfolio  

The US swap dealer can be considered to be long a US bond with fxed coupon receipts $C_{X,i}^{\Phi}=$ $(s p_{0}^{\ s}h^{\ s}Q^{\$})$ and short a foreign bond with payments $C_{X,i}^{\varepsilon}=(s p_{0}^{\varepsilon}h^{\varepsilon}Q^{\varepsilon})$ and in addition, the principals $Q^{\S}$ and $Q^{\varepsilon}$ are exchanged at the end of the swap $\displaystyle{\mathit{t}=n} $ . Spot interest rates (continuously compounded) are all measured from time $t$ and the discount factors are $d_{i}=\exp(-r_{i}.t_{i})$ . The USD and Euro bonds have present values at $t$ :  

$$
V_{F i x}^{\S}(t)=C^{\S}\sum_{i=1}^{n}e^{-r_{i}^{\S}t_{i}}+Q^{\S}~e^{-r_{i}^{\S}t_{i}}
$$  

$$
V_{F i x}^{\varepsilon}(t)=C^{\varepsilon}\sum_{i=1}^{n}e^{-r_{i}^{\varepsilon}t_{i}}+Q^{\varepsilon}e^{-r_{n}^{\varepsilon}t_{n}}
$$  

Converting from Euros into USD, at the current spot rate $E_{t}$ gives the value of the swap at $t$ :  

$$
\begin{array}{l}{{{\displaystyle V_{s p}(t)=V_{F i x}^{\S}(t)-E_{t}V_{F L}^{\varepsilon}(t)}}}\\ {{{\displaystyle V_{s p}(t)=C^{\ S}\sum_{i=1}^{n}e^{-r_{i}^{s}t_{i}}+Q^{\ S}~e^{-r_{i}^{s}t_{i}}-E_{t}\left[C^{\varepsilon}\sum_{i=1}^{n}e^{-r_{i}^{\varepsilon}t_{i}}+Q^{\varepsilon}~e^{-r_{n}^{\varepsilon}t_{n}}\right]}}}\end{array}
$$  

For example, in the main text Equations (36.4) to (36.6) give $C_{i}^{\mathfrak{S}}=\$3.752\mathrm{m}$ , $C_{i}^{\varepsilon}=\in2.23\mathrm{m}$ , $V_{F i x}^{\mathfrak{F}}(t)=139,586,430$ , $V_{F i x}^{\varepsilon}(t)=99,866,755$ and $V_{s p}(t)=-\ \$10,231,702$ .  

# Currency Swap as a Series of Forward Contracts  

At each payment date there is a receipt of USD, $C_{i}^{\$\S}=(s p_{0}^{\S}h^{\S}Q^{\Phi})$ and a payment of Euros, $C_{i}^{\varepsilon}=$ $(s p_{0}^{\varepsilon}h^{\varepsilon}Q^{\varepsilon})$ with the latter being worth $(F_{i}C_{i}^{\varepsilon})$ in USD, at time $t_{i}$ . The PV of these USD net cash fows discounted at USD interest rates is:  

$$
\S(C_{i}^{\Phi}-F_{i}\ C_{i}^{\varepsilon})e^{-r_{i}^{\Phi}t_{i}}
$$  

where today $t$ , the forward rate for delivery at $t_{i}$ is $\begin{array}{r}{F_{i}=E_{t}\ e^{(r^{\S}-r^{\varepsilon})t_{i}}}\end{array}$ . Hence the USD value of all net cash fows to the ‘receive-USD pay-Euros’, viewed as a strip of forward contracts is:  

$$
\left[\sum_{i=1}^{n}(C_{i}^{\S}-F_{i}{\ C}_{i}^{\varepsilon})+(Q^{\S}-F_{n}{\ Q}^{\varepsilon})\right]e^{-r_{i}^{\S}t_{i}}
$$  

It is easy to see that (36.B.4) and (36.B.6) are equivalent by substituting $\boldsymbol{F}_{i}=E_{t}~e^{(r^{\mathbb{S}}-r^{\varepsilon})t_{i}}$ in (36.B.4).  

# EXERCISES  

# Question 1  

You are a US frm with a fxed-rate bank loan in sterling (GBP) with reset dates every 6 months for the next 5 years. How can you hedge your FX position using a currency swap?  

# Question 2  

A US swap dealer has $a$ series of net (GBP) fxed-sterling payments of £10m p.a. (and USD fxed receipts), over each of the next 5 years. What are the risks to the mark-to-market value of the swap dealer’s position (apart from counterparty risk)?  

# Question 3  

Consider a receive-USD, pay-Euros currency swap with a fxed swap-rate of $s p_{E}=3\%$ p.a. in Euros and $s p_{U S}=5\%$ p.a. fxed in USDs.  

At inception the swap principals in the two currencies were $\$0$ and $\upepsilon Q=\upepsilon90\mathrm{m}$ . The tenor is annual (with an exchange having just taken place). The swap has been in existence for some time and currently has 2 more years to maturity. The current exchange rate is $S=1.0$ Euros per USD. The current term structure of interest rates is fat in the United States and Euroland and the current interest rate $r_{u s}=6\%$ p.a. while the Euro interest rate is $r_{E}=3\%$ p.a. (both continuously compounded).  

Consider the swap as a portfolio of bonds. What is the market value of the receive-USD, pay-Euros swap?  

# Question 4  

Consider a receive-USD, pay-Euros, currency swap with a fxed swap-rate of $s p_{E}=3\%$ p.a. in Euros and $s p_{U S}=5\%$ p.a. fxed in USDs (both continuously compounded).  

At inception the swap principals in the two currencies were $\$0$ and $\upepsilon Q=\upepsilon90\mathrm{m}$ . The tenor is annual (with an exchange having just taken place). The swap has been in existence for some time and currently has 2 more years to maturity. The current exchange rate is $S=1.0$ Euros per USD. The current term structure of interest rates is fat in the United States and  

Euroland and the current interest rate $r_{u s}=6\%$ p.a. while the Euro interest rate is $r_{E}=3\%$ p.a.   
(both continuously compounded).   
(a) Calculate the 1-year and 2-year forward exchange rates.   
(b) Consider the swap as a portfolio of forward contracts. What is the market value of the receive-USD, pay-Euros swap?  

# Question 5  

A currency swap for Australian dollars and US dollars, with annual payments has a remaining life of 15 months with the next two payments in 3 months and 15 months. The fxed swap rates are $s p_{A U S}=6\%$ and $s p_{U S}=4\%$ and the principals are $\mathtt{A U S50m}$ and $\mathrm{US}\$300$ .  

Th퐴e푈t푆erm structure of in푈t푆erest rates in both countries is fat with $r_{u s}=8\%$ and $r_{A u s}=$ $10\%$ (continuously compounded). The current exchange rate is $S=0.65$ USD/AUD.  

Consider the swap as a portfolio of bonds. What is the value of the swap to the party receiving USDs and paying AUDs?  

# Question 6  

A currency swap for Euros and USDs, with annual payments, has a remaining life of 2 years. The fxed swap rates are $s p_{E}=8\%$ p.a. and $s p_{U S}=11\%$ p.a. (simple interest) and the principals are $\mathsf{\epsilon}10\mathsf{m}$ and $\mathrm{US}\$100$ .  

The term structure of interest rates in both countries is fat with $r_{U S}=11\%$ and $r_{E}=$ $8\%$ (continuously compounded). The current exchange rate is $S=0.909090$ USD/Euro.  

Consider the swap as a portfolio of domestic and foreign bonds.  

What is the value of the receive-USD, pay-Euro swap?  