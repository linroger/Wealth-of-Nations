---
tags:
  - eurodollar_futures
  - fixed_income_derivatives
  - interest_rate_caps
  - interest_rate_options
  - libor_bank_loan
  - t_bond_option
aliases:
  - Eurodollar options
  - Interest rate caps and floors
  - Interest rate collar
  - T-bond options
key_concepts:
  - Interest rate caps
  - Interest rate collar
  - Interest rate floors
  - LIBOR bank loan
  - Options on T-bond futures
  - Options on T-bonds
---
# FIXED INCOME DERIVATIVES  

# T-Bond Option, Caps, Floors and Collar  

# Aims  

• To examine the use of options on T-bonds (T-notes) and options on T-bond futures and Eurodollar futures.   
• To show how interest rate caps (foors) can be used to set an efective upper (lower) limit on the interest rate to be paid (received) in the future on a LIBOR bank loan (deposit).   
• To show how a collar is used to limit the maximum and minimum interest rates payable in the future, on an existing LIBOR bank loan or bank deposit.  

Interest rate options have payofs determined either by the interest rate itself (caps and foors) or the payof is based on the price of an asset (e.g. bond price or bond futures price). There are a wide variety of interest rate derivatives which can be used either for speculation on the future direction of interest rates (or bond prices) or to hedge/insure against future changes in interest rates (or bond prices). Many interest rate derivatives are OTC instruments while some are traded on organised exchanges. In Chapters 40 and 41 we examine in more detail how fxed-income derivatives are priced but here we concentrate on describing how these derivatives are used.  

# 38.1 OPTIONS ON T-BONDS AND EURODOLLARS  

A European option on a T-bond gives the holder the right to buy or sell a T-bond at some time in the future at a certain known strike price $K.$ . The payof to a long call option on the T-bond is $\operatorname*{max}(V_{T}-K,0)$ where $V_{T}$ is the market price of the bond at maturity of the option contract. A T-bond option can be used to speculate on future changes in long-term interest rates – for example, buy a call on a T-bond if you believe interest rates will fall in the future (i.e. bond prices will rise above $K$ ). A put on a T-bond can be used to insure a lower bound of $K_{:}$ , for an existing portfolio of T-bonds if interest rates rise. If interest rates fall and bond prices rise (above $K$ ) you will not exercise the put but your bonds have a higher market price.  

In practice, hedging or speculation is less costly if the underlying in the options contract is a futures contract rather than the cash market asset, such as a T-bond. Therefore the most popular exchange traded fxed-income options in the US are on T-bond futures, T-note futures and Eurodollar futures. These, of course, are futures options.  

In an earlier chapter we noted that the value at expiration $T$ , of a call on a T-bond futures option is $\operatorname*{max}(F_{T}-K,0)$ where $F_{T}$ is the T-bond futures price at expiration of the option. If the option is exercised, the holder of a long call receives a long position in the futures contract and if the futures contract is immediately closed out there is a cash payout of $F_{T}-K$ , where $F_{T}$ is the Eurodollar futures price at expiration of the option’s contract. (If the futures is not closed out then initial margin must be paid.)  

A US T-bond futures call option quote might be denoted $^{\cdot}C=3{-}10^{3}$ . This implies $C=$ $3\mathrm{-}10/64\%$ and on a futures contract size of $\$100,000$ of T-bonds, implies an invoice price for the option of \$3 156 $.25\left(=0.0315625\times100,000\right)$ . A basis point $(0.01\%)$ change in the IMM futures index, implies a gain or loss on one T-bond futures contract of $\$25$ . An option on a Eurodollar futures contract is priced similarly, so a call option with a quoted premium of $C=0.50$ (50 basis points) implies that one call costs $50\times\$25=\$1,250$ .  

# 38.2 CAPLETS AND FLOORLETS  

Interest rate options are widely used to either speculate on the future course of interest rates or to hedge/insure the interest payments/receipts on an underlying cash market position (e.g. LIBOR bank loan or bank deposit). Below we discuss:  

• The mechanics of using interest rate options and how their payofs are related to FRAs and interest rate swaps.   
• Hedging a single interest rate payment or receipt, using a caplet or foorlet.   
• Setting an upper limit on a series of interest rate payments, using a cap.   
• Setting a lower limit on a series of interest rate receipts, using a foor.   
• Establishing both a foor and a ceiling on a corporate or bank’s (foating rate) borrowing costs by using a collar.  

We have seen how an FRA ‘locks in’ an interest rate beginning at some point in the future. If you have a 90-day LIBOR loan with principal $Q$ plus a long position in an FRA (with notional principal $Q$ ), then if interest rates either rise or fall, your efective borrowing rate on the loan remains constant.  

$$
\begin{array}{r l}{\ }&{=Q\{L I B O R_{T}-[L I B O R_{T}-F R A]\}(90/360)}\\ {\ }&{=Q\ F R A(90/360)}\end{array}
$$  

# 38.2.1 Long Call (Caplet)  

A caplet is like an FRA in that it sets an efective maximum interest rate you pay on a LIBOR bank loan. But if interest rates turn out to be low, you do not exercise the caplet and simply pay the lower rate of interest on your loan. So the caplet sets a maximum interest rate you will pay on the loan but allows you to take advantage of lower interest rates should they occur. A long position in a caplet has a $\$1$ -payof at maturity $T$ :  

where days is the tenor of the LIBOR rate in the caplet. Suppose the caplet is on 90-day LIBOR on a notional principal $Q=\$1000$ , with strike $K_{c a p}=10\%$ p.a. and premium $C=\$250,000$ (i.e. equal to $0.25\%$ of the $\$1000$ principal). The option expires at $T=30$ days. Using ‘actual/ $360^{\circ}$ day-count convention, the caplet has a cash payout (at $T\mathrm{+}90$ days):  

$$
T+90=\S1000\mathrm{max}(0,L I B O R_{T}-0.10)(90/360)
$$  

The payof is determined at expiration of the option at $T=30$ but the cash payout does not take place until 90 days later (Figure 38.1).  

If at expiration $L I B O R_{T}=14\%$ the option has a payof of $L I B O R_{T}-K_{c a p}=4\%$ p.a. (or $1\%$ over 90 days). This proft of $4\%$ p.a. ofsets the higher borrowing rate of $L I B O R_{T}=14\%$ giving an efective borrowing rate of $10\%$ p.a., which equals the strike rate in the option contract. If at expiration $L I B O R_{T}=8\%<K_{c a p}=10\%$ then the caplet is not exercised but you can take advantage of the low borrowing cost of $8\%$ p.a. The loan plus caplet ensures an efective maximum borrowing cost of $K_{c a p}=10\%$ but allows the ‘upside’ of borrowing at low rates should these occur. The caplet therefore provides insurance for the borrower:  

![](b8bb6ed9610620b56d469decbe3e8f2ca7d6d3856a9f10ba71389da0053f0076.jpg)  
FIGURE 38.1 Payof at maturity, 30-day caplet on 90-day LIBOR  

$$
\begin{array}{r l}&{\L_{\mathit{\mathcal{C}}\mathit{b o r r o w i n g c o s t}}^{\mathit{\texttt{c o l I B O R}}_{T}(\operatorname{90/360})-Q}\ \{\operatorname*{max}(0,L I B O R_{T}-K_{c a p})\ (d a y s/360)}\\ &{\quad\quad\quad=Q\ K_{c a p}\ (d a y s/360)\quad\quad\quad\quad\quad\quad\mathrm{if}\ L I B O R_{T}>K_{c a p}}\\ &{\quad\quad\quad=Q\ L I B O R_{T}\ (\mathrm{days/360})\quad\quad\quad\quad\mathrm{if}\ L I B O R_{T}\leq K_{c a p}}\end{array}
$$  

Of course, if the corporate at $T=30$ days decides it does not want to borrow funds after all, the most it will have lost is the call premium and if interest rates have risen above $K_{c a p}=10\%$ , then it will earn a proft from the call.  

The efective borrowing cost of the loan as calculated above ignores the caplet premium of $C=\$250,000$ (which has to be paid at $t=0$ ) and the fact that the cash payout on the option does not occur until $T\mathrm{+}90$ . Calculation of the correct efective rate on the loan requires the following steps. If 30-day LIBOR at $t=0$ is $L_{0}=10\%$ then at $T$ :  

Caplet premium $+$ Interest $T=\S250,000\ [1+0.10(30/360)]=\S252,083$ Efective amount borrowed $T=\S100\mathrm{m}-\S252,083=\S99,748\mathrm{m}$  

At $T_{:}$ , if 90-day $L I B O R_{T}=14\%$ then:  

$$
T+90=\S100\mathrm{m}\left(0.14-0.10\right)\left(90/360\right)=\S1\mathrm{m}
$$  

$$
T+90=\S100\mathrm{m}\left(0.14\right)\left(90/360\right)=\S3.5\mathrm{m}
$$  

$$
J n h e d g e d~c o s t-c a p l e t~p a y o u t=\S3.5\mathrm{m-\mathbb{{g}}1m=\Phi2.5\mathrm{m}}
$$  

The efective interest paid on borrowing $\$99.748\mathrm{m}$ at $T$ and paying out $\$102.5m$ at $T\mathrm{+}90$ is:  

$$
t i v e i n t e r e s t\ c o s t=\left(\frac{102.5}{99.748}\right)^{\frac{365}{90}}-1=\left(1.02759\right)^{\frac{365}{90}}-1=0.1167\ \left(11.67\%\right)
$$  

The efective interest cost of $11.67\%$ p.a. is reasonably close to that of the strike rate of $K_{c a p}=10\%$ (simple interest) in the option contract. The cost of the unhedged position is considerably higher than $K_{c a p}=10\%$ because the LIBOR rate at $T$ is $14\%$ :  

With the caplet, whatever the out-turn LIBOR rate (at or above $K_{c a p}=10\%$ ), the cost of borrowing is a maximum of $11.67\%$ . Of course, if $\mathrm{LIBOR}_{\mathrm{T}}<10\%$ , then the caplet is not  

![](21f62fd3cfee65f124bdad808f99e449d887291e50bc997322adcc07a15eeb8c.jpg)  
FIGURE 38.2 Loan $^+$ caplet  

exercised and the interest cost of the loan is the low LIBOR rate. The cost of the unhedged position and the efective cost of borrowing with the long caplet are given in Figure 38.2. The payof profle for the insured position is similar to a covered call.  

# 38.2.2 Long Put (Floorlet)  

Consider a corporate that will place $\$1000$ in a deposit account in 90 days’ time and the deposit account is on 180-day LIBOR. Alternatively, consider a bank that in 90 days time will issue a bank loan to a corporate, based on 180-day LIBOR (plus a spread) but has raised the fnance with a fxed rate deposit. Both the corporate and the bank are vulnerable to a fall in 180-day LIBOR rates, in 90 days’ time.  

Both parties can ‘lock in’ a lower bound on their efective interest rate in 90 days’ time, by today buying a put option (foorlet) on 180-day LIBOR, which has an expiration date in 90 days. If the strike $K_{F L}=10\%$ the payof from the foorlet in $T=90$ days is:  

where $d a y s=180$ . But the corporate with the bank deposit will not receive the payof from the foorlet until $T\mathrm{+}180$ . If at expiration 180-day $L I B O R_{T}=8\%<K_{F L}=10\%$ , the payof to the put is $(K_{F L}-L I B O R)=2\%$ which ofsets the lower deposit rate of $8\%$ p.a. This efectively ‘locks in’ a minimum efective deposit rate of $8\%+2\%$ which is equal to the strike rate $K_{F L}=$ $10\%$ – hence the put is known as a foorlet. If at $T$ , 180-day $L I B O R_{T}=11\%>K_{F L}=10\%$ , the put is not exercised but the corporate receives the high deposit rate of $11\%$ . The foating rate bank deposit plus the long foorlet has a payof profle of a long call – see Figure 38.3:  

![](2254348aabbce9c22d60eae0087307bc3d333ea82bee9dfe26836ea3af3ac210.jpg)  
FIGURE 38.3 Deposit $^+$ foorlet  

$$
\begin{array}{r l}&{\mathrm{\Lambda}_{^2}d e p o s i t r a t e=Q\ L I B O R_{T}(90/360)+Q\{\operatorname*{max}(0,K_{F L}-L I B O R_{T})\ (d a y s/360)\}}\\ &{\qquad=Q\ K_{F L}\ (d a y s/360)\qquad\mathrm{~if~}L I B O R_{T}<K_{F L}}\\ &{\qquad=Q\ L I B O R_{T}\ (\mathrm{days}/360)\qquad\mathrm{~if~}L I B O R_{T}\geq K_{F L}}\end{array}
$$  

The efective return on the deposit plus foorlet depends on the exact timing of the cash fows. Suppose the put premium $P=\$250,000$ on a notional principal $Q=\$1000$ . If 90-day LIBOR at $t=0$ is $L_{0}=10\%$ then at $T$ :  

$$
T=\S250,000[1+0.10(90/360)])=\S256,250
$$  

If at expiration $L I B O R_{T}=8\%$ , then:  

Net cash payout excluding principal \$5  

Total amount received at $T+180=\$105\mathrm{m}$  

Annualised return $(d e p o s i t+f l o o r l e t)=[105/100.25625]^{365/180}-1=0.0983(9.83\%)$  

Note that the unhedged return is based on the actual bank deposit of $\$1000$ and a fnal payment of $\$1045$ , whereas for the deposit $+$ foorlet we have to factor in the cost of the foorlet.  

With the foorlet there is a minimum return of $9.83\%$ (which is higher than the unhedged return on the deposit account of $8.28\%$ ). If $\mathrm{LIBOR}_{\mathrm{T}}$ turns out to be higher than $K_{F L}=10\%$ , then the put is not exercised but the corporate earns a high interest rate on its deposit account.  

The Excel fle for the payof to a caplet and foorlet can be found on the website.  

Interest rate options are usually OTC instruments where the strike rate is usually chosen to be close to the current level of spot (or forward) interest rates. Note that unlike some other fxed-income derivative contracts (e.g. T-bill futures and T-bond futures) which have payofs based on the price of the underlying asset, caplets and foorlets have payofs based on interest rates.  

# 38.3 INTEREST RATE CAP  

So far we have used an OTC interest rate contract to ‘lock in’ either a maximum borrowing rate or a minimum deposit rate, at a single future date. However, a corporate or a bank may wish to lock in a series of payments or receipts over successive known future dates.  

To obtain protection against a series of rising loan rates whilst also benefting from any fall in rates, then today buy a cap.  

A cap is nothing more than a series of individual caplets (calls) which mature on dates corresponding to future LIBOR reset dates on an existing loan. A cap is therefore a ‘strip’ of caplets. The cap premium is equal to the sum of the call premia for the separate caplets.  

At each LIBOR reset date on the loan, the cap will have a payof depending on whether LIBOR on the expiration date exceeds the strike rate in the cap contract. Actual cash payment takes place after the expiration date. For example, if the cap is written on 90-day LIBOR, payment will take place at $T\mathrm{+}90$ , based on the 90-day LIBOR rate on the expiration date.  

Suppose on 10 April a corporate has a 1-year loan of $\$200$ , with interest payments based on 90-day LIBOR. The corporate fears a rise in interest rates over the year and wishes to cap its payments at the current 90-day LIBOR rate of $L_{0}=10\%$ . It buys an interest rate cap for $C=$ $\$60,000$ with strike $K_{c a p}=10\%^{1}$ and expiration dates on 10 July, 10 October, etc. (assuming these are ‘working days’). The cap premium at $\$60,000$ is $0.3\%$ of the principal of $\$200$ .  

TABLE 38.1 Loan and cap   


<html><body><table><tr><td>Interest cost with cap without cap</td><td>Per quarter 2.61% 2.82%</td><td>Per annum 10.88% 11.77%</td><td colspan="6"></td></tr><tr><td>Date</td><td>Days in quarter</td><td>LIBOR</td><td>Interest due</td><td>Cap payment</td><td>Principal repayment</td><td>With cap</td><td colspan="2"> Net cash flows</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>Without cap</td></tr><tr><td>10-Apr-00</td><td></td><td>10</td><td></td><td>-60,000</td><td></td><td>0 19,940,000</td><td></td><td>20,000,000</td></tr><tr><td>10-Jul-00</td><td>91</td><td>10.7</td><td>505,556</td><td></td><td>0</td><td>0</td><td>-505,556</td><td>-505,556</td></tr><tr><td>10-Oct-00</td><td>92</td><td>12.3</td><td>546,889</td><td></td><td>35,778</td><td>0</td><td>-511,111</td><td>-546,889</td></tr><tr><td>10-Jan-01</td><td>92</td><td>11.6</td><td>628,667</td><td>117,556</td><td></td><td>0</td><td>-511,111</td><td>-628,667</td></tr><tr><td>10-Apr-01</td><td>90</td><td></td><td>580,000</td><td>80,000</td><td></td><td>20,000,000 -20,500,000 -20,580,000</td><td></td><td></td></tr></table></body></html>

Note: First payment on the cap is based on 10 July but does not get paid until 10 October.  

At each expiration date $(=T)$ for the caplets, the cash payout 90 days later is:  

$$
(T+90)=\S20\mathrm{m}\times\mathrm{max}\{0,L I B O R_{T}-0.10\}(90/360)
$$  

Since $L I B O R=10.7\%$ on 10 July this gives rise to a cap payout of $\$35,778$ on 10 October (Table 38.1). The net cash fow on 10 October of $\$511,111$ is the interest payment on the loan of $\$546,889$ less the cap payout of $\$35,778$ . If interest rates rise over the year then the cap will lock in an efective (simple) interest cost for the loan of around $K_{c a p}=10\%$ . Table 38.1 shows the (ex-post) cash payments in the cap, assuming that interest rates are always above $10\%$ throughout the year.  

The annualised borrowing rate with the cap in place is the internal rate of return from the net cash fows and depends on LIBOR rates over the life of the cap. The internal rate of return is the solution for $y$ where the net cash fows are given in Table 38.1 (column 7):  

$$
\S19.94\mathrm{{m}={\frac{\S0.5056\mathrm{{m}}}{(1+y)}}+{\frac{\S0.5111\mathrm{{m}}}{(1+y)^{2}}}+{\frac{\S0.5111\mathrm{{m}}}{(1+y)^{3}}}+{\frac{\S20\mathrm{{m}}+\S0.5\mathrm{{m}}}{(1+y)^{4}}}}
$$  

$y=2.615\%$ quarter annualised compound rate $=(1.02615)^{4}-1=10.88\%$ p.a.  

If the cap had not been purchased, the cash fows in the fnal column of Table 38.1 imply an unhedged cost (internal rate of return) of $11.77\%$ p.a.  

If LIBOR rates had fallen below $10\%$ at any reset date, that caplet would not be exercised but the lower cash market LIBOR rate implies a lower efective borrowing cost for the corporate. A cap therefore fxes the maximum interest rates payable on a bank loan over the life of the cap but allows the corporate to take advantage of lower loan rates, should they occur.  

# 38.4 INTEREST RATE FLOOR  

A corporate with a series of future cash infows which it wants to place on deposit would lose from a future fall in interest rates. Similarly, a bank which receives foating rate payments on its loans would lose from a fall in rates.  

To obtain protection from a series of falling deposit rates, whilst also benefting from any rise in LIBOR rates, buy a foor, today.  

A foor is a series of interest rate puts (foorlets), each one expiring on the reset date for interest paid on the bank deposit. The payof from each foorlet on a notional principal $\$0i s^{2}$ :  

$$
Q\operatorname*{max}(0,K_{F L}-L I B O R_{T})\ (d a y s/360)
$$  

Suppose on 10 January a corporate places $\$200$ in a 1-year bank deposit tied to 90-day LIBOR and it purchases a foor with a strike rate $K_{F L}=10\%$ at a premium of $\$40,000$ , with the frst reset date on 10 April. The payments with and without the foor, if we assume a fall in 90-day interest rates over the whole year, are given in Table 38.2.  

The corporate has a cash outfow equal to the $\$200$ bank deposit and also pays $\$40,000$ for the foor, making a total cash outfow of $\$20,040,000$ . On 10 January, 90-day LIBOR rates are $L_{0}=9.9\%$ hence:  

$$
\mathrm{erest}\ (10\ \mathrm{April})=\S20\mathrm{m}\ (0.099)(90/360)=\S500,500
$$  

TABLE 38.2 Deposit and foor   


<html><body><table><tr><td>Interest cost Per quarter Per annum with floor without floor</td><td>2.48% 2.32%</td><td>10.3% 9.6%</td><td colspan="6"></td></tr><tr><td>Date</td><td>Days in quarter</td><td>LIBOR</td><td>Interest due</td><td>Floor payment</td><td>Principal repayment</td><td></td><td colspan="2">Net cash flows</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>With floor</td><td>Without floor</td></tr><tr><td>10-Jan-00</td><td></td><td>9.9</td><td></td><td>-40,000</td><td></td><td>0</td><td>-20,040,000</td><td>-20,000,000</td></tr><tr><td>10-Apr-00</td><td>91</td><td>9.5</td><td>500,500</td><td></td><td>0</td><td>0</td><td>500,500</td><td>500,500</td></tr><tr><td>10-Jul-00</td><td>91</td><td>9</td><td>480,278</td><td>25,278</td><td></td><td>0</td><td>505,556</td><td>480,278</td></tr><tr><td>10-Oct-00</td><td>92</td><td>8</td><td>460,000</td><td>51,111</td><td></td><td>0</td><td>511,111</td><td>460,000</td></tr><tr><td>10-Jan-01</td><td>92</td><td></td><td>408,889</td><td>102,222</td><td></td><td>20,000,000</td><td>20,511,111</td><td>20,408,889</td></tr></table></body></html>

Note: First payment of the floor is based on 10 April but does not get paid until 10 July.  

On 10 April LIBOR has fallen to $L_{1}=9.5\%$ hence:  

Payout from foorle $\mathrm{{t}(o n~10~J u l y)=\S20m\ (0.10-0.095)(91/360)=\S25{,}278}$  

On 10 July based on $L_{1}=9.5\%$ :  

Deposit Interest $(10~\mathrm{July})=\S20\mathrm{m}~(0.095)(91/360)=\S480,278$  

Cash fows with the foor are given in Table 38.2 (column 7) and imply an internal rate of return of $2.48\%$ per 90 days or $10.3\%$ p.a. $(=(1.0248)^{4}-1)$ . If the foor had not been used then as LIBOR rates on the bank deposit fall, the unhedged return is $9.6\%$ p.a. Hence the foor has boosted the corporate’s efective interest rate by about 70 bps. Had LIBOR been above $10\%$ over the year, the foor would not be exercised but the corporate would have the beneft of higher deposit interest rates (to ofset against the foor premium it paid at the outset).  

# 38.5 INTEREST RATE COLLAR  

If a corporate is borrowing money at LIBOR, it can protect itself against future rises in LIBOR by buying a cap and it also benefts if interest rates fall, since its loan repayments will be low. The corporate may have to pay a hefty cap premium for this privilege. It can ofset some of this cost by also selling a foor and hence receiving the foor (put) premium.  

Suppose $K_{c a p}=10\%$ and $K_{F L}=8\%$ . Hence at LIBOR rates above $10\%$ , the cap is exercised and the corporate’s efective borrowing costs are a maximum of $K_{c a p}=10\%$ (Figure 38.4). When LIBOR falls below $8\%$ the corporate can take advantage of lower loan rates but these savings are ofset because the corporate will have to pay $K_{F L}-L I B O R$ on the written foor. Hence for $L I B O R<K_{F L}$ (ignoring cash fows from the sale of the foor and the cost of the cap):  

![](851befc3b2be2f17784d1b6836b1afa89dcf11a6544e50ec4929234a637d2179.jpg)  
FIGURE 38.4 Collar  

The net efect of being long a cap and short a foor is to establish both a ceiling and a foor on the efective borrowing cost of the corporate’s LIBOR loan – this combination is a collar.  

A collar comprises a bank loan plus a long cap and short foor.   
It establishes both a foor $K_{F L}=8\%$ and a ceiling $K_{c a p}=10\%$ on the efective borrowing cost.  

The efective cost of the loan plus a collar depends on the path for interest rates over the life of the collar and the strike rates chosen for the cap and the foor.  

# 38.5.1 Payoffs from the Collar  

We ignore the fact that the cap and foor premia are paid/received at $t=0$ whereas the payofs to the collar accrue at various times $t>0$ . At any expiration date, the option payofs (ignoring the option premia) on the collar (for $K_{c a p}=10\%$ and $K_{F L}=8\%$ ) and a 90/360 day-count convention are:  

Payoff on the long cap and short floor  

$$
=\{\operatorname*{max}[0,L I B O R_{T}-K_{c a p}]-\operatorname*{max}[0,K_{F L}-L I B O R_{T}]\}\ Q(90/360)
$$  

Effective borrowing cost with collar  

$$
\begin{array}{r l}&{=\{L I B O R_{T}+\{\operatorname*{max}[0,L I B O R_{T}-K_{c a p}]-\operatorname*{max}[0,K_{F L}-L I B O R_{T}]\}\ Q(90/360)}\\ &{=Q\ K_{c a p}(90/360)\ }\\ &{=Q\ K_{F L}(90/360)\ }\\ &{=Q\ L I B O R_{T}(90/360)\ }\\ &{=Q\ L I B O R_{T}(90/360)\ }\end{array}
$$  

It is clear from the above calculations that the collar involves a (simple) borrowing cost at each payment date of either $K_{c a p}=10\%$ or $K_{F L}=8\%$ or $L I B O R_{T}$ if the latter is between $8\%$ and $10\%$ . The true efective borrowing cost requires the ‘up-front’ cost of the cap premium net of the receipts from the foor premium, to be taken into account. It is even possible to set the strike prices $K_{c a p}$ and $K_{F L}$ , so that the premium received from the sale of the foor equals the premium paid for the cap. This is a zero-cost collar.  

TABLE 38.3 Interest rate collar   


<html><body><table><tr><td>with collar with cap unhedged</td><td>Interest cost Per quarter Per annum 2.33% 2.40% 2.40%</td><td>9.65% 9.95% 9.96%</td><td colspan="7"></td></tr><tr><td rowspan="2">Date</td><td rowspan="2">Days in quarter</td><td rowspan="2">LIBOR</td><td rowspan="2">Interest due</td><td rowspan="2">Cap payment</td><td rowspan="2">Floor payment</td><td rowspan="2">Principal repayment</td><td colspan="3">Net cash flow</td></tr><tr><td>With collar only </td><td>With cap only</td><td>Unhedged</td></tr><tr><td>10-Apr-00</td><td></td><td>10.5</td><td>0</td><td>-350,000</td><td>500,000</td><td>0</td><td>100,150,000</td><td>99,650,000</td><td>100,000,000</td></tr><tr><td>10-Jul-00</td><td>91</td><td>11.5</td><td>2,654,167</td><td>0</td><td>0</td><td>0</td><td>-2,654,167</td><td>-2,654,167</td><td>-2,654,167</td></tr><tr><td>10-Oct-00</td><td>92</td><td>10</td><td>2,938,889</td><td>383,333</td><td>0</td><td>0</td><td>-2,555,556</td><td>-2,555,556</td><td>-2,938,889</td></tr><tr><td>10-Jan-01</td><td>92</td><td>9</td><td>2,555,556</td><td>0</td><td>0</td><td>0</td><td>-2,555,556</td><td>-2,555,556</td><td>-2,555,556</td></tr><tr><td>10-Apr-01</td><td>90</td><td>7.8</td><td>2,250,000</td><td>0</td><td>0 -50,556</td><td>0 0</td><td>-2,250,000</td><td>-2,250,000</td><td>-2,250,000</td></tr><tr><td>10-Jul-01</td><td>91</td><td>7.7</td><td>1,971,667</td><td>0</td><td>-76,667</td><td>100,000,000</td><td>-2,022,222</td><td>-1,971,667</td><td>-1,971,667</td></tr><tr><td>10-Oct-01</td><td>92</td><td></td><td>1,967,778</td><td>0</td><td></td><td></td><td>-102,044,444</td><td>-101,967,778</td><td>-101,967,778</td></tr></table></body></html>  

The efective borrowing cost with the collar depends on the particular outcome for LIBOR at each reset date. An illustrative outcome is given in Table 38.3 for:  

$$
\begin{array}{l l l l}{{Q=\S100\mathrm{m}}}&{{\:\:}}&{{C=\S350,000}}&{{\:\:}}&{{P=\S500,000}}\\ {{K_{c a p}=10\%,}}&{{\:\:}}&{{K_{F L}=8\%}}&{{\:\:}}&{{90\mathrm{-dayLIBOR}}}\end{array}
$$  

The loan is for $\$1000$ and the interest rate on 10 April-00 is $10.5\%$ . The cap costs $C=$ $\$500,000$ and the written foor provides an immediate cash infow of $P=\$350,000$ . Given the path of LIBOR assumed in Table 38.3, the cap is only exercised on 10 July-00 when $L I B O R=$ $11.5\%$ and the caplet payout of $\$383,333$ is received on 10 October-00.  

The foor is exercised on 10 April-01 and 10 July-01, when LIBOR falls below $K_{F L}=8\%$ to $7.8\%$ and $7.7\%$ respectively (and payments are 90 days later). The interest paid on the corporate’s loan at each reset date is based on LIBOR, 90 days earlier (column 4). The net cash fow to the corporate is given for the following three scenarios:  

• With collar – Table 38.3, column 8   
• With cap (only) – Table 38.3, column 9   
• Unhedged – Table 38.3, column 10  

The efective cost of borrowing (i.e. internal rate of return) for the unhedged strategy is $9.96\%$ whereas that for the collar is lower at $9.65\%$ . The important fact is that the collar limits the interest cost, should interest rates rise (above $10\%$ ) and the receipt of the put (foor) premium ofsets some of the cost of the cap. However, as interest rates fall (below $K_{F L}=8\%$ ) the short put involves a cash payout by the corporate, which ofsets the lower interest payments on the company’s bank loan. Thus the efective cost of hedging with the collar depends on the actual course of interest rates, until the expiration date of the collar.  

If only a cap had been used then the efective cost of borrowing would have been $9.95\%$ only just below the unhedged cost of $9.96\%$ . This is because the cost of the cap is not ofset by any future high cash payouts from the cap or by su\$ciently low borrowing rates on the loan – given the path of interest rates we have chosen.  

# 38.6 SUMMARY  

• Call options on T-bonds and T-bond futures can be used to set a maximum purchase price for the underlying bond or bond future at expiration of the option, but you can also take advantage of low cash market prices should these occur. Similarly a put on T-bonds or T-bond futures can be used to set minimum selling prices for the T-bonds you already own but also allows you to take advantage of high T-bond prices should they occur in the future.  

• A corporate with an outstanding LIBOR loan might buy an interest rate call (caplet) to provide insurance (i.e. maximum efective interest rate payable) but it also allows the corporate to take advantage of lower cash market interest rates should these occur in the future.   
• An interest rate put (foorlet) might be used by a corporate who has funds in a (foating rate) deposit and fears a fall in interest rates in the future. It ‘locks in’ a minimum efective rate that will be paid on its bank deposit in the future. It also allows the corporate to take advantage of high deposit rates in the future, should they occur.   
• A cap is used to protect against rising interest rates on a series of future loan payments. A cap is a series of individual caplets which each mature on dates corresponding to interest rate reset dates on a loan.   
• A corporate with a series of cash infows from funds held on deposit would lose from a future fall in rates. Similarly a bank which receives foating rate payments on its loans would lose from a fall in rates. To obtain a minimum efective rate on future cash infows based on LIBOR, while also benefting from any rise in rates, you would buy a foor.   
• A collar consists of an existing LIBOR bank loan, then buying a cap (with a high strike price) and selling a foor (with a low strike price). This establishes both a ceiling and a foor on the efective borrowing costs for the corporate.  

# EXERCISES  

# Question 1  

Explain how a European cap on 90-day LIBOR, with caplets which expire in 9 months and 1 year, and a strike of $K_{c}$ is similar to an interest rate call option. Explain who might use this cap.  

# Question 2  

You already have a bank deposit of $\$100$ at a 90-day LIBOR foating rate. Explain how you can protect the future receipts from your bank deposit by using an interest rate foor with strike, $K_{F L}$ . Explain the outcomes at an interest rate reset date.  

# Question 3  

You have a LIBOR foating-rate bank loan. Explain how a collar can be used to mitigate interest rate risk. Explain with reference to outcomes at an interest rate reset date.  

# Question 4  

You are pricing a cap on LIBOR with caplets expiring at the end of year-1, year-2, and year-3.   
Intuitively, what variables might infuence the price of the cap. Briefy explain.  

# Question 5  

What is the key diference between an FRA and a caplet? Explain with reference to holding a bank loan on which you pay LIBOR and then either taking a position in an FRA or in a caplet.  

Explain with reference to outcomes at an interest rate reset date.  

# Question 6  

On 1 June 2000, BigCorp takes out bank loan of $\$100$ at 90-LIBOR, with maturity date 1 June 2001 (when the principal is repaid). The current 90-day LIBOR rate is $10\%$ p.a. At the same time BigCorp buys an interest rate cap (on 90-day LIBOR) with a strike rate $K_{c}=10\%$ at a premium of $\$15,000$ .  

LIBOR turns out to be $10.5\%$ on 1 September $\dot{}+92$ days) $10.8\%$ on 1 December $_{+91}$ days) and $11\%$ on 1 March 2001 $_{+90}$ days). The cap payof and loan interest payments use actual/360, day-count convention.  

(a) Calculate the interest cost of the loan for each 3-month period.   
(b) Calculate the cash fows from the cap for each 3-month period.   
(c) Calculate net cash fows from the loan cap for each 3-month period.   
(d) Calculate the efective annual cost of (i) the loan (ii) loan $^+$ cap (using the internal rate of return IRR of the cash fows with and without the cap).  

You may fnd it useful to use Excel for the calculations and fll in the entries in the following table.  

<html><body><table><tr><td>Date</td><td>Days in quarter</td><td>LIBOR</td><td>Interest due</td><td>Cap</td><td> Principal</td><td>With cap</td><td>Without cap</td></tr><tr><td>01.06.00</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>01.09.00</td><td>92</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>01.12.00</td><td>91</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>01.03.01</td><td>90</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>01.06.01</td><td>92</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>  

# Question 7  

Assume the stochastic behaviour of the short-term interest rate (90-day LIBOR) can be represented as:  

$$
r_{t+1}=r_{t}+\lambda(w-r_{t})\mathrm{dt}+\sigma\sqrt{d t}\varepsilon_{t}\qquad\varepsilon_{t}\mathrm{is}n i i d(0,1).
$$  

Current interest rate $r_{1}=10\%$ , volatility of interest rates $\sigma=0.007$ p.a. and the long-run equilibrium interest rate, $\omega=8\%$ The rate of mean reversion $\lambda=0.02$ (per period) and the time-step chosen is $d t=0.01$ (years, approximately 3.5 days).  

Using MCS, outline the steps required to calculate the price of a caplet (on 90-day LIBOR) with maturity $T=1$ year and strike $K=10\%$ p.a.  