---
tags:
  - arbitrage_arguments
  - floating_rate_note
  - interest_rate_swaps
  - replication_portfolio
  - term_structure
aliases:
  - FRN Valuation
  - IRS Pricing
  - Swap Valuation
key_concepts:
  - FRN market value
  - FRN valuation methods
  - Replication portfolio
  - Swap cash flows
  - Swap rate calculation
---
# Pricing Interest Rate Swaps  

# Aims  

• To show that cash fows in a swap are equivalent to a replication portfolio consisting of a position in a fxed rate bond and a foating rate note (bond) (FRN).   
• To demonstrate that the swap rate is calculated by assuming that the swap must have the same value to both parties at inception – otherwise the swap would not take place. The swap rate is determined solely by the term structure of interest rates.   
• To show how arbitrage arguments can be invoked to demonstrate that the market value of an FRN is equal to the notional principal $Q$ in the FRN (a) at inception $t_{0}$ , and (b) just after, any reset date $t_{i}(i=1,2,...,n)$ .   
• To show how to value an FRN at any date $t$ (between payment dates), using two diferent methods the ‘short method’ and the ‘forward rate method’. Both methods give the same outcome for the value of the FRN at any date $t$ .   
• To show that the value of a swap at any date $t$ is the diference between the present value of the cash fows from a fxed rate bond and the present value of the cash fows from an FRN.   
• To analyse how the mark-to-market value of a swap changes through time in response to changes in interest rates and the number of remaining payments in the swap.  

A swap can be priced by considering the swap as a synthetic bond portfolio. When a pay-fxed, receive-foat interest rate swap is initiated (at $t=0$ ) each leg of the swap must have the same (present) value – otherwise both sides would not enter into the swap. This insight allows us to price the swap (i.e. determine the fxed swap rate, $s p$ ).  

Over time $(t>0)$ the (mark-to-market) value of the swap to any one party can be positive or negative, as the present value (PV) of the fxed and foating rate payments in the swap alter as interest rates change. Somewhat paradoxically the PV of the variable rate (LIBOR) payments remain relatively stable, even though these foating cash fows change over time. So it is the fxed leg of the swap which is the main source of changes in the mark-to-market value of the swap.  

# 34.1 CASH FLOWS IN A SWAP  

The payments in a receive-foat, pay-fxed swap are shown in Figure 34.1 and look exactly like a long position in an FRN and a short position in a fxed rate bond.  

If you have a ‘receive-foat, pay-fxed’ swap, on a nominal principal $Q=\$1000$ , your net cash receipts at each 6-month payment date, are $C_{F L}-C_{X}$ . These are the same cash fows that would ensue from selling a fxed rate bond with maturity value1 $\$1000$ and using the proceeds to purchase (i.e. go long) a foating rate bond (also with maturity value $\$1000$ ). Both the foating and fxed rate bond are redeemed at maturity for $Q=\$1000$ . In an interest rate swap the notional principal $Q=\$1000$ is not exchanged at maturity, so there are no cash fows from this source in the swap. But the latter is also the case if we are long the FRN and short the fxed rate bond since the two principal amounts of $\$2$ at maturity, cancel out (Figure 34.1). Hence, the net payment in the swap and the net payment from the long-short bond position are both $C_{F L}-C_{X}$ at maturity.  

The replication portfolio of being long an FRN and short a fxed rate bond (both with maturity value $Q$ ) gives exactly the same (net) cash fows as the swap. You would not enter the swap unless the present value of foating payments $V_{F L}$ equals the present value of the  

![](bfdd5078518ee9524d9f2178fbe571ac6165c6cebec55fc6e50ffbe8ec1f28cb.jpg)  

$t=0$ is outset of swap (when sp is determined) and all cash flows are paid with 6 month lag.   
The first floating cash flow is determined by the known interest rate at $\scriptstyle t=0$ .  

Dashed line indicates an uncertain cash flow.  

FIGURE 34.1 Cash fows in a receive-foat, pay-fxed swap fxed payments $V_{F i x}$ . Hence you only enter the swap if at $t=0$ , $V_{F i x}=V_{F L}$ . As we see below, this result allows us to determine the swap rate. However, frst we consider how to value the FRN.  

# 34.2 FLOATING RATE NOTE (FRN)  

An FRN is a bond with variable rate coupons based on future LIBOR rates. We can value the FRN in a number of diferent ways:  

• Using arbitrage arguments.   
• Using all forward rates to estimate all (expected) future foating cash fows. The value of the FRN is then the present value of these expected cash fows. This is the ‘forward rate method’.   
• Using a ‘short method’ to value the FRN which only uses the foating cash fow at the next payment date and the known principal Q of the FRN.  

Not surprisingly, all three methods give the same answer for the value of the FRN (at any date) and all the methods are equivalent, although it is the arbitrage argument which really underlies the other two approaches.  

It is also important to be clear about what point in time you are trying to value the FRN. When pricing a swap you need to fnd the value of the FRN at inception of the swap $\mathbf{\eta}(t=0)$ . We will see that the present value of the FRN at $t=0$ is just the principal in the FRN, which equals Q. After inception of the swap, interest rates may change (i.e. the yield curve will shift) and the market value of the FRN could increase or decrease – but we can still use the above three methods to value the FRN at $t>0$ .  

# 34.2.1 Value of an FRN at $t=0$  

An FRN is a bond whose foating (coupon) payments are adjusted in line with prevailing market interest rates, which are determined at the previous reset date. Consider a notional principle of $\$2$ and a LIBOR rate of $L_{01}$ at time $t=0$ . At $t=0$ the coupon payable at the frst reset date $t=1$ , on the foating rate bond is known and equals $C_{F L,1}=L_{01}m_{1}Q$ (where $m_{1}=d a y s/360)$ . Subsequent coupon payments on the ‘foater’ depend on future LIBOR rates at $t=1,2,3,.$ which are not known at $t=0$ . However, somewhat counter-intuitively it is shown in Appendix 34 that even though these future foating payments are uncertain, nevertheless the following propositions are true:  

# Proposition 1  

At inception $t=0$ , all future receipts on an FRN have a present value equal to Q  

Proposition 2 Immediately after any reset date $t_{i},$ all future foating receipts have a present value of Q  

Proposition 1 allows us to price the swap at inception, $t=0$ . Proposition 2 helps in valuing the FRN (and hence the swap) after inception (i.e. $t>0$ ). Hence the value of an FRN over time is like the stylised pattern in Figure 34.2 – its value equals $Q$ at $t=0$ , it also equals Q just after any of the reset dates and at the maturity date, $t=n$ . Between reset dates, the market value of the FRN can deviate from its notional value $Q$ (Figure 34.2). But as interest rates generally do not change drastically over short periods, the value of the FRN does not deviate too far from $Q$ , between reset dates.  

A semi-intuitive way of showing that the (present) value of an FRN equals $Q$ at $t=0$ and just after each payment date is to value the FRN using current forward rates and to recursively calculate its value, as we move back in time from the fnal payment date (Figure 34.3).  

For simplicity consider a 3-period FRN, which pays annual coupons (and we use compound rates). The forward rates are all known at $t=0$ . (They are calculated from the known spot rates at $t=0$ ). The expected fnal foating payment is $C_{F L,3}=(1+f_{23})Q$ but this has an expected present value at $t=2$ of $P V_{2}=(1+f_{23})Q/(1+f_{23})=Q$ . Hence at $t=2$ , the present value of the cash fow at $t=3$ plus the cash fow at $t=2$ is $P V_{2}+C_{F L,2}=Q(1+f_{12})$ – the latter has a present value at $t=1$ of $P V_{1}=(1+f_{12})Q/(1+f_{12})=Q$ . We have now shown that at $t=1$ , the present value of both the future cash fows at $t=2$ and $t=3$ are worth $Q$ in total. At $t=1$ we also receive a cash fow $C_{F L,1}=r_{1}Q$ , so at $t=1$ all (current and future) cash fows are worth $Q+r_{1}Q$ – but these have a present value at $t=0$ of $(Q+r_{1}Q)/(1+r_{1})=Q.$ . Hence the value of all the future cash fows $t=1,2,3$ from the FRN have a value today (at $t=0$ ) of Q. Also note from the above that just after the foating rate payment dates at $t=1$ and $t=2$ , the (present) value of any remaining future cash fows, is also equal to Q. (See Appendix 34 for a formal proof of this using arbitrage arguments.)  

![](c4dd16f6cccae3de19465174a09a108fcc01836c9eb53d9f3db3952a5f4eeadb.jpg)  
FIGURE 34.3 FRN, expected cash fows  

![](2d3032eb9cbe90561a4acbbca6c14dd7eca38f74b1a979a5decad03a93efe242.jpg)  
FIGURE 34.2 Value of a FRN over time  

# 34.3 PRICING A SWAP: SHORT METHOD  

To price a plain vanilla swap at the outset $(t=0$ means fnding the fxed rate $s p$ which makes the (present) value of the fxed rate bond equal to the (present) value of the FRN – or what is the same thing, that the fxed-for-foating swap has zero initial value.  

For example, suppose you are a swap dealer who has to fx the swap rate $s p$ for a ‘new’ fxed for foating (LIBOR) swap with a notional principal of $\$2$ . Let $C_{X,i}=(s p h_{i}Q)$ be the payment each period in the fxed leg of the swap and $h_{i}$ the tenor in the fxed-leg (e.g. 180/360 or 181/360 etc.). The discount factors are $d_{i}=1/[1+r_{i}.t_{i}]$ where $r_{i}=L I B O R_{i}$ $t_{i}=d a y s_{i}/360$ and $d a y s_{i}$ is the actual number of days from $t_{0}$ to $t_{i}$ .2 The (present) value of the fxed leg at $t=0$ is:  

$$
\begin{array}{l}{{V_{F i x}=C_{X,1}d_{1}+C_{X,2}d_{2}+C_{X,3}d_{3}+\ldots\ldots\ldots+C_{X,n}d_{n}+Q d_{n}}}\\ {{V_{F i x}=Q\left[s p\displaystyle\sum_{i=1}^{n}h_{i}d_{i}+d_{n}\right]}}\end{array}
$$  

Note that if the notional principal in the swap is $\$1$ , then the term in square brackets is the ‘present value of the fxed payments in an interest rate swap, with $\$1$ notional principal’. Now we make use of our above proposition that the market value at $t_{0}$ of all the future foating (LIBOR) cash fows are today equal to the notional principal, so $V_{F L}(t_{0})=Q.$ The swap rate is that value of $s p$ for which $V_{F L}=V_{F i x}$ . Hence the swap rate is the solution to:  

$$
Q=Q\left[s p\sum_{i=1}^{n}h_{i}d_{i}+d_{n}\right]
$$  

The swap rate depends only on the term structure of spot rates at $t=0$ (and not on $Q$ ):  

$$
s p_{n}={\frac{1-d_{n}}{\displaystyle\sum_{i=1}^{n}h_{i}d_{i}}}
$$  

This is the swap rate for an $n$ -period swap. There are diferent quoted swap rates for swaps with diferent maturities. The ‘swap spread’ is often defned as the diference between the swap rate and the yield to maturity $(y_{n})$ of an $n$ -period government bond, so the ‘swap spread’ $=s p_{n}-y_{n}$ . A plot of the swap rate $s p_{n}$ against $n$ is often referred to as the ‘swap rate curve’.  

Swap rates generally lie slightly above T-bond yields because swap rates refect the creditworthiness of major banks that provide swaps (and also refect liquidity in the market). In fact swap rates rather than government bond rates are often used as benchmark rates for pricing assets such as corporate bonds, mortgages etc., because the swaps’ market is so liquid and virtually risk free. If the tenor $h$ in the fxed leg of the swap is constant, then  

$$
s p_{n}=(1/h)\frac{(1-d_{n})}{\displaystyle\sum_{i=1}^{n}d_{i}}
$$  

Table 34.1 shows the calculation of the (4-year) swap rate $s p_{n}=5.3579\%$ p.a. from the spot yield curve on 15 March-01, using the above formula (with $h=180/360$ for all periods in the fxed-leg of the swap).3  

The discount rates are calculated as follows. For example, between 15 March-01 and 15 September-02 $\left(t=3\right)$ there are 549 days and the quoted spot rate (at $t=0$ ) is $r_{3}=5.36\%$ p.a., so the discount factor is:  

$$
d_{3}=1/[1+r_{3}.t_{3}]=1/[1+0.0536(549/360)]=0.924437
$$  

How can we check that $s p=5.3579\%$ is the correct swap rate? The PV of the fxed cash fows using $s p=5.3579\%$ should equal the notional principal in the swap of $\$100,000$ . We have $C_{X}=(s p.h.Q)=0.053579(180/360)\S100\mathrm{m}=\S2,367,4976$ (payable every 6 months) and using the discount factors in Table 34.1:  

$$
V_{F i x}=C_{X}\left[\sum_{i=1}^{n}d_{i}\right]+Q d_{n}=\S100,000
$$  

So, using $s p=5.3579\%$ ensures that $V_{F i x}=\S100,000=V_{F L}$ which is as expected. If the swap dealer is a fxed rate receiver (and foating rate payer) she will set the actual swap rate above $5.3579\%$ to refect the transactions cost of hedging her swaps book and the credit risk of the counterparty in the swap.  

Today is 15 March-01   
Notional principal: 100,000   
Days in year (swap convention): 360   
Days to 1st floating reset date: 184   
6-month LIBOR on 15 March-01: $5.15\%$  

TABLE 34.1 Calculation of swap rate   


<html><body><table><tr><td>Date</td><td>Days </td><td>Cum. days</td><td>Spot rates LIBOR</td><td>Discount factors LIBOR</td><td>Forward rates LIBOR</td><td>Floating cash flows</td><td>PV (Floating cash flows)</td><td>d*f*m</td></tr><tr><td>15-Mar-01</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>15-Sep-01</td><td>184</td><td>184</td><td>5.15</td><td>0.9744</td><td>5.1500</td><td>2,632.2222</td><td>2,564.7133</td><td>0.0256</td></tr><tr><td>15-Mar-02</td><td>181</td><td>365</td><td>5.27</td><td>0.9493</td><td>5.2537</td><td>2,641.4436</td><td>2,507.4648</td><td>0.0251</td></tr><tr><td>15-Sep-02</td><td>184</td><td>549</td><td>5.36</td><td>0.9244</td><td>5.2576</td><td>2,687.2221</td><td>2,484.1663</td><td>0.0248</td></tr><tr><td>15-Mar-03</td><td>181</td><td>730</td><td>5.45</td><td>0.9005</td><td>5.2905</td><td>2,659.9635</td><td>2,395.2546</td><td>0.0240</td></tr><tr><td>15-Sep-03</td><td>184</td><td>914</td><td>5.54</td><td>0.8767</td><td>5.3102</td><td>2,714.1088</td><td>2,379.4313</td><td>0.0238</td></tr><tr><td>15-Mar-04</td><td>182</td><td>1096</td><td>5.65</td><td>0.8532</td><td>5.4376</td><td>102,749.0067</td><td>87,668.9698</td><td>0.0235</td></tr><tr><td></td><td></td><td>1.Swap rate</td><td></td><td>0.0536</td><td></td><td>2. Swap rate</td><td></td><td>0.0536</td></tr><tr><td></td><td></td><td>PV fixed CF</td><td></td><td>100,000</td><td></td><td>PV floating CF</td><td></td><td>100,000</td></tr></table></body></html>  

# 34.4 PRICING A SWAP: FORWARD RATE METHOD  

When using the ‘forward rate method’ to determine the swap rate we use all the forward rates to determine the present value of the foating rate payments $V_{F L}$ , set this equal to the present value of the fxed rate payments $V_{F i x}$ and then solve for the unknown swap rate, $s p_{n}$ . Of course, we already know that the present value of the foating payments is equal to $Q$ but the ‘forward rate method’ is useful in pricing other kinds of swap which we meet later – so we introduce the method here.  

The foating coupon payments are $C_{F L,i}=f_{i}m_{i}Q$ where the forward rates $f_{i}$ apply to the period between $(t_{i-1},t_{i})$ . Therefore $f_{1}=L_{01}$ is actually the known LIBOR rate fxed at $t_{0}$ for the period $(t_{0},t_{1})$ . Also $m_{i}=d a y s_{i}/360$ and $d a y s_{i}=$ actual number of days between each repayment date. Spot rates are used to calculate forward rates. For example, the forward rate $f_{2}$ applicable to the period $(t_{1},t_{2})$ is derived from the two spot rates $r_{1},r_{2}$ using the arbitrage relationship:  

$$
(1+r_{1}m_{1})(1+f_{2}m_{12})=(1+r_{2}m_{2}),m_{12}=d a y s_{12}/360
$$  

For example, from Table 34.1 we see that $m_{1}=184$ , $m_{2}=184+181=365$ , $m_{12}=181$ , $r_{1}=5.15\%$ and $r_{2}=5.27\%$ . Hence $f_{2}=\{[1+0.0527(365/360)]/[1+0.0515$ $(184/360)]-1\}$ $360/181=0.052537.$ 4 The present value of all the foating payments, $C_{F L,i}=f_{i}m_{i}Q$ at $t=0$ is:  

$$
V_{F L}(t_{0})=\sum_{i=1}^{n}C_{F L,i}d_{i}+Q d_{n}=Q\left[\sum_{i=1}^{n}f_{i}m_{i}d_{i}+d_{n}\right]
$$  

and from Table 34.2 this gives $V_{F L}(t_{0})=\mathbb{\$100,000}$ as expected, since we already know that at inception of the swap, the value of the foating leg equals $Q$ . The PV of the fxed cash fows is $C_{X,i}=s p.h_{i}.Q$ hence, as before:  

$$
V_{F i x}=\left[\sum_{i=1}^{n}C_{X,i}d_{i}+Q d_{n}\right]=Q\left[s p\sum_{i=1}^{n}h_{i}d_{i}+d_{n}\right]
$$  

TABLE 34.2 New spot rates and discount factors  

<html><body><table><tr><td colspan="8">Today is 15 June-01 Notional principal: 100,000 Days in year (swap convention): 360 Days to 1st floating reset date: 184 6-month LIBOR on 15 March-01: 5.15%</td></tr><tr><td colspan="8">Swap rate (set on 15 March-01): 5.36% Date Days Cum. New Discount Fixed CF, PV days LIBOR factors sp = 0.0536 fixed rate LIBOR cash</td></tr><tr><td>15 Jun-01 15-Jun-01</td><td></td><td></td><td></td><td></td><td>flows</td><td>flows)</td><td></td><td> flows</td></tr><tr><td colspan="9"></td></tr><tr><td>15-Sep-01 15-Mar-02</td><td>92</td><td>92</td><td>6.15</td><td>0.9845</td><td>2,679</td><td>2,637</td><td>5.1500</td><td>2,632 2,591</td></tr><tr><td>15-Sep-02</td><td>181</td><td>273</td><td>6.27</td><td>0.9546 0.9253</td><td>2,679 2,679</td><td>2,557 2,479</td><td>6.2330 3,134 6.1988</td><td>2,992</td></tr><tr><td></td><td>184</td><td>457</td><td>6.36 6.45</td><td>0.8974</td><td>2,679</td><td>2,404</td><td>3,168</td><td>2,932</td></tr><tr><td>15-Mar-03</td><td>181</td><td>638</td><td>6.54</td><td>0.8701</td><td>2,679</td><td>6.1784</td><td>3,106 3,143</td><td>2,788</td></tr><tr><td>15-Sep-03</td><td>184</td><td>822</td><td>6.65</td><td>0.8436</td><td>102,679</td><td>2,331 86,615</td><td>6.1492 6.2182</td><td>2,735</td></tr><tr><td>15-Mar-04</td><td>182</td><td>1004</td><td></td><td></td><td></td><td></td><td>3,144</td><td>87,007</td></tr><tr><td colspan="7">PV fixed CF 99,024</td><td colspan="2">PV floating CF</td></tr><tr><td colspan="7">Value 'receive-float, pay-fixed' swap (15 June) 2,020</td><td colspan="2"></td></tr></table></body></html>  

Equating $V_{F i x}$ and $V_{F L}$ and rearranging, we obtain an expression for the swap rate using the ‘forward rate method’:  

$$
s p_{n}={\frac{\displaystyle\sum_{i=1}^{n}d_{i}f_{i}m_{i}}{\displaystyle\sum_{i=1}^{n}h_{i}d_{i}}}
$$  

The swap rate calculated using (34.11) is shown as ‘2. Swap rate’ in Table 34.1 and naturally it gives the same numerical value of $5.36\%$ as that derived in Equation (34.5), which uses only the term structure of spot (or discount) rates.  

# 34.5 MARKET VALUE OF A SWAP  

At inception of the swap on 15 March-01, the value of the swap is $V_{s p}(t_{0})=V_{F L}-V_{F i x}=0$ by construction. We now want to calculate the mark-to-market value of the swap sometime after its inception. The value of the swap changes over time as interest rates change and as the number of cash fows remaining changes. The value of a receive-foat pay-fxed swap at $t>0$ is the diference between the value of the FRN (foating leg) and the fxed coupon bond:  

$$
V_{s p}(t)=V_{F L}(t)-V_{F i x}(t)
$$  

Suppose on 15 June (i.e. after 3 months), spot rates (and hence forward rates) have all increased – what is the new value of the swap? To value the swap we need to fnd the new (present) values of the FRN and the fxed-rate bond, using the new higher spot rates. We begin by valuing the FRN and we can use two diferent methods:  

(a) ‘short method’ – use only the next LIBOR cash fow (plus $\boldsymbol{Q}$ ) (b) ‘forward rate method’ – use forward rates as forecasts of all future LIBOR cash fows.  

# 34.5.1 Value of FRN at $t>0$ (‘Short Method’)  

Suppose we are trying to value the swap at $t$ (15 June), between $t=0$ (15 March) and $t=1$ (15 September-01) – Figure 34.4. From our earlier analysis we know that the present value of the foating leg equals $Q$ immediately after any payment date. Between payment dates an FRN can have a value diferent to $Q$ .  

The foating cash fow at $t=1$ (15 September) is known and depends on the LIBOR rate $L_{0,1}$ which was fxed on 15 March (at $t=0$ and which pays out at $t=1\dot{}$ ). This cash fow is:  

$$
C_{F L,1}=Q[L_{0,1}(d a y s_{0,1}/360)]=\S100\mathrm{m}(0.0515)(184/360)=\S2,632
$$  

Using proposition 2, the value of all future LIBOR cash fows accruing after $t_{1}$ (that is $C_{F L,2},C_{F L,3},\dots C_{F L,n}$ plus the fnal payment of $Q$ at $t_{n}$ ), have a PV at $t=1$ of $Q$ . Hence the  

![](e868def553c3f126656728313d47c12e034f20962d0d6609420f0cd138678dcc.jpg)  
FIGURE 34.4 Value of swap at $t$ , receive-foat, pay-fxed  

value of the FRN at $t$ depends only on the present value of the next foating LIBOR payment $C_{F L,1}$ plus Q. The new spot rate applicable from 15 June to 15 September (92 days) is $r_{1}^{*}=6.15\%$ , so the new discount rate $d_{1}^{*}=1/(1+0.0615(92/360))=0.984526525$ (Table 34.2).  

Hence the (present) value of the FRN on 15 June is:  

$$
V_{F L}(t)=(C_{F L,1}+Q)d_{1}^{*}=(\S2,632+\S100,000)\ 0.984526525=\S101,044
$$  

At inception of the swap (15 March) the present value of the foating rate payments was $\$100,000$ . Although the spot-LIBOR rate $r_{1}^{\ast}$ has increased and the next cash fow of $\$2,632$ is unchanged, nevertheless the value of the FRN on 15 June has increased. This is because you now have less time to wait (92 days) for the frst payment on 15 September (compared with 184 days at inception of the swap on 15 March-01).  

The above formula with minor changes in notation applies to the value of the FRN between any two payment dates – its value depends only on the present value of the next known foating LIBOR payment $C_{F L}$ , plus $Q$ .  

# 34.5.2 Value of FRN at $t>0$ (‘Forward Rate Method’)  

The value of the FRN at $t\left(15\mathrm{June}\right)$ is the PV of all future LIBOR cash fows after time $t.$ We can value the FRN by using the new forward rates at $t$ to provide an estimate of expected future cash fows and discount these cash fows back to time $t$ , using the new spot rates determined at t. This is the ‘forward rate method’.  

The value of the FRN between inception and the frst payment date $(t_{0}<t<t_{1})$ depends on: (i) the PV of the next LIBOR payment $C_{F L,1}=Q.L_{0,1}(d a y s_{0,1}/360)$ which was fxed at $t=0$ ; plus (ii) PV of all the future foating rate payments $C_{F L,i}=f_{i}m_{i}Q_{i}$ at payment dates $t_{i}\geq2(i=2,...n)$ ; plus (iii) the PV of $Q$ . The ‘new’ interest rates at $t$ are higher (Table 34.2) than at $t=0$ . All spot rates are now measured from time $t$ and hence we have ‘new’ discount factors and new forward rates:  

$$
V_{F L}(t)=\left[\sum_{i=1}^{n}C_{F L,i}^{*}d_{i}^{*}+Q d_{n}^{*}\right]=Q\left[\sum_{i=1}^{n}f_{i}^{*}m_{i}^{*}d_{i}^{*}+d_{n}^{*}\right]=\S101,044
$$  

where $d_{i}^{*}=1/[1+r_{i}^{*}t_{i}^{*}],~r_{i}^{*}=L I B O R_{t,i}~t_{i}^{*}=d a y s_{t,i}/360$ , so the discount factors apply to the period from today $t$ to the remaining payment dates, $t_{i}$ . The PV of the FRN on 15 June is $V_{F L}(t)=\$101,044$ not surprisingly this is the same value as found above using the ‘short method’.  

For more ‘exotic’ swaps than the plain vanilla swap considered here (and discussed in Chapter 35), we often cannot use the ‘short method’ and we need to value the foating leg using ‘the forward rate method’.  

# 34.5.3 Value of Fixed Leg at $t>0$  

Now let’s value the fxed leg at $t$ . The fxed payments are $C_{X}=(s p.h.Q)=0.0536$ 180 360 $\$100,000=82,679$ . The only change to note is that discount rates now use the new spot rates at time $t$ so that $t_{i}=d a y s_{t,i}/360$ where $d a y s_{t,i}$ is the actual number of days from $t$ to $t_{i}$ , that is from 15 June to the other reset dates (Figure 34.4), hence:  

$$
d_{i}^{*}=1/[1+r_{i}^{*}.t_{i}^{*}],r_{i}^{*}=L I B O R_{t,i},t_{i}^{*}=d a y s_{t,i}/360
$$  

The value of the fxed leg on 15 June-01 is calculated in Table 34.2:  

$$
V_{F i x}(t)=C_{X}\sum_{i=1}^{n}d_{i}^{*}+d_{n}^{*}=\S99,024
$$  

The PV of the fxed leg has fallen from $\$100,000$ (at inception on 15 March) to $\$99,024$ (on 15 June) because of the rise in spot rates which alters the discount factors $d_{i}^{*}$ . The value of a receive-foat, pay-fxed swap at time $t$ is therefore:  

$$
V_{s p}(t)=V_{F L}(t)-V_{F i x}(t)=\S101,044-\S99,024=\S2,020
$$  

The rise in interest rates between 15 March and 15 June results in an increase in value of the receive-foating LIBOR-leg of the swap and a fall in the value of the ‘pay-fxed’ leg of the swap – so the ‘receive-foat pay-fxed swap’ has increased in value and is worth $\$2,020$ .  

# 34.6 SWAP DELTA AND PVBP  

In the above example the value of the swap changed because of (i) a change in the yield curve and (ii) because we moved through time and revalued the swap on 15 June. If we had valued the swap on, say, 15 April two years later and interest rates had not changed, the swap value would have changed simply because it has only two further cash fows remaining.  

It is useful when hedging a swap to separate out the efect of interest rate changes and the ‘passage of time’, on the market value of the swap. To do so we consider what happens to the (present) value of the swap when all interest rates increase by the same small amount over a small time interval (say one day). If the change in interest rates is taken to be 1 bp then the resulting change in the value of the swap is known as the swap delta. The latter concept is useful when hedging a position in swaps – which we discuss in Chapter 39. The swap delta is a similar concept to the delta of an option. The value of the swap on 15 June (using the ‘short method’) gives:  

$$
V_{s p}(t)=Q[1+L_{0,1}(d a y s_{0,1}/360)]d_{1}^{*}-\left[C_{X}\sum_{i=1}^{n}d_{i}^{*}+Q d_{n}^{*}\right]=\S2.020
$$  

where  

$$
d_{i}^{*}=1/[1+r_{i}^{*}.t_{i}^{*}],r_{i}^{*}=L I B O R_{t,i},t_{i}^{*}=d a y s_{t,i}/360.
$$  

What will happen to the value of the swap if all interest rates rise by 1 bp, over the next day? Higher spot and hence forward rates lead to an increase in the expected cash fows from the FRN and no change in the cash fows in the fxed leg, hence the net cash receipts of the receive-foat pay-fxed swap, increase. But does this imply that the present value of these net cash fows increases?  

All future foating LIBOR payments (except that at the next payment date) will increase but so will the discount rates applied to these higher foating cash fows, and in present value terms these two efects are largely ofsetting so the value of the foating leg of the swap does not vary much (see Figure 34.2). But how much is this ofset? Using the ‘short method’ we can easily see what’s happening to the value of the FRN:  

If interest rates increase, $V_{F L}(t)$ will fall the next day but not by much, as it only falls because of the increase in the (single) short-term LIBOR interest rate which implies $d_{1}^{*}$ is smaller. On the other hand, although the fxed dollar payments each period do not change, there may be many of these, so their present value falls by a relatively large amount, after a rise in all spot interest rates. But as a fxed rate payer you are better of when the PV of your ‘debt’ is lower. Hence:  

A rise in interest rates will increase the present value of a ‘receive-foat, pay-fxed’ swap. Hence, a ‘receive-foat, pay-fxed swap’ has a positive delta.  

Another way of seeing how the value of a long maturity ‘receive-foat pay-fxed’ swap changes after a rise in interest rates is to note that the foating-leg (FRN) has a small duration $D_{F L}$ and the fxed-leg has a large duration, $D_{F i x}$ . For each leg of the swap we have $d V=$ $-V(D)d r$ , hence for a parallel shift in the yield curve:  

$$
d V_{s p}=d V_{F L}-d V_{F i x}=-(V_{F L}D_{F L}+V_{F i x}D_{F i x})d r
$$  

Since $D_{F L}<D_{F i x}$ then a rise in interest rates (usually) increases the value of the receive-foat pay-fxed swap.  

# 34.7 SUMMARY  

• A plain vanilla interest rate swap involves one party exchanging a series of fxed cash fows for cash fows determined by a foating rate (LIBOR). The notional principal in the swap is not exchanged.   
• Cash fows in a ‘receive-foat, pay-fxed swap’ are equivalent to taking a long position in an FRN and a short position in a fxed rate bond. At inception, the two parties in the swap will not enter the swap unless the value of the fxed bond equals the value of the foating bond. Hence the swap rate is calculated by making the fxed leg of the swap equal to the value of the foating leg, at inception of the swap.   
• The swap rate is determined by the term structure of spot rates, at inception of the swap.   
• After a swap has been initiated, the value of the swap may become positive or negative (to one of the parties). The mark-to-market value of a swap at any time is the present value of the remaining future net cash fows in the swap.   
• The mark-to-market value of a swap changes over time as spot interest rates (and hence forward rates) change and because the swap will have less cash fows outstanding. For a long-dated swap, it is the fxed-leg rather than the foating-leg whose present value changes by a large amount, as interest rates change.   
• The change in the (present) value of a swap position after a 1 basis point change in all interest rates is known as the swap delta (or the present value of a basis point, PVBP). The swap delta is a useful concept when swap dealers try to hedge the whole of their swaps book.  

# APPENDIX 34: VALUE OF AN FRN USING ARBITRAGE  

We wish to determine the present value $V_{F L}$ of all future foating rate payments on an FRN at any reset date $t_{i}$ $(i=0,1,2,\ldots n)$ . The FRN has a notional (face) value $Q$ , which is fxed. Using an arbitrage argument, we show that $V_{F L}$ must equal $Q$ immediately after any reset date, including at $t_{0}$ when the swap is initiated. (Note that this analysis says nothing about the value of the FRN when we are between reset/payment dates.)  

Suppose that immediately after any reset/payment date $t_{i}$ we have $V_{F L}(t_{i})>Q$ . Consider the following arbitrage strategy:  

1. Sell (short) an FRN at $V_{F L}(t_{i})$ and invest $\$2$ at LIBOR (in a risk-free bank deposit). Net cash infow at $t_{i}$ is $V_{F L}(t_{i})-Q>0$ .   
2. At the next payment date use the LIBOR receipts from the bank deposit to pay LIBOR on the short FRN. Roll over the principal $Q$ of the deposit. Repeat this process until $t_{n-1}$ . Net cash infow 0 at each payment date up to tn 1.   
3. At $t_{n}$ use the LIBOR interest from the deposit account to pay LIBOR on the FRN and use the principal $\$2$ from the deposit account to pay the principal on the FRN.  

Net cash infow $=0$ .  

Hence, if $V_{F L}(t_{i})>Q$ at any payment date (including $t_{0}$ ) there is a risk-free arbitrage proft to be made, since you receive a net cash infow at $t_{i}$ and no net cash outfows after that date. This arbitrage strategy will result in bond arbitrageurs selling FRNs at time $t_{i}$ , which will push the market price of the FRN down, until its market value equals $Q$ (its par value), at which point arbitrage trades cease and equilibrium is restored. But the market price of the FRN is just the market’s valuation of the future cash fows from the FRN so $V_{F L}(t_{i})=Q$ . Since the arbitrage is riskless, we expect $V_{F L}(t_{i})=Q$ at all future payment/reset dates $t_{i}(i=1,2,...n)$ , and today at t0.  

# EXERCISES  

# Question 1  

What are the main causes of a change in the mark-to-market value of a 20-year pay-fxed, receive-foating (plain vanilla) interest rate swap? Explain.  

# Question 2  

From a swap dealer’s viewpoint, explain a ‘matched’ 20-year swap.  

# Question 3  

Today a swap dealer agrees a receive-fxed, pay-foating 10-year interest rate swap on a notional principal of $\$100$ . What might cause the swap to have a positive value to the swap dealer, in 3 months’ time? Explain.  

# Question 4  

A swap dealer has to decide the swap rate to charge in a ‘new’ fxed-for-foating (LIBOR) swap on a notional principal of $Q=\$25m$ . The swap’s maturity is 2 years, with payments every 180 days. The term structure of LIBOR rates is $12\%$ p.a. over 6 months, $12.25\%$ p.a. over  

1 year, $12.75\%$ p.a. over 18 months and $13.02\%$ p.a. over 2 years (all continuously compounded).   
Assume there are 360 days in a year. Calculate the swap rate.   
Briefy explain what factors determine the quoted swap rate.  

# Question 5  

At inception, the swap rate is $s p=6\%$ (simple rate) on a plain vanilla $Q=\$1000$ swap.  

The previous reset date was 15 January. The 6-month LIBOR rate on 15 January was $3.6\%$ p.a. (simple rate). The tenor in the swap is 6 months.  

It is now 15 March. The next (LIBOR) reset date is 15 July and the swap matures on the next 15 January (in 10 months’ time).  

Assume 6 months equals $^1/_{2}$ year etc. and the yield curve is ‘fat’ at $5\%$ p.a. (continuously compounded). Forward rates to calculate foating cash fows in the swap are ‘simple rates’, not continuously compounded.  

Calculate the mark-to-market value of a receive-fxed, pay-foating swap (on 15 March) by considering the swap as a series of forward contracts.  

# Question 6  

A $Q=\$1000$ notional, interest rate swap has a remaining life of 10 months. Under the terms of the swap, 6-month LIBOR (foating) is exchanged for a fxed swap rate, $s p=12\%$ p.a.  

The yield curve is currently ‘fat’ at $10\%$ p.a. (continuously compounded), which is equivalent to $10.254\%$ p.a. (simple interest).  

The 6-month LIBOR rate, 2 months ago, at the previous ‘reset date’ was $9.6\%$ p.a. (simple rate) and the next payment dates are in 4 months and 10 months.  

Consider the swap as a combination of a fxed and a foating bond and calculate the current value of the swap, to the party paying foating.  

# Question 7  

It is immediately after a payment date on swap with a notional principal of $\$0$ (annual payments). The swap rate $s p=10\%$ . The swap is a receive-fxed, pay-foating interest rate swap with two remaining payment dates.  

The current spot rates for the two periods are $r_{1}=5\%$ p.a. and $r_{2}=5.5\%$ p.a., respectively and the forward rate is $f_{12}=6.0\%$ p.a. (compound rates).  

Consider the swap as a bond portfolio and calculate the value of the swap to the party receiving-fxed.  