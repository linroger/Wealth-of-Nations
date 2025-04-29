---
tags:
  - comparative_advantage
  - interest_rate_swaps
  - libor
  - otc_instruments
  - plain_vanilla_swaps
  - swap_dealers
aliases:
  - Fixed-for-Floating Swap
  - IRS
  - Interest Rate Swap
  - Swap
  - Swap Agreements
key_concepts:
  - Cash flow determination
  - Convert uncertain cash flows
  - Principle of comparative advantage
  - Privately arranged contracts
  - Role of swap dealers
---
# SWAPS  

# Interest Rate Swaps  

# Aims  

• To show how plain vanilla interest rate swaps can be used to convert uncertain future foating-rate interest cash fows into known fxed-rate cash fows (or vice versa).   
• To examine the role of swap dealers, settlement procedures, pricing schedules and the termination of swap agreements.   
• To demonstrate how cash payofs in the swap are determined.   
• To demonstrate the principle of comparative advantage – the source of gains in a swap.  

Swaps are privately arranged contracts (i.e. OTC instruments) in which parties agree to exchange cash fows in the future according to a prearranged formula. Swap contracts originated in about 1981. The largest market is in interest rate swaps but currency swaps are also widely used.  

The most common type of interest rate swap is a plain vanilla fxed-for-foating rate swap. Here one party agrees to make a series of fxed interest payments to the counterparty, and to receive a series of payments based on a variable (foating) interest rate (LIBOR). The interest payments are based on a stated notional principal of say $Q=\$1000$ , but only the interest payments are exchanged each period, not the principal value – hence the use of ‘notional’. The payment dates, day-count convention, maturity of the swap, and the foating rate to be used (usually LIBOR) are also determined at the outset of the contract. In a plain vanilla swap ‘the fxed rate payer’ knows exactly what the (dollar) interest payments will be on every payment date but the foating rate payer does not.  

Why are swaps so popular? The frst reason is that swaps can be used to reduce the cost of borrowing. Suppose Microsoft wants a fxed-rate loan with a principal $Q=\$1000$ . Rather than  

Microsoft currently has floating rate loan from Citibank at LIBOR $+0.5\%$ with principal $\$100m$ , to run for a further 5 years. Interest rate resets are annual.  

![](6f3c3932511b56ce58471bf79f431549126090d02216857a67945aa42826aba0.jpg)  
FIGURE 33.1 Interest rate swap  

Microsoft has a ‘receive floating – pay fixed swap’ After the swap: Net payment for Microsoft $=0.5\%+6\%=6.5\%$ $[=$ fixed)  

taking out a fxed-rate loan directly with Citibank at $6.6\%$ p.a. (say), Microsoft may end up paying a lower fxed payment, if it obtains its fxed-rate loan indirectly.  

Surprisingly, Microsoft frst takes out what it does not want – a foating-rate loan at $\mathrm{LIBOR}{+}0.5\%$ with Citibank (Figure 33.1). Then Microsoft goes to a swap dealer (e.g. Goldman Sachs) and agrees to swap LIBOR receipts for fxed rate payments. Microsoft agrees to receive foating rate (LIBOR) from Goldman and to pay Goldman a fxed rate of say $6\%$ , on a (notional) principal of $\$1000$ in the swap. The fxed rate $s p=6\%$ is the swap rate.  

The LIBOR receipts from Goldman are simply passed on to Citibank. Efectively Microsoft now has a fxed-rate loan at $6.5\%$ (rather than at $6.6\%$ , if Microsoft had gone directly for a fxed rate loan from Citibank). The lower fxed loan rate via the swap occurs because of the principle of comparative advantage (see Appendix 33). It probably arises because of ‘frictions’ in credit markets. There may be an element of oligopoly amongst lending institutions or the market between diferent banks in diferent countries is fragmented, so that credit spreads on direct borrowing at fxed rates are relatively high. Swaps may then provide a method of circumventing this problem, providing a net gain to all parties in the swap (assuming no one defaults).  

It may be immediately obvious to some readers that an interest rate swap is (analytically) nothing more than a series of forward rate agreements (FRAs), to exchange cash fows based on a foating interest rate in exchange for cash fows at a fxed rate, at various predetermined dates in the future. Since the swap is equivalent to a series of FRAs (or interest rate forward contracts) then what swaps ofer is lower transactions costs than a strip of FRAs. Indeed, although the market in FRAs is liquid (competitive) at short horizons of up to 1–2 years, the swaps market is liquid at both short and long horizons out to 20–30 years.  

The intermediaries in a swap transaction are usually banks who act as swap dealers. They are usually members of the International Swaps and Derivatives Association (ISDA) which provides some standardisation in swap agreements via its master swap agreement which can then be adapted where necessary, to accommodate most customer requirements.  

Swap dealers make profts via the bid–ask spread on the (fxed) swap rate and might also charge a small brokerage fee. Swap dealers take on many diferent swaps from many diferent counterparties but they will generally end up with a net open position (i.e. net payments or receipts at a foating rate). They usually hedge this position using interest rate (Eurodollar) futures contracts (and sometimes interest rate options).  

# 33.1 USING INTEREST RATE SWAPS  

Another reason you might use an interest rate swap is to remove existing interest rate risk. Suppose Microsoft has an existing long-term bank loan with Citibank which has been running for some time, on which it pays $\mathrm{LIBOR}{+}0.5\%$ . Assume Microsoft now becomes worried about rising interest rates in the future, so it wants to switch to a fxed rate loan.  

It could go back to Citibank and negotiate to switch from a foating rate loan to one where it pays known fxed (dollar) interest payments every year. But renegotiating loan contracts for large corporations is a tricky and expensive proposition – think of all those lawyers’ fees when the covenants in the loan contract are altered, not to mention lengthy negotiations before the new loan is issued. It is easier and cheaper to keep the existing foating rate loan with Citibank but undertake a swap. This will result in Microsoft ending up with what it wants – namely, to have fxed known dollar interest payments. We have already dealt with this situation in Figure 33.1.  

By using the swap, Microsoft has transformed an initial foating rate loan with Citibank into fxed rate payments at $6.5\%$ . Microsoft efectively now has the equivalent of a fxed rate loan. If the maturity of the swap ends when the bank loan terminates and is for the same principal amount, and tenor, then Microsoft will have known fxed interest payments over the rest of the life of the loan. In a plain vanilla interest rate swap the foating rate is usually ‘LIBOR-fat’ (i.e. without a spread) and the swap dealer will then determine the appropriate fxed rate to charge in the swap.  

Next, let us see how a swap can be used to reduce interest rate risk for a fnancial intermediary like a bank or Savings and Loan Association (‘Building Society’ in the UK and Savings Bank in Europe), so that the fnancial intermediary can ‘lock in’ a proft over future years. Assume Silverado bank has fxed rate receipts from its existing loans or housing mortgages, at say $12\%$ , but raises much of its fnance in the form of short-term foating rate deposits, at say LIBOR- $1\%$ (Figure 33.2). Income paid on deposits varies as market interest rates vary and this is a source of risk for the fnancial intermediary.  

If the deposit rate is LIBOR- $1\%$ and LIBOR currently equals $11\%$ the bank pays out $10\%$ to depositors. But if its fxed rate mortgages and loans earn $12\%$ , the fnancial intermediary currently earns a proft (maturity spread) of $2\%$ p.a. However, the danger is that if LIBOR rises by more than $2\%$ the S&L will make a loss – the source of the risk is future increases in LIBOR.  

As LIBOR increases the spread (profit) earned by Silverado, falls. Without the swap, if LIBOR $>13\%$ , Silverado makes a loss  

![](351ea7671eaf6f46f62d90edab18177e059a134a5bcf60b7d487f6ce4e702f0b.jpg)  

FIGURE 33.2 Interest rate risk of Silverado Bank  

Silverado Bank can remove this LIBOR risk if it enters into a swap with Goldman to receive LIBOR and pay a fxed rate. Suppose Goldman sets the fxed rate payment in the swap at $s p=11\%$ . By entering into the swap Silverado is protected from any future rises in LIBOR rates. It now efectively has net fxed rate receipts of $2\%$ , which is its fxed (risk-free) proft margin.  

As discussed above, one reason for undertaking a swap is that some frms fnd it cheaper to borrow at say foating rates and then use a swap to create the efective fxed rate payments that they really want. This cost saving provides the fnancial incentive behind the expansion of the swaps market. An example of a swap agreement is shown in Finance Blog 33.1.  

# Finance Blog 33.1 ISDA Swap Agreements  

The International Swaps and Derivatives Association (ISDA) in New York provides some standardisation in swap agreements via a number of master agreements. A stylised example of a confrmation agreement for a plain vanilla interest rate swap between Apple and the swap dealer JPMorgan-Chase is given below.  

# Dates  

Trade date 15 February 2019 Efective date 20 February 2019 Termination date 20 March 2024 Business day convention Following business day Holiday calendar US  

# Fixed leg  

Fixed-rate payer Notional principal Fixed rate Day-count convention Payment dates  

Apple   
$\mathrm{US}\$1000$   
$2.5\%$ p.a.   
Actual/365   
Each 20 February and 20 August Beginning 20 August 2019 and terminating 20 March 2024  

# Floating leg  

Floating-rate payer Notional principal Floating rate Day-count convention Payment dates  

JPMorgan-Chase   
$\mathrm{US}\$1000$   
$\mathrm{US}\$6$ -month LIBOR   
Actual/360   
Each 20 February and 20 August   
Beginning 20 August 2019 and   
terminating 20 March 2024  

The US calendar determines which days are deemed to be business days (e.g. not a weekend or US holiday). If a payment date occurs on a Saturday (say) the payment will take place on the Monday (or a Tuesday, if Monday is a US holiday). Note the diferent day-count conventions for the fxed and foating legs of the swap. A master agreement may cover all outstanding swap deals between the two parties and will also cover the legal arrangements in the event of a default by either side to the agreement.  

# 33.2 CASH FLOWS IN A SWAP  

Suppose on 15 March-01 $\mathit{\check{t}}=0\mathit{\check{\Psi}}$ ,1 Microsoft enters into a ‘receive-foat, pay-fxed’ swap – this is referred to as a ‘long position’ in the swap (by convention). Suppose the swap rate $s p=6\%$ on a notional principal of $Q=\$1000$ , with a 6-month tenor and the swap ends on 15 March-04.  

Floating rate payments are determined by LIBOR at the beginning of each (6-month) reference period but the actual cash payment occurs 6 months later. Hence the known value for LIBOR on 15 March-01, $L_{01}=6.5\%$ is used to determine the foating cash payment on the 15 September-01. Similarly, whatever LIBOR turns out to be on 15 September-01 will determine the foating cash payment on 15 March-02 etc.  

Day-count conventions difer, but we use the so-called ‘money-market’ day-count convention for the foating leg of the swap which is ‘actual/360’. Hence we have $m_{i}=d a y s_{i}/360$ and $d a y s_{i}=$ actual number of days between each repayment date. For a swap with a 6-month tenor actual $d a y s_{i}$ would be around 180 but might vary slightly for each 6-month period. The frst foating payment (on 15 September-01, at $t=1$ ) is:  

$$
C_{F L,1}=L_{01}m_{1}Q=0.065(184/360)\S100\mathrm{m}=\S3,322,222
$$  

The cash fows for the fxed-leg $C_{X,i}$ are determined by the (fxed) swap rate. Hence, $C_{X,i}=$ $(s p.h_{i}Q)$ where $s p$ is the swap rate and $h_{i}$ is the tenor in the fxed-leg. The convention for determining $h_{i}$ for the fxed leg is set out in the swap contract – we assume the convention is $h=180/360$ for each 6-month period in the fxed leg of the swap.2 Hence the fxed cash fows are (always):  

$$
C_{X}=(s p.h.Q)=0.06(180/360)\S100\mathrm{m}=\S3\mathrm{m}
$$  

The net receipts for the long position (receive foating-pay fxed) in the swap, on 15 September-01 is:  

$$
\begin{array}{r}{\cdot O1=\S3,322,222-\S3,000,000=\S322,222}\end{array}
$$  

Similarly the net receipts on 15 March-02 are determined by the out-turn LIBOR rate on 15 September-01 of $7\%$ and the 181 days between September-01 and March-02:  

$$
\cdot O2=\S3,519,444-\S3,000,000=\S519,444
$$  

On 15 March-01 we do not know what the LIBOR rates will turn out to be on any of the reset dates $t=1,2,3,\dots,n-1$ , until we actually reach these dates in ‘real time’. But Table 33.1 assumes a set of out-turn LIBOR rates and calculates the resulting ex-post payments in the swap – that is, the swap payments that ensue after we observe the out-turn values for LIBOR.  

TABLE 33.1 Swap: cash pay-outs (ex-post)   


<html><body><table><tr><td>Notional principal</td><td colspan="5">100,000,000</td></tr><tr><td>Swap rate</td><td colspan="5">6</td></tr><tr><td>Days in years (swap convention)</td><td colspan="5">360</td></tr><tr><td colspan="2">Tenor for fixed leg (days)</td><td colspan="4">180</td></tr><tr><td colspan="6">Tenor for floating leg is 'actual/360'</td></tr><tr><td>Date</td><td>Days</td><td>LIBOR</td><td>LIBOR cash flow</td><td>Fixed cash flow</td><td>Receive float, pay fixed</td></tr><tr><td>15-Mar-01</td><td></td><td>6.5%</td><td></td><td></td><td></td></tr><tr><td>15-Sep-01</td><td>184</td><td>7%</td><td>3,322,222</td><td>3,000,000</td><td>322,222</td></tr><tr><td>15-Mar-02</td><td>181</td><td>6.5%</td><td>3,519,444</td><td>3,000,000</td><td>519,444</td></tr><tr><td>15-Sep-02</td><td>184</td><td>6.25%</td><td>3,322,222</td><td>3,000,000</td><td>322,222</td></tr><tr><td>15-Mar-03</td><td>181</td><td>5.75%</td><td>3,142,361</td><td>3,000,000</td><td>142,361</td></tr><tr><td>15-Sep-03</td><td>184</td><td>5.25%</td><td>2,938,889</td><td>3,000,000</td><td>-61,111</td></tr><tr><td>15-Mar-04</td><td>182</td><td></td><td>2,654,167</td><td>3,000,000</td><td>-345,833</td></tr></table></body></html>

Note: Last reset date 15 March-01. First payoff in the swap is based on rates on 15 March but cash payment does not occur until 15 September.  

# 33.3 SETTLEMENT AND PRICE QUOTES  

Take the case of a US swap dealer who wishes to set the swap rate on a 10-year swap with the foating rate based on 6-month LIBOR (Table 33.2). She will have an indicative pricing schedule (for that day) where the fxed rate will be based on the yield on current 10-year Treasury notes (bonds). In fact this will usually be the par bond yield plus a spread.  

For example on a 10-year swap, if the swap dealer agrees to pay fxed (to counterparty-A) and receive foating then she will quote $s p=2.76\%$ $(=2.7+6$ bps, swap spread) and receive 6-month LIBOR-fat. The swap spread refects the ‘normal’ credit risk as perceived by the swap dealer. Notice that no foating rates appear in the pricing schedule of Table 33.2 since the foating rate is understood to be 6-month LIBOR fat.3  

TABLE 33.2 Indicative pricing schedule for swaps   


<html><body><table><tr><td>Maturity</td><td>Current T-bond rate</td><td>Bank pays fixed</td><td>Bank received fixed</td></tr><tr><td>5 years</td><td>1.5%</td><td>5-year T-bond + 5 bp</td><td>5-year T-bond + 10 bp</td></tr><tr><td>10 years</td><td>2.7%</td><td>10-year T-bond + 6 bp</td><td>5-year T-bond + 12 bp</td></tr><tr><td>20 years</td><td>3.4%</td><td>20-year T-bond + 8 bp</td><td>5-year T-bond + 16 bp</td></tr></table></body></html>  

The dealer will eventually hope to match the pay-fxed deal with an ofsetting swap (from another counterparty-B) to receive-fxed (on the same notional principal and tenor) at $2.82\%$ $(=2.7+12\mathrm{bps})$ ) – thus obtaining 6 bps bid–ask spread as proft. In our above stylised example, once the swap dealer fnds counterparty-B, then she is perfectly hedged with certain net receipts of 6 bps (i.e. the mismatch risk is eliminated).  

However, it may be di\$cult for the swap dealer to fnd a counterparty-B who has exactly the ‘reverse wishes’ of A. For example, if the maturity of A’s swap is say 5 years but B will only enter into the swap for 3 years, then the swap dealer is a net foating rate receiver in years 4 and 5 and is subject to interest rate risk, in the last 2 years of the swap. She may then initially hedge her mismatched swaps book using (Eurodollar) futures contracts which mature in 4 years and 5 years, respectively.  

The bid–ask spread refects several factors, namely the degree of competition between dealers, the risk in (temporarily) holding a net open position on one leg of the swap deal, and a swap dealer’s current inventory position of being either net long or short in the fxed (or foating legs) of all its outstanding swaps (i.e. the overall position of its swap book).  

The bid–ask spreads on interest rate swaps in various currencies are given in Table 33.3. All the fxed rates are quoted against the appropriate LIBOR rate (usually 3 months or 6 months). As you can see the bid–ask spreads are rather small, refecting the high degree of competition and liquidity in the swaps market.  

TABLE 33.3 Swap rates (FT)   


<html><body><table><tr><td rowspan="2">Oct 26</td><td colspan="2">Euro</td><td colspan="2"></td><td colspan="2">US$</td></tr><tr><td>Bid</td><td>Ask </td><td>Bid </td><td>Ask</td><td>Bid</td><td>Ask</td></tr><tr><td>1 year</td><td>1.38</td><td>1.43</td><td>0.82</td><td>0.85</td><td>0.37</td><td>0.40</td></tr><tr><td>5 year</td><td>2.13</td><td>2.18</td><td>2.10</td><td>2.15</td><td>1.47</td><td>1.50</td></tr><tr><td>10 year</td><td>2.78</td><td>2.83</td><td>3.18</td><td>3.23</td><td>2.67</td><td>2.70</td></tr><tr><td>20 year</td><td>3.13</td><td>3.18</td><td>3.74</td><td>3.82</td><td>3.41</td><td>3.44</td></tr><tr><td>25 year</td><td>3.06</td><td>3.11</td><td>3.79</td><td>3.92</td><td>3.52</td><td>3.55</td></tr><tr><td>30 year</td><td>2.94</td><td>2.99</td><td>3.80</td><td>3.93</td><td>3.58</td><td>3.61</td></tr></table></body></html>  

# 33.4 TERMINATING A SWAP  

Suppose a swap agreement has been in existence for some time and the current value of the swap to Microsoft who receives LIBOR and pays fxed, is $\$1.2m$ and therefore the value to the swap dealer (Goldman) is $-\$1.20$ . (We will see how the mark-to-market value of the swap of $\$1.2m$ is calculated in a later chapter.) Microsoft can terminate the swap by sale, assignment or buy-back.  

In a sale, Microsoft simply fnds a third party (e.g. Apple) to take over the fxed payments and LIBOR receipts (from Goldman) and Microsoft sells the swap (to Apple) for $\$1.20$ . Alternatively, if the value of the swap to Microsoft had been $-\$1.45$ (say) then Microsoft would have paid Apple $\$1.45$ to take on the swap. The swap dealer Goldman would have to approve the use of any third party in the deal (i.e. Apple) because of credit risk.  

Microsoft could use a buy-back whereby Goldman would pay $\$1.20$ to Microsoft and the swap is terminated. Finally, Microsoft could undertake a reversal, that is enter a new swap where the cash fows exactly ofset the cash fows in the original swap – the new swap (say with Morgan Stanley) will be a receive fxed-pay foat with the same maturity, tenor, and notional principal as the original swap with Goldman.  

# 33.5 COMPARATIVE ADVANTAGE  

Interest rate swaps are undertaken because there are net reductions in the cost of borrowing for both parties to the swap. The swap dealer can also share in some of these gains. However, to keep things simple assume only two parties in the swap A and B.  

A wishes to end up borrowing \$10m at a foating rate for 5 years and  

B wishes to end up borrowing \$10m at a fxed rate for 5 years.  

The rates ofered to A and B are shown in Table 33.4. ‘A’ has an absolute advantage in both markets since it can borrow at both foating and fxed rate at a lower cost than B (probably because B has a lower credit rating than A). Nevertheless, there is a net gain to both parties if they enter a swap. First look at the total cost to A and B if they directly borrow in their preferred form (i.e. A at foating and B at fxed) or non-preferred form (i.e. A at fxed and B at foating)  

1. Total cost to A and B of direct borrowing in ‘preferred form’  

$$
=B_{X}+A_{F}=11.2\%+(L+0.3\%)=L+11.5\%
$$  

TABLE 33.4 Bank borrowing rates facing A and B   


<html><body><table><tr><td></td><td>Fixed</td><td>Floating</td></tr><tr><td>Company-A</td><td>10.00% (Ax)</td><td>LIBOR+0.3%</td></tr><tr><td>Company-B</td><td>11.20% (Bx)</td><td>LIBOR+1.0%</td></tr><tr><td>Absolute difference (B - A)</td><td>△(fixed)=1.2</td><td>△(float)= 0.7</td></tr><tr><td>Net comparative advantage</td><td colspan="2">NCA = △(fixed)-△(float)= 0.5</td></tr><tr><td rowspan="3">or 'quality spread differential'</td><td>B has comparative advantage in</td></tr><tr><td>borrowing at a floating rate.Hence B</td></tr><tr><td>borrows from the bank at a floating rate.</td></tr></table></body></html>  

2. Total cost to A and B if they borrow in ‘non-preferred form’  

$$
=A_{X}+B_{F}=10\%+(L+1\%)=L+11\%
$$  

Hence the total cost is lower if they initially borrow in their non-preferred form:  

Although there is a reduction in total cost using strategy (2), it results in A and B not having their preferred form of borrowing. However, a swap provides the mechanism to achieve their preferred form of borrowing and it has the advantage of lowering the overall cost of borrowing for both parties.  

Looking at the overall gain in a slightly diferent way (Table 33.4), the key element is that B has comparative advantage when borrowing in the foating rate market, while A has comparative advantage when borrowing in the fxed rate market. (Comparative advantage is used in international trade theory to help explain why the UK exports some wine to France, even though the latter has an absolute cost advantage in producing wine.)  

B has comparative advantage when borrowing in the foating rate market because B pays only $0.7\%$ more than A does, whereas B pays (a larger) $1.2\%$ more than A in the fxed rate market. (If you like, B pays ‘less more’ in the foating market than in the fxed rate market.)  

B initially borrows foating and A borrows fxed. They then enter into a swap agreement whereby B agrees to pay A at a fxed rate and A pays B at a foating rate, so they both ultimately achieve their desired type of borrowing (i.e. B ends up paying fxed and A foating). A swap is advantageous to both parties if the net comparative advantage or quality spread diferential is positive.  

Net comparative advantage / Quality spread diferential  

$$
\begin{array}{r l}&{N C A=D i f f e r e n c e i n F i x e d R a t e s-D i f f e r e n c e i n F l o a t i n g R a t}\\ &{\qquad=(11.2\%-10\%)-[(L I B O R+1\%)-(L I B O R+0.3\%)]}\\ &{\qquad=1.2\%-0.7\%=0.5\%}\end{array}
$$  

The $0.5\%$ is the total gain from the swap, which is available to A and B. As long as A and B get some gain they will willingly enter the swap. We arbitrarily assume that the gain of $0.5\%$ is split equally $(0.25\%)$ between A and B. (This split will depend on the relative bargaining power of A and B.) B has a comparative advantage in the foating rate market and hence issues $\$100$ foating rate debt at $\mathrm{LIBOR}+1\%$ while A issues fxed rate debt at $10\%$ (Figure 33.3).  

Here’s how we work out the fgures in the swap (which are the cash fows between A and B in Figure 33.3). We initially consider the swap from B’s point of view (who ultimately wants to borrow fxed) and expects to gain $0.25\%$ overall. We will fnd that this ensures that A also achieves a gain of $0.25\%$ . This is what happens to B:  

1. B initially borrows ‘direct’ from a bank at $\mathrm{LIBOR}+1\%$ (in which it has NCA)   
2. B in ‘leg1’ of the swap agrees to receive LIBOR   
3. Net payments by B so far are $1\%$ (fxed)   
4. But B must end up with a gain of $0.25\%$ , hence  

B’s total fxed interest payments $\mathbf{\tau}=\mathbf{\tau}$ ‘Direct cost of borrowing fxed Swap gain’ $=11.2\%-0.25\%=10.95\%$  

5. Hence in ‘leg $2^{\circ}$ of the swap B must pay fxed at $10.95\%-1\%=9.95\%$ .  

![](c7a578bfdc02d2867dd47fb73a6c4df7432842dc1caaa0a130137858da1f3644.jpg)  

Swap: B is floating rate receiver and fixed rate payer A is floating rate payer and fixed rate receiver  

After the swap: B borrows fixed at an effective rate of $9.95\%+1\%=10.95\%$ $0.25\%$ less than directly borrowing at $11.2\%$ fixed)  

FIGURE 33.3 Interest rate swap (between A and B)  

Out-turn after swap for cash flows of B:  

B initially borrows at LIBOR from a bank and in the swap, receives foating and pays fxed:  

• B pays $\mathrm{LIBOR}+1\%$ on its bank loan • B receives LIBOR from A • B pays $9.95\%$ fxed to A.  

Hence, the net result is that B ends up paying $10.95\%$ fxed $(=9.95\%+1\%)$ even though it started out with a LIBOR bank loan. Although B pays $10.95\%$ fxed, this is $0.25\%$ less than if it went directly to the bank and borrowed at the rate of $11.2\%$ fxed (Table 33.4). Does the above also allow A to gain 0.25 from the swap? The cash fows for A are:  

Out-turn after swap for cash flows of A:  

Initially ‘A’, takes out a fxed rate bank loan and in the swap receives fxed and pays foating:  

• ‘A’ pays $10\%$ fxed on its bank loan • ‘A’ receives $9.95\%$ fxed from B • ‘A’ pays LIBOR to B.  

Hence ‘A’ ends up paying $\mathrm{LIBOR}+0.05\%$ $(=\mathrm{LIBOR}+10\%-9.95\%)$ . ‘A’ has converted its fxed interest bank loan into a net foating rate payment. Also A’s foating rate payment of $\mathrm{LIBOR}+0.05\%$ is $0.25\%$ less than it would pay if it borrowed directly from the bank at LIBOR $+0.3\%$ (see Table 33.4).  

Hence in the swap, A agrees to pay B at LIBOR and B agrees to pay A fxed at $9.95\%$ (Figure 33.3). The overall payments and receipts are:  

• B takes out a bank loan of $\$100$ at $\mathrm{LIBOR}+1\%$ • ‘A’ takes out a bank loan of $\$100$ at $10\%$ fxed • In the swap $\mathbf{\dot{A}}^{\prime}$ agrees to pay B at LIBOR on a notional $\$100$ and • B agrees to pay ‘A’ at $9.95\%$ fxed, on notional $\$100$ .  

Both A and B gain by $0.25\%$ each, compared with borrowing directly in their preferred form from the bank. It can be shown (but it is tedious) that if we put a swap dealer in the ‘middle’, who deals with both A and B then all three parties, A, B, and the swap dealer can each have a share in the $0.5\%$ total gain (see Appendix 33).  

# 33.6 SUMMARY  

• Swap contracts allow one party to exchange periodic cash fows with another party. They are over-the-counter OTC instruments.   
• A plain vanilla interest rate swap involves one party exchanging fxed interest payments for cash fows determined by a foating rate (LIBOR). The notional principal in an interest rate swap is not exchanged.   
• Swaps enable a company with a bank loan at foating rates to efectively switch this to a fxed rate (or vice versa) – hence a swap can be used to eliminate interest rate risk of future cash fows.   
• Swap dealers earn profts on the bid–ask spread of the swap deal.   
• One reason for swaps is that it may be cheaper for a company to borrow at say foating and use a swap to convert this to a fxed rate loan, rather than to directly obtain a fxed rate loan from its correspondent bank.   
• The principle of comparative advantage allows all the parties to the swap to obtain their desired cash fows (fxed or foating), at a lower cost than borrowing directly in their preferred form.  

# APPENDIX 33: COMPARATIVE ADVANTAGE WITH SWAP DEALER  

We use the same fgures as in the text which are reproduced here in Table 33.A.1.  

Assume that the swap dealer takes part of the total gain of $0.5\%$ . In Figure 33.A.1 the swap dealer breaks even on the foating rate, since she pays out and receives LIBOR. On the fxed leg the swap dealer receives $10\%$ but only pays out $9.9\%$ , which provides an overall gain of $0.1\%$ for the swap dealer.  

TABLE 33.A.1 Bank borrowing rates facing A and B   


<html><body><table><tr><td></td><td>Fixed</td><td>Floating</td></tr><tr><td>Company-A</td><td>10.00% (Ax)</td><td>LIBOR+0.3%</td></tr><tr><td>Company-B</td><td>11.20% (Bx)</td><td>LIBOR+1.0%</td></tr><tr><td>Absolute difference (B－ A)</td><td>(fixed)= 1.2</td><td>(float)= 0.7</td></tr><tr><td>Net comparative advantage or 'quality spread differential'</td><td>NCA = △(fixed)-△(float)= 0.5</td><td></td></tr><tr><td rowspan="3"></td><td>B has comparative advantage in</td><td></td></tr><tr><td>borrowing at a floating rate.Hence B</td><td></td></tr><tr><td>borrows from the bank at a floating rate.</td><td></td></tr></table></body></html>  

Assume swap dealer makes $0.1\%$ and A and B each gain $0.2\%$ Swap dealer makes no profit on the floating rate leg  

![](968d1eced56ff5f5141520f50353c6feee4bdc5a950f8bcca357dc3ac70f8aae.jpg)  

# FIGURE 33.A.1 Swap dealer  

Cash Flows A  

A’ initially takes out a fxed rate bank loan and in the swap receives fxed and pays foating  

• ‘A’ pays $10\%$ fxed on the bank loan (as Table 33.A.1) • ‘A’ receives $9.9\%$ fxed from the swap dealer and • pays LIBOR to the swap dealer.  

The net efect is that A pays $\mathrm{LIBOR}+0.1\%$ , which is $0.2\%$ less than going directly to the foating rate loan market. From Figure 33.A.1 it is easy to work out B’s position.  

# Cash Flows B  

B initially takes out a bank loan at LIBOR and in the swap receives foating and pays fxed • B pays $\mathrm{LIBOR}+1\%$ on its bank loan (as Table 33.A.1) • B receives LIBOR from the swap dealer and • B pays $10\%$ fxed to the swap dealer.  

The net efect is that B pays $11\%$ fxed (which is $0.2\%$ better than borrowing directly at a fxed rate from its correspondent bank). The swap dealer gains $0.1\%$ on the diference between its receipts and payments on the fxed legs of the two swaps. Note that the swap dealer is subject to potential default risk since either A or B could default, yet the swap dealer has to honour its commitment to the other party. Also note that LIBOR in the above example can take on any value and the swap will still be worthwhile to all parties – so they will willingly enter the swap.  

# EXERCISES  

# Question 1  

You have a foating rate bank loan (at LIBOR plus a spread). Why might you use an interest rate swap?  

# Question 2  

What is a forward rate agreement (FRA) and how does it relate to a plain vanilla interest rate swap?  

# Question 3  

You are a swap dealer. What is the meaning of the term ‘warehousing swaps’?  

# Question 4  

Explain the diference between credit risk and market risk with reference to interest rate swaps. How can the market risk of interest rate swaps be hedged?  

# Question 5  

The notional principal in a ‘pay-fxed, receive-foating’ interest rate swap with 3 further payments is $\$200$ . The fxed rate payer pays $11\%$ p.a. and the foating rate payer, pays LIBOR. Payments in the swap are every 90 days. Today at time $t$ , immediately after a payment date, LIBOR is $11.5\%$ p.a. The LIBOR rates at $t+90$ days, $t+180$ days and $t+270$ days, actually turn out to be $10.5\%$ p.a., $10.2\%$ p.a. and $9.6\%$ p.a., respectively.  

Show the schedule of actual payments in the swap. Assume actual/365 day-count convention for all interest rates.  

# Question 6  

Consider the following loan rates facing frms A and B.  

<html><body><table><tr><td></td><td>Fixed</td><td>Floating</td></tr><tr><td>Firm-A</td><td>10% p.a.</td><td>LIBOR + 0.3% p.a.</td></tr><tr><td>Firm-B</td><td>11.2% p.a.</td><td>LIBOR + 1.0% p.a.</td></tr></table></body></html>  

Firm-A can borrow more cheaply than frm-B in both the fxed and foating market. But frm-A wants to ultimately end up borrowing at a foating rate and B at a fxed rate. How might both A and B beneft by using the swaps market? Assume A and B deal directly with each other and split the gains from the swap, 50:50.  

# Question 7  

Companies A and B have been ofered the following rates per annum on a $\$20$ million, 5-year loan:  

<html><body><table><tr><td></td><td>Fixed rate</td><td>Floating rate</td></tr><tr><td>Company A</td><td>12.0%</td><td>LIBOR + 0.1%</td></tr><tr><td>Company B</td><td>13.4%</td><td>LIBOR + 0.6%</td></tr></table></body></html>  

Company A wants to end up paying a foating rate while company B desires a fxed rate loan. Design a swap that will net a bank, acting as intermediary, $0.1\%$ p.a. and appear equally attractive to both companies. Assume the bank pays and receives LIBOR and split any gain in the swap equally between A and B (after the swap dealer has taken a $0.1\%$ p.a. gain).  