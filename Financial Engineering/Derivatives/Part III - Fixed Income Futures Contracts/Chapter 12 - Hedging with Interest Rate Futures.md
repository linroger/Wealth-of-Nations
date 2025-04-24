---
tags:
  - bank_loans
  - eurodollar_contract
  - fixed_income
  - hedging
  - interest_rate_futures
  - t_bills
aliases:
  - Chapter 12
  - Futures Contracts
  - Hedging Strategies
  - Interest Rate Futures
key_concepts:
  - 90-day Eurodollar contracts
  - 90-day T-bill contracts
  - Bank deposit hedging
  - Duration-based hedge ratio
  - Floating rate bank loans
  - Hedging fixed income assets
  - Interest rate futures
  - Locking in future rates
  - Price value of basis point
  - Strip, rolling, stack hedges
---
# Hedging with Interest Rate Futures  

# Aims  

• To examine how interest rate futures can be used for either hedging the value of fxed income assets (e.g. the dollar value of a portfolio of T-bills), or to ‘lock in’ future borrowing or lending rates (e.g. on existing foating-rate bank loans or deposits).   
• To use the ‘price value of a basis point’ (PVBP) and the ‘duration-based hedge ratio’ to determine the optimal number of futures contracts to hedge a cash-market position in a fxed income asset (e.g. T-bills, bank loan, or bank deposit).   
• To demonstrate the use of strip, rolling, and stack hedges.  

We show how interest rate futures contracts allow investors to hedge spot positions in cash market assets, such as T-bills, bank deposits, and loans. Interest rate futures are a little more complex than futures on, say, stocks or oil. But the key thing to remember is that the price of any interest bearing asset (e.g. spot T-bill prices, interest rate futures prices) always moves in the opposite direction to the change in interest rates (yields). So, for example, when yields fall, the futures price will rise (and vice versa). The futures contracts we consider are the (90-day) T-bill and (90-day) Eurodollar contracts, where the change in futures prices depends on the change in a 90-day (forward) interest rate.  

Interest rate futures can be used to lock in a known ‘efective’ interest rate over a specifc future time period. Consider the following situations:  

• It is 27 June. You have $\$100$ in a (dollar) bank deposit which pays 180-day LIBOR. The next interest rate reset date is in about 6 months’ time on 21 December. You fear a fall in interest rates over the next 6 months which means you will earn less interest on your deposits, when the (180-day) deposit rate is reset on 21 December.  

You can hedge this risk on 27 June, by going long (i.e. buying) a DecemberEurodollar futures contract (which matures a few days after 21 December). If interest rates fall, the December-Eurodollar futures price will rise between June and December. You can then close out (i.e. buy back) your December-futures on 21 December at a higher price, making a cash proft on your futures trades, which can then be used to compensate for the lower interest rate you will receive on your bank deposit (from 21 December over the next 180 days).  

• It is 27 July. You have a $\$100$ bank loan at a foating rate (based on 90-day LIBOR), with the next reset date on 21 September. You fear that interest rates will rise over the next 2 months so your borrowing costs will increase on 21 September. Today on 27 July, you hedge by shorting (i.e. selling) a September, T-bill futures contract (which matures towards the end of September). If interest rates rise over the next 2 months, the futures price will fall and you can close out (i.e. buy back) your September-futures contract at a proft on 21 September – which then ofsets the higher borrowing costs on your bank loan on 21 September.  

• It is 27 July and you know you will receive funds on 15 September which you want to invest in a (‘cash market’) 90-day T-bill. If spot interest rates fall over the next 2 months the price of your cash market T-bill will increase. So doing nothing is risky. However, today you can hedge against a rise in the price of the cash market T-bill by buying a ‘September T-bill futures’ on 27 July at an agreed price of $\mathrm{F}=98\mathrm{-no}$ money changes hands in July. If interest rates fall over the next 2 months then you can close out (i.e. sell your futures) on 15 September at a proft – which ofsets the higher cost of buying your ‘cash market’ T-bill.1  

# 12.1 NUMBER OF FUTURES CONTRACTS  

# 12.1.1 Three-month Eurodollar Contract  

To simplify matters, assume for the moment that yields for all maturities move together and by the same amount (i.e. parallel shift in the yield curve). We also ignore any distinction between discount rates and yields and avoid details of day-count conventions. As interest rates and futures prices move in opposite directions then:  

# Hedging using interest rate futures:  

• You have an existing loan at a foating rate (LIBOR). At the next reset date you fear a rise in interest rates. Today, you hedge by selling/going short interest rate futures contracts.  

• You have a bank deposit which pays LIBOR. At the next reset date you fear a fall in interest rates. Today, you hedge by buying/going long interest rate futures contracts.  

The number of futures contracts needed to hedge a cash market position can be found in two broadly equivalent ways:  

• Using the ‘price value of a basis point’ (PVBP).   
• Using a ‘duration-based hedge ratio’.  

12.1.2 Bank Loan at 6-month LIBOR: Single Payment  

It is 20 April $(t=0)$ and Ms A has an existing bank loan for $\$20$ , with interest payable based on 6-month (180-day) LIBOR and the next interest rate reset date is in 2 months’ time on 15 June (Figure 12.1). So the interest on the loan will be determined by the 6-month LIBOR rate on 15 June. The ‘exposure period’ is 2 months and the loan rate set on the 15 June applies over the 6 months between June and December. (Actual payment of the loan interest is on 15 December, $t=2.$ .)  

Ms A fears a rise in interest rates over the next 2 months, as her loan will then incur higher interest charges on 15 June. Since futures prices fall when interest rates rise, she can today (20 April) hedge by selling June-interest rate futures (with mature on 28 June, say). If interest rates do rise, she makes a gain on the futures when she closes out on 15 June (and buys back at a lower futures price). The proft from closing out the futures position ofsets the higher interest rate she has to pay on the loan for the period 15 June to 15 December.  

Suppose on 20 April the yield curve is fat so that interest rates at all maturities are equal. On 20 April if the 6-month (spot) interest rate is $y_{0}=7\%$ p.a. then the 3-month forward rate (beginning in June) is also $d_{f,0}=7\%$ p.a. On 20 April, the $6$ -month forward rate (which applies between 15 June and 15 December) is also $7\%$ p.a. (fat yield curve) and hence:  

Expected cost of borrowing between June and December $\cdot=\mathfrak{H}2\mathrm{m}(0.07)(1/2)=\mathfrak{H}70,000.$  

We hedge using the June-Eurodollar futures contract. The contract size is for ‘notional delivery’ of a $\$10$ deposit (with 3 months maturity). The quoted (June) IMM index is determined by the (90-day) forward (discount) rate $d_{f,0}=7\%$ p.a. (quoted on 20 April, which applies to the 3-month period between 15 June and 15 September)2:  

![](b85523932694191a298af426e0fdcc03f59dc36aa116d08028f2060fa3822d0a.jpg)  
FIGURE 12.1 Hedging 6-month bank loan using Eurodollar futures  

$$
I M M_{0}(J u n e)=100-d_{f,0}=93
$$  

If the forward discount rate changes by 1 bp $(=0.01\%$ p.a.), the change in the dollar value of one 3-month Eurodollar futures contract (i.e. ‘tick value’) is:  

$$
\mathrm{Tick\value:Eurodollar\futures}=\S1\mathrm{m}\times(0.01/100)\times(3/12)=\S25
$$  

Hence, if the IMM index changes from 93.0 to 93.01, (i.e. 1 bp) this implies a change in the value of the futures contract by $\$25$ . We are now in a position to hedge the next interest rate reset (on 15 June) for the $\$20$ loan, using the June-Eurodollar futures contract. On 20 April we fear a rise in interest rates over the next 2 months so we go short (sell) the June-futures contracts. One way of determining the number $N_{F}$ of futures contracts for the hedge is to use the concept of the ‘price value of a basis point’ (PVBP). For the bank loan, a change of 1 bp in the LIBOR rate will result in an increase in interest payments over 6 months of:  

$$
P V B P(6m l o a n)=\S2\mathrm{m}\left(0.01/100\right)\:\left(1/2\right)=\S100
$$  

So for every 1 bp increase in loan rates, interest payments on the $6$ -month loan will increase by $\$100$ .3 But a 1 bp increase in interest rates results in a change in value of one Eurodollar futures contract by $\$25$ (the tick value). Hence the number of futures contracts required for the hedge is:  

$$
N_{F}=\frac{P V B P(6m\ l o a n)}{P V B P(3m\ E u r o d o l l a r\ f u t u r e s)}=\frac{\S100}{\S25}=4\:\mathrm{contracts}
$$  

Suppose by 15 June (the 6-month) LIBOR rate increases to $y_{1}=8\%$ p.a. Since the June-futures is now close to maturity then the forward rate will be approximately equal to the June spot-rate so $d_{f,1}(i n J u n e)=8\%$ p.a. and therefore $I M M_{1}(i n J u n e)100-8=92$ . Since $I M M_{0}=93\$ the change in the IMM index is 100 ticks. The outcome of the hedge in June is:  

$$
{\begin{array}{l l l}{\mathrm{terest~cost~of~bank~loan~(June-Sept)~at~LIBOR}={\mathfrak{F}}2\mathrm{m~(0.08/2)~}=}&{{\mathfrak{F}}80,000}\\ {\mathrm{in~on~futures}=100\mathrm{~ticks}\times{\mathfrak{H}}\mathrm{5}\times4\mathrm{contracts}}&{=}&{{\mathfrak{F}}10,000}\\ {\mathrm{st~of~borrowing~less~gain~on~futures}}&{=}&{{\mathfrak{F}}7\mathbf{0},\mathbf{0}\mathbf{0}\mathbf{0}}\end{array}}
$$  

LIBOR rates rise from $7\%$ to $8\%$ between April and June which increases borrowing costs on the loan from $\$70,000$ to $\$80,000$ . But the cash proft on the 4 futures contracts of $\$10,000$ just ofsets the extra LIBOR cost, so the efective interest cost of borrowing is $\$70,000$ . The latter is the same interest cost we expected when we instituted the hedge in April, when the quoted (6-month) forward rate, which applied to the period June to December was $7\%$ p.a. We can also interpret the hedge in an equivalent way:  

$$
\begin{array}{l l}{{\mathrm{}}}&{{=100\mathrm{bps}\times\mathrm{PVBP}\left(\mathrm{=}\S100\right)\mathrm{\quad}=\S10,000}}\\ {{\mathrm{}}}&{{=100\mathrm{bps}\times\S25\times4\mathrm{contracts}\mathrm{\}=\S10,000}}\end{array}
$$  

So even though the 4 futures contracts are closed out, the hedge is efective. The futures hedge has ‘locked in’ a borrowing rate of $d_{f,0}=7\%$ , the forward rate which ‘lies behind’ the quoted IMM-index $(I M M_{0}=93\$ ), which is known on 20 April when we initiate the hedge.4  

Observant readers might have noticed that the loan interest is payable in December but the cash proft on the futures contract is paid out on 15 June. Hence the above fgures are not quite comparable. In fact the $\$10,000$ payout for the futures can be invested at $y_{1}=8\%$ between June and December giving $\$10,400,[=\S10,000\times(1+0.08/2)]-s0$ the hedge makes a small proft of $\$400$ in December (that is $0.02\%$ on $\$20$ , over 6 months).  

# 12.1.3 Duration Based Hedge Ratio  

An alternative way of determining $N_{F}$ , which does not require the explicit calculation of the PVBP, is to use a duration-based hedge ratio (see Appendix 12). The contract size for one Eurodollar futures contract is $\$10$ . The duration of a 6-month bank loan is $D(l o a n)=\mathrm{\Omega}^{1}/2$ year and the duration of the (notional) 3-month interest rate in the Eurodollar futures contract is $D(f u t u r e s)=1/_{4}$ year . The duration based hedge ratio for $N_{F}$ is:  

$$
N_{F}={\frac{V a l u e\ o f\ l o a n}{C o n t r a c t\ s i z e}}\Bigg[{\frac{D(l o a n)}{D(f u t u r e s)}}\Bigg]={\frac{{\mathbb{S}}2\mathrm{m}}{{\mathbb{S}}1\mathrm{m}}}\Bigg[{\frac{1/2}{1/4}}\Bigg]=4\ \mathrm{contracts}
$$  

Implicit in the above calculation is the assumption that the 3-month forward rate underling the futures contract, moves by the same (absolute) amount as the 6-month (LIBOR) interest rate on the loan. This may not be true. For example, if the 3-month rate (underlying the futures contract) moves by $1\%$ , the 6-month LIBOR rate on the bank loan might change by only $0.9\%$ (on average), so you need slightly less than 4 contracts in the hedge. We can express the relationship between the changes in these two interest rates in a regression equation:  

$$
\Delta y(l o a n r a t e)=\alpha+\beta_{y}(\Delta f)
$$  

This equation could be estimated using daily changes in the $6$ -month LIBOR rate regressed on daily changes in the 3-month forward rate – using the last 100 trading days of data, for example – to obtain an estimate of the regression slope, here $\beta_{y}=0.9$ . The estimate of the intercept $\alpha$ would probably be close to zero but is unimportant here, as it does not fgure in the hedge-ratio formula. So our ‘complete’ formula for the number of Eurodollar futures contracts to hedge a single future reset date for the LIBOR interest rate on the bank loan is:  

$$
N_{F}=\frac{V a l u e o f L o a n}{C o n t r a c t s i z e}\Bigg[\frac{D(l o a n)}{D(f u t u r e s)}\Bigg]\beta_{y}
$$  

Instead of using the contract size of $\$10$ for the (Eurodollar or T-bill) futures contract, a small amendment to the above equation is often used:  

$$
N_{F}=\frac{V a l u e\:o f l o a n}{V_{F}}\:\left[\frac{D(l o a n)}{D(f u t u r e s)}\right]\:\beta_{y}\:\:\mathrm{where}\:V_{F}=\S1\mathrm{m}(F_{0}/100)
$$  

$V_{F}$ is the ‘value of one futures contract’ (or ‘invoice price’ or ‘contract price’). For example, if the forward (discount) rate $d_{f}=2\%$ p.a. then $F_{0}=99.5$ and $V_{F}=\$99,500$ , which is close to the contract size of $\$10$ . Hence in most cases, using either of the above duration based formulas gives similar results.  

Note that using the above formulas will not in general produce a perfect hedge – this is because using ‘duration’ involves an approximation to price changes and also assumes shifts in the yield curve are always parallel. In addition, ‘beta’ is a (regression) estimate based on past data and hence may not accurately represent what happens when the hedge is over any future period.  

# 12.2 DIFFERENT TYPES OF HEDGE  

# 12.2.1 Strip Hedge  

Suppose it is 15 April and company-XYZ knows that it will borrow at 3-month LIBOR (i.e. the ‘tenor’ of each bank loan is 3 months), for the following dates and amounts (Figure 12.2):  

<html><body><table><tr><td>15 June</td><td>$40m (for 3 months)</td></tr><tr><td>10 Sept</td><td>$20m (for 3 months)</td></tr><tr><td>20 December</td><td>$30m (for 3 months)</td></tr><tr><td>Total future exposure</td><td>$90m</td></tr></table></body></html>  

On 15 April, suppose (spot) LIBOR rates for all maturities are $3\%$ p.a. and therefore all forward rates are also $3\%$ p.a. Company-XYZ fears a rise in the LIBOR yield curve in the future.  

![](24e9671a2674bf49f884c0f6b47bd7eec50bc576f5a3e864ff2b8abd62ea0958.jpg)  
FIGURE 12.2 Hedging 3-month loans at LIBOR using Eurodollar futures  

To cover the frst loan reset-date on 15 June, frm-XYZ on the 15 April will short (sell) $N_{F}=40$ June-contracts:  

$$
N_{F}=\frac{P V B P(3m\:l o a n)}{P V B P(f u t u r e s)}=\frac{\S40\mathrm{m}(0.0001)(1/4)}{\S25}=\frac{\S1.000}{\S25}=40\:\mathrm{contracts}
$$  

Alternatively, using Equation (12.6), the tenor of each of the loan interest payments is 3 months, so $D(l o a n)=\mathrm{\Omega}^{1}/4$ year and $D(f u t u r e s)=1/_{4}$ for the (3-month) Eurodollar futures contract, hence:  

$$
N_{F}=\frac{V a l u e\ o f l o a n}{C o n t r a c t s i z e}\left[\frac{D(l o a n)}{D(f u t u r e s)}\right]\beta_{y}=N_{F}=\frac{\S40\mathrm{{m}}}{\S1\mathrm{{m}}}\left[\frac{1/4}{1/4}\right]1=40^{5}
$$  

On 15 April company-XYZ will also sell 20 September-futures contracts and 30 Decemberfutures to cover the future $\$200$ and $\$300$ exposures – making a total of 90 contracts in all. This is a strip hedge – we match each loan reset-date with a futures contract which matures just after each reset-date. Because the yield curve is fat, this strategy will ‘lock in’ an efective interest rate on each of the bank loans of around $3\%$ p.a.  

On 15 June company-XYZ will buy back (close out) the 40 June contracts (leaving 20 September and 30 December contracts outstanding). Similarly on 10 September it will close out the 20 September-contracts (leaving 30 December-contracts outstanding) and on 20 December it will close out the remaining 30 December-contracts.  

If interest rates rise throughout the period then all the futures contracts will be closed out at a proft, and this proft will ofset the higher LIBOR loan rates at each of the 3-month reset dates. The efective cost of borrowing will be an average of the forward interest rates (quoted on 15 April), implicit in the June, September and December, quoted futures prices – that is, about $3\%$ p.a. Conversely, if interest rates fall, then closing out the futures involves a loss, but the interest costs of the loans will be lower – the result of the hedge is again to ‘lock in’ an efective cost of the loans, equal to the forward rate of about $3\%$ p.a.  

The strip hedge locks in an efective borrowing rate on the loan payments equal to the average of the forward rates (known on 15 April) in the contracts used. For example, if on 15 April $(t=0)$ the September-Eurodollar futures is quoted as $I M M_{0}(S e p t)=97$ then the hedge will lock in an efective borrowing rate between September and December of around $3\%$ p.a. (since $d_{f}(S e p t)=100-I M M_{0}(S e p t)=3\%$ . A similar argument applies to the outcomes from the other futures contracts used, so if the yield curve is fat the efective rate on each loan is $3\%$ p.a.6  

# 12.2.2 Stack Hedge  

If the ‘far’ December-futures contract is liquid, then you could hedge your interest rate resets on all future loan payments using only the December (far-dated) contract – this is often called a stack hedge.  

<html><body><table><tr><td>15 April</td><td>Sell (short) 9o December-contracts</td></tr><tr><td>15 June</td><td>Buy back 40 December-contracts</td></tr><tr><td></td><td>Retain 50 short December-contracts</td></tr><tr><td></td><td>(which cover the remaining reset dates/exposures)</td></tr><tr><td>10 Sept</td><td>Buy back 20 December-contracts</td></tr><tr><td></td><td>Retain 30 December-contracts (covers final exposure)</td></tr><tr><td>20 December</td><td>Buy back remaining 30 December-contracts</td></tr></table></body></html>  

# 12.2.3 Rolling Hedge  

If company-XYZ is worried about the lack of liquidity in the far dated contracts then it might use only the ‘nearby contracts’. This is called a rolling hedge. Here’s what happens in a rolling hedge with Eurodollar futures contracts.  

<html><body><table><tr><td>15 April</td><td>Sell 90 June-contracts</td></tr><tr><td>15 June</td><td>Buy back all 90 June-contracts</td></tr><tr><td></td><td>Sell 50 September-contracts (covers remaining reset dates/exposures)</td></tr><tr><td>10 Sept</td><td>Buy back all 50 September-contracts</td></tr><tr><td></td><td> Sell 30 December-contracts (covers final exposure)</td></tr><tr><td>20 December</td><td>Buy back all 30 December-contracts</td></tr></table></body></html>  

Note that in the rolling hedge you sell 90 (not 40) June-contracts on 15 April. You close out these 90 June-contracts on 15 June (because the contracts will expire soon after that date). On 15 June you then sell 50 September-contracts (these are now the ‘nearby contracts’) and close them out on 10 September, when you also then short 30 December contracts, which you close out on 20 December – when you take out the fnal bank loan $\$400$ on which you pay the 90-day LIBOR rate set on 20 December.  

On 15 April, interest rates for all maturities are $3\%$ . At frst sight it might look as if shorting and then closing out 90 (rather than 40) June-contracts involves too many contracts to hedge the June LIBOR rate on the $\$400$ bank loan (taken out in June). But consider a $1\%$ increase in all interest rates (for all maturities) from $3\%$ to $4\%$ , just before 15 June – and interest rates then stay at $4\%$ until after 20 December. Clearly, the proft on 40 of the 90 June-contracts cover the extra loan interest payments on the $\$400$ loan between June and September. But the proft on the other 50 June-contracts (which are realised on 15 June when you close out) are needed to cover the $1\%$ higher loan interest payments which will occur in September and December, as a result of interest rates remaining at $4\%$ between June and December. Hence, there is no additional proft when closing out the 50 September-contracts (on 10 September) and the 30 December-futures contracts (on 20 December) as interest rates remain at $4\%$ and hence the June-futures and September-futures prices remain constant after 15 June. But this is fne, as we have already covered the $1\%$ higher interest cost of the loan-resets in September and December, with the proft from the 50 (of the 90) June-contracts, that were closed out on 15 June.  

In the rolling hedge, the 50 September-contracts you sell on 15 June cover any further rises in LIBOR rates between June and September, above the $1\%$ increase that has already occurred in June. Similarly, the 30 December-contracts you sell on the 10 September, cover any further rises in interest rates between 15 September and 20 December.  

The transactions costs of the rolling hedge compared with the strip hedge might be higher because at each reset date, more contracts are being closed out in the rolling hedge than in the strip hedge. However, if the short dated (nearby) contracts are more liquid than the longer dated contracts (used in the strip hedge) then the transactions costs for the rolling hedge may be less per contract and the total transactions cost may also be less. This is a practical matter. However, note that Eurodollar futures contracts are very liquid for maturities out to 10–15 years, so a lower cost strategy using shorter-dated contracts and rolling the hedge really only applies if you are hedging interest rates on a loan with a maturity in excess of 15 years.7  

The rolling hedge has an additional risks. You close out all of your 90 June-contracts on 15 June when interest rates are $4\%$ p.a. and take a new position on 15 June by selling 50 September-contracts. Similarly, on the 10 September you sell 30 December-contracts. If interest rates increase between June and September from $4\%$ to $5\%$ (say), then the 50 September-futures contracts (sold in June) will cover this additional $1\%$ loan interest in September. But the 50 September futures you sold on 15 June (and that you buy back in September) will lock in an efective interest rate of $4\%$ p.a. (not $3\%$ p.a.) – the implicit forward rate on the September-futures contracts sold in June. A similar argument applies when you close out the December-futures.  

Roll-over risk can also work to your advantage. Suppose interest rates fall from $3\%$ to $2\%$ on 15 June and to $1\%$ on 10 September. When you sell your 50 September-futures (on 15 June) and your 30 December-futures (on 10 September), you lock in an efective interest cost on your bank loans of $2\%$ and $1\%$ , respectively.  

But a rolling hedge is more risky than a strip hedge. On 15 April, the strip hedge locks in an efective cost on all the loans of $3\%$ , no matter what happens to the path of interest rates in the future – this is because the strip hedge locks in the forward rate (of $3\%$ ) quoted for all maturities, on 15 April. However, the efective interest cost of the loans when using a rolling hedge depends on the future path of interest rates – if interest rates either rise or fall continuously from April to December then the rolling hedge will result in either a higher or lower efective cost of the loan than $3\%$ p.a. This is because you do not sell your 50 September-futures and 30 December-futures on 15 April but only on their roll-over dates of 15 June and 10 September (respectively), thus locking in the forward rates implicit in the futures prices at those dates.  

# 12.2.4 Basis Risk  

Of course, all of the above hedges have ‘basis risk’. The tenor of the loan interest payments may not exactly match the forward rate that determines changes in the IMM-index (futures) price. For example, a frm’s borrowing costs may be determined by the 6-month LIBOR and this may not change by the same (absolute) amount as the 3-month Eurodollar rate in the futures contract – this requires a regression to determine the interest rate beta as in Equation (12.5) and this is subject to estimation error.  

The rolling hedge is subject to roll-over risk as you do not know what futures prices will be after the frst reset date – and these determine the forward rates you lock in, in future periods. The stack hedge locks in the forward interest rate implicit in the December contract – that is, the forward rate which applies between December and the following March. But changes in the loan rate between April and June and June and September may not be the same as the change in the December–March forward rate, if shifts in the yield curve are not parallel.  

If we experience parallel shifts in the yield curve then each of the above hedges will produce broadly similar outcomes. But a rolling or stack hedge is highly vulnerable to a change in the slope of the yield curve. Hence, our earlier ‘strip hedge’ using futures with diferent maturity dates would provide a better hedge for non-parallel shifts in the yield curve, assuming long dated futures contracts are fairly liquid so that transactions costs are not too high.  

# 12.3 HEDGING: T-BILL AND EURODOLLAR FUTURES  

When hedging with US T-bill or Eurodollar futures we can either use the IMM index quote (as appears in the Wall Street Journal and on dealers’ screens) or the futures price $F$ . Our example is a cross-hedge. Suppose it is 15 May and the company CashRich has a $\$20$ bank deposit paying 6-month LIBOR, with the next interest rate reset date on 15 August (with interest actually paid on 15 February). The maturity (duration) of the 6-month bank deposit is $D_{s}={^1}/{2}$ (Figure 12.3). CashRich fears a fall in interest rates, which implies that the deposit account will earn less interest beginning on 15 August, for the next 6 months.  

A fall in rates implies a rise in futures prices, so on 15 May CashRich buys (goes long) September Eurodollar futures (i.e. with a maturity date closest to, but longer than the hedge period May–August). Any loss of interest on its bank deposit should be ofset by the cash gain when closing out the futures contracts. This is a cross-hedge because the 90-day interest rate underlying the Eurodollar futures contract is not the same tenor as the 180-day interest rate on the bank deposit.  

On 15 May:  

$$
F_{0}=100-(1/4)(100-I M M)=97.30\ \mathrm{(per\{}}
$$  

$$
\begin{array}{l l}{{V_{F}=\S1\mathrm{m}{(F_{0}/100)}}}&{{=\S973,000}}\\ {{f_{0}=[(100/97.3-1)4]}}&{{=\mathrm{11.1\%{(impliedforwardyield,simple~rate)}}}}\end{array}
$$  

On 15 May, the forward yield implied by the quoted September-IMM index (or futures price) is $f_{0}=11.1\%$ – this is the rate CashRich hopes to ‘lock in’ for 6 months beginning on 15 August, when the September-futures is closed out.  

# Number of futures contracts:  

The duration-based hedge ratio (assuming a parallel shift in the yield curve) is:  

$$
N_{F}=\frac{\S-D e p o s i t}{C o n t r a c t\ s i z e}\frac{D_{s}}{D_{f}}=\frac{\S2\mathrm{m}}{\S1\mathrm{m}}\left(\frac{0.5}{0.25}\right)=4
$$  

Between 15 May and 15 August assume that all interest rates fall (see Table 12.1) and CashRich only earns a yield of $y_{1}=9.6\%$ on its 6-month deposit. However, lower spot rates  

![](08c11c35b2525d7d6b47281494b550bb591ddb33749ba385fe2ec238183cb9f6.jpg)  
FIGURE 12.3 Hedging using Eurodollar futures  

TABLE 12.1 Cross hedge (US T-bill futures)   


<html><body><table><tr><td colspan="4">3-month US T-bill futures (September maturity)</td></tr><tr><td>Spot rates, 15 May (T-bill yields)</td><td>IMM Index</td><td>Futures price, F (per $100)</td><td>FVF = $1m(F/100)</td></tr><tr><td>May</td><td>y (6 months)= 11%</td><td>IMMg = 89.2</td><td>Fo= 97.30 $973,000</td></tr><tr><td>August</td><td>y1 (6 months)= 9.6% IMM = 90.3</td><td>F1 = 97.575</td><td>$975,750</td></tr><tr><td>Change -1.4%</td><td>1.10 (110 ticks)</td><td>0.28</td><td>$2,750 (per contract)</td></tr><tr><td colspan="4">Durations: Ds = 0.5, DF = 0.25. Amount to be hedged = $2m. Number of contracts Nf = 4 </td></tr></table></body></html>

Notes: We use spot T-bill yields $y,$ whereas in practice discount rates would be quoted and the yields would need to be derived from the discount rates.  

imply that the 3-month forward rate also falls and hence the IMM index and the futures price rise (see Table 12.1). The proft from closing out the futures ofsets the lower interest on the bank deposit, so the company earns an efective rate on its deposit of around $f_{0}=11.1\%$ .  

On 15 August:  

$$
{\begin{array}{l l l}{G a i n~o n~4f u t u r e s~c o n t r a c t s~=~({\mathfrak{H}}975,750-{\mathfrak{H}}973,000)~4}&{={\mathfrak{H}}11,000}\\ &{=~110{\mathrm{~ticks}}\times{\mathfrak{H}}25\times4{\mathrm{~contracts}}}&{={\mathfrak{H}}11,000}\end{array}}
$$  

Invest the futures proft of $\$11,000$ for 6 months (August–February) at $y_{1}=9.6\%$ p.a.  

$$
F u t u r e s~p r o f t s~i n v e s t e d f o r~6~m o n t h s=\S11,000~[1+(0.096/2)]=\S11,528
$$  

The proft on the futures is equivalent to $\$23,056$ over 1 year, hence:  

Efective simple annual rate earned bank deposit $=y_{1}+(\S23,056/\S2\mathrm{m})$ $=0.096+0.0115=0.1075\left(10.75\%\right)$  

Alternatively, we have:  

$$
{\begin{array}{r l r}&{\mathrm{:treceived~over~6~months~on~bank~deposit=\mathbb{S}2m~(0.096/2)~=~\mathbb{S}96,000}}&\\ &{\mathrm{~Yom~futures~(after~6~months~on~deposit)}}&{=~\S11,528}\\ &{\mathrm{~\mathbb{e}c e i v e d~o v e r~6~m o n t h s}}&{=~\S107,528}\\ &{\mathrm{~ver~1~year~(\times2)~}}&{=~\S215,056}\\ &{\mathrm{ive~interest~\mathbb{P}.a.(d e p o s i t+f u t u r e s~p r o f t)}=\S215,056/\S2\mathrm{m}}&{=~\Im0,75\%..}\end{array}}
$$  

The $10.75\%$ hedged return is substantially above the unhedged rate $y_{1}=9.6\%$ and is reasonably close to the implied (simple) yield on the September-futures contract of $f_{0}=11.1\%$ .  

The hedge is not perfect because shifts in the yield curve may not be parallel and the contract is closed out on 15 August, well before its September maturity date.  

We can look at the hedge in a slightly diferent way by working out the loss of interest received on the bank deposit on 15 August, relative to the interest rate we expected to earn, which is given by the implied forward rate $f_{0}=11.1\%$ on 15 May8:  

Loss of interest receipts -month bank deposit $=11.1\%,y_{1}=9.6\%=82\mathrm{m}\left[0.111-0.096\right](1/2)=815.000$ l $o s s=L o s s$ bank deposit Gain futur $\dot{s}=\mathfrak{H}15,000-\mathfrak{H}11,528=\mathfrak{H}3,472$  

Had the company remained unhedged then the loss of interest would have been $\$15,000$ rather than the hedged loss of $\$3,472$ (which is only $0.17\%$ of the $\$20$ deposit).  

# 12.4 EURODOLLAR STACK HEDGE  

The Eurodollar futures contract with maturities extending out to about 20 years are some of the most actively traded interest rate futures contracts, the reason being the demand by various types of hedger particularly swaps dealers. Short-term contracts are more liquid but there is considerable liquidity in the market out to 10 years maturity. Any fnancial institution or corporate paying or receiving a foating rate (LIBOR) might wish to hedge using Eurodollar futures. Consider the following situations:  

• Bank-A has issued a 5-year $4\%$ fxed rate loan of $\$1000$ , fnanced by $\$1000$ of foating rate (LIBOR) deposits (from Citibank), with deposit rates reset every 3 months and currently equal to $3\%$ p.a. (for all maturities).   
• Bank-B has issued 10-year foating rate loans of $\$1000$ based on 180-day LIBOR and fnances these by bidding for foating rate deposits of $\$1100$ (from Citibank) based on 90-day LIBOR.   
• A corporate (McTrump) with a 5-year, $\$1000$ principal, foating rate (LIBOR) loan with Citibank, with rate resets every 3 months.  

Bank-A is currently earning a spread of $1\%$ $(=4\%$ fxed on its loans, fnanced by LIBOR foating-rate deposits currently at $3\%$ p.a.). But if LIBOR deposit rates rise in the future by more than $1\%$ it will make a loss. Now consider Bank-B whose receipts and payments are both at a foating rate (based on LIBOR). But Bank-B has net foating rate payments of $\mathfrak{S}10\mathrm{m}\left(=\mathfrak{H}110\mathrm{m}-\mathfrak{H}100\mathrm{m}\right)$ . It is therefore vulnerable to a rise in the general level of interest rates and also to a change in the spread between 180-day and 90-day LIBOR rates. McTrump borrowed $\$1000$ at a foating rate and is vulnerable to a future rise in interest rates.  

Note that in all cases the participants are vulnerable over several periods since the foating rate payments are reset periodically. Today, these positions can be hedged by shorting Eurodollar futures.  

# 12.4.1 Corporate Borrowing: Stack Hedge  

Let us consider the case of a company (McTrump) on 1 May $\mathbf{\Psi}(t=0)$ which has a foating rate loan of $\$100$ with resets every 30 days, the next is in June, followed by another in July and the principal is repaid in August (see Figure 12.4).9  

The current (30-day) LIBOR rate in May is $L_{0}=10\%$ p.a. (simple rate). The day-count convention for (USD) LIBOR is actual/360. For simplicity assume that on 1 May there is a fat term structure, so that quoted forward rates beginning in June and August are also $10\%$ (simple interest). The out-turn values for future LIBOR rates and futures prices are given in Table 12.2A. We use the September-futures to hedge the next two interest rate resets – this is a stack hedge.  

McTrump expects to pay $\$100,L_{i}$ (30/360) each month. Since the (simple) forward rates for June and July are also $10\%$ p.a., the expected compound annual rate McTrump is trying to ‘lock in’ is:  

$$
E x p e c t e d f u t u r e\ l o a n r a t e\left(c o m p o u n d\right)=\left[1+0.10\left(\frac{30}{360}\right)\right]^{\frac{365}{30}}-1=0.1062
$$  

![](1c88856e680d69e9944ca7d585947b5c8d32382947f4e29d09f5925abdeaaa0a.jpg)  

TABLE 12.2A Eurodollar futures, stack hedge   


<html><body><table><tr><td></td><td>t = 0 (1 May)</td><td>t = 1 (June)</td><td>t = 2 (July)</td></tr><tr><td>LIBOR rates (simple)</td><td>Lo= 10%</td><td>L = 10.50%</td><td>L = 11%</td></tr><tr><td>Spot rates (compounded)</td><td>Yo = 10.62%</td><td>Y = 11.18%</td><td>Y = 11.74%</td></tr><tr><td>Futures</td><td>dfo = 9.76%</td><td>df1 = 10%</td><td>df2 = 10.40%</td></tr><tr><td rowspan="3"></td><td></td><td></td><td></td></tr><tr><td>IMMg = 90.24 Fo= 97.56</td><td>IMM = 90.00</td><td>IMM2 = 89.60</td></tr><tr><td></td><td>F = 97.50</td><td>F2 = 97.40</td></tr><tr><td>Implied forward rate (compounded rates)</td><td>fo= 10.54%</td><td>f = 10.81%</td><td>f = 11.28%</td></tr></table></body></html>

Notes: The LIBOR day count convention is actual/360. The tick value for IMM index is $\$25,F$ is the futures price per $\$100$ and the contract size is $\$1m$ .  

The quoted (simple) LIBOR rates $L_{i}$ correspond to compound rates $y_{i}=$ $[1+L_{i}(30/360)]^{365/30}-1$ . On 1 May the September-futures price $F_{0}=97.56$ and therefore the (compound) forward rate is $f_{0}=(100/97.56)^{365/90}-1=10.54\%$ p.a. The loan rate is reset every month so $D_{s}=1/12$ and for the 90-day Eurodollar futures contract $D_{f}=1/4$ , hence:  

$$
N_{F}=-\frac{L o a n}{C o n t r a c t~s i z e}\frac{D_{s}}{D_{f}}=-~\frac{\S10\mathrm{m}}{\S1\mathrm{m}}\left(\frac{\left(1/12\right)}{\left(1/4\right)}\right)=-3.33^{10}
$$  

To hedge interest payments for both the June and July reset dates using a stack hedge, we require $N_{F}=-6.67$ , that is, on 1 May we short 7 September-futures contracts. On 1 May, 30-day LIBOR is $L_{0}=10\%$ p.a. and the loan outstanding on 1 June is:  

$$
\mathfrak{H}10\mathrm{m}\left[1+0.10\frac{30}{360}\right]=10,083,333
$$  

However, between 1 May and the June reset date, the rise in LIBOR from $10\%$ to $10.5\%$ results in a fall in the IMM-index by 24 ticks. In June we need a short position in three  

$$
N_{F}=-\frac{L o a n}{C o n t r a c t~S i z e}\frac{D_{s}}{D_{f}}\left(\frac{(1+f_{0})}{(1+y_{0})}\right)=-~\left(\frac{(1/12)}{(1/4)}\right)~\frac{\S10m}{\S1m}~\frac{(1.1054)}{(1.1062)}=-3.33
$$  

The additional term $(1+f_{o})/(1+y_{0})$ occurs because we use compound rates rather than continuously compounded rates – omitting this term makes little diference.  

September-futures to hedge the second interest rate reset in July.11 Hence at $t=1$ (June), we buy back four futures contracts (Table 12.2B):12  

Proft futures $\left(\mathrm{in~June}\right)=4\left(I M M_{1}-I M M_{0}\right)\S25\ =\ \S2{,}400$ Reduce loan outstanding to 10 083 333 2 400 \$10 080 933  

<html><body><table><tr><td>TABLE12.2B</td><td colspan="2">Eurodollar futures, hedge outcome</td></tr><tr><td>At t = 1 (June)</td><td>Amount owing spot = $10m(1+0.1(30/360))</td><td>= $10,083,333</td></tr><tr><td></td><td>Buy back 4 futures contracts:</td><td></td></tr><tr><td></td><td>Profit on futures = 4($1m)(F - Fo)/100 = 4 x 600</td><td></td></tr><tr><td></td><td>Or =4×(IMM-IMM)×$25</td><td>= $2,400</td></tr><tr><td></td><td>= 4 ×24 ticks × $25</td><td>= $2,400</td></tr><tr><td></td><td>Reduce loan outstanding to $10,083,333 - $2,400 L = 10.5%, rate reset in June</td><td>= $10,080,933</td></tr><tr><td>At t = 2 (July)</td><td>Amount owing spot = $10,080,933(1+0.105(30/360))</td><td></td></tr><tr><td></td><td></td><td>= $10,169,141</td></tr><tr><td></td><td>Buy back remaining 3 futures contracts: Profit on futures = 3($1m)(F- F2)/100 = 3 × 1,600</td><td>= $4,800</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td>Or = 3×(IMM- IMM)×$25</td><td></td></tr><tr><td></td><td>= 3x64 ticks × $25</td><td>= $4,800</td></tr><tr><td></td><td>Reduce loan outstanding to $10,169,141 - $4,800</td><td>= $10,164,341</td></tr><tr><td>At t = 3 (August)</td><td>L = 11%, rate reset in July</td><td></td></tr><tr><td></td><td>Amount owing spot = $10,164,341(1+0.11(30/360)</td><td>= $10,257,514</td></tr><tr><td></td><td>Corporate borrowed $10m and paid back $10,257,514 after 3 months:</td><td></td></tr><tr><td></td><td>Effective loan rate (compound) = ($10.257m / $10m)4 - 1 = 10.7% p.a.</td><td></td></tr><tr><td></td><td>The 10.7% is only 8 bps above the target rate of 10.62% the corporate</td><td></td></tr><tr><td></td><td>was hoping to achieve on 1 May. Had the corporate not hedged, the</td><td></td></tr><tr><td></td><td>annual compound rate would have been:</td><td></td></tr><tr><td></td><td>[(1 +0.1/12)(1 + 0.105/12)(1 + 0.11/12)]4 - 1 = 11.02%</td><td></td></tr><tr><td></td><td>which is 40 bps above the target rate of 10.62%.</td><td></td></tr></table></body></html>  

By July, LIBOR has again increased by a further $0.5\%$ to $11\%$ and the IMM-index has fallen 40 ticks $(=89.6-90)$ ), so the proft on the 3 remaining futures contracts is:  

which again is used to reduce the principal of the loan. The July LIBOR rate of $11\%$ determines the last loan interest payment, resulting in an outstanding balance in August of $\$10,257,514$ . This gives an efective borrowing rate of $10.7\%$ p.a. which is only 8 bps above the target rate of $10.62\%$ the corporate was trying to lock in at $t=0$ . Without the hedge, the corporate would have paid LIBOR rates of $10\%$ , $10.5\%$ , and $11\%$ in June, July, and August (respectively) resulting in an unhedged cost of $11.02\%$ , which is 40 bps above the target rate of $10.62\%$ .  

# 12.5 SUMMARY  

• Hedging fxed income positions in the cash market is based on the inverse relationship between (forward) interest rates and futures prices.   
• At $t=0$ , a hedger can ‘lock in’ the (implied quoted) forward rate $f_{12}$ applicable between any two future periods $t=1$ and $t=2$ , by taking a position in futures contracts today. These futures contracts are (usually) closed out before the maturity date (at $t=1$ ).   
• Alternatively, a futures hedge can be viewed as trying to match any increase in interest payments on a bank loan or any fall in interest receipts on a bank deposit, with profts/losses on the futures position.   
• If you already have or are planning to take out a bank loan at a foating interest rate (LIBOR) in the future, then you can hedge any future rise in LIBOR by today, shorting (selling) interest rate futures contracts. If interest rates rise, the futures price falls and you buy back (close out) the futures contract at a lower price – the proft on the futures contract ofsets the higher interest cost of the bank loan.   
• Conversely, if you have a bank deposit which pays a foating interest rate (LIBID), or are planning to deposit funds in the future, then you should hedge any future fall in deposit rates by today, going long (buying) an interest rate futures contract. If interest rates do fall, the futures price rises and you sell (close out) the futures contract at a higher price – the proft on the futures contract ofsets the lower interest rate payable on the bank deposit.   
• The optimal number of futures contracts is determined by applying either the ‘price value of a basis point’ (PVBP), or using the duration based hedge ratio. The number  

of (Eurodollar) futures contracts required to hedge each reset date (using the duration based hedge ratio) is:  

$$
N_{F}=\left({\frac{\S C a s h\ M a r k e t}{V_{F}}}\right)\left[\frac{D_{s}}{D_{f}}\beta_{y}\right]\approx\left({\frac{\S C a s h\ M a r k e t}{\S1m}}\right)\left[\frac{D_{s}}{D_{f}}\beta_{y}\right]
$$  

where $V_{F}=\mathfrak{F}1\mathrm{m}(F_{0}/100)$ , $F_{0}=$ futures price, $D_{s}=$ duration of the spot cash market position, $D_{f}=$ the duration of the ‘underlying’ in the futures contract. Beta $\beta_{y}$ is obtained from a regression of the change in the spot (cash-market) interest rate (e.g. 6-month LIBOR) on the change in the forward rate (underlying the futures) contract (e.g. 90-day Eurodollar rate). The above formula is often simplifed by replacing $V_{F}$ with the contract size of the Eurodollar futures contract, namely, $\$10$ .  

• To hedge a series of interest rate reset dates (on a bank loan or bank deposit) you can use a strip hedge, rolling hedge, or stack hedge. The strip hedge locks in the diferent forward rates implied by the diferent maturity futures contracts used in the hedge – each of which matures (just) after each reset date. The rolling hedge and stack hedge carry more ‘basis risk’, particularly if there are non-parallel shifts in the yield curve.  

# APPENDIX 12: HEDGE RATIOS  

The duration based hedge ratio for fxed income assets can be derived in a number of diferent ways.  

$S=$ price of the spot cash market asset to be hedged e.g. price of T bills held $V_{s}=$ total $\$1$ amount in cash market at $t=0$ e.g. principal on bank loan $y_{s}=$ yield on cash market asset e.g. bank interest rate $F=$ price of a short term interest rate futures contract per $\$100$ nominal Note this is not the IMM index $z=$ contract size $(=\$10$ for T bill and Eurodollar futures $V_{F}=\mathbb{\mathbb{S}}1\mathrm{m}(F/100)=$ value of one futures contract ‘invoice price’ $N_{F}=$ number of futures contracts in the hedge  

# Using Calculus  

Suppose you have a bank deposit of $(V_{s}>0)$ or bank loan $(V_{s}<0)$ based on (spot) yields $(y_{s})$ with resets every 6 months. The change in interest receipts (payments) over 6-months is $d V_{s}=V_{s}(d y_{s}/2)=V_{s}D_{s}d y_{s}$ where $D_{s}=1/2$ is the duration of a 6-month deposit or loan. The  

change in interest cash fows on the deposit or loan, plus the gain or loss on $N_{F}$ (Eurodollar or T-bill) futures contracts is:  

$d V=\$1$ -change in cash market position $+\$8$ -change in futures position  

$$
\begin{array}{r l}{}&{=V_{s}D_{s}d y_{s}+N_{F}[(F_{1}-F_{0})/100]\ z}\\ {}&{=V_{s}D_{s}d y_{s}+N_{F}(z F_{0}/100)(d F/F_{0})}\\ {}&{=V_{s}(D_{s}d y_{s})+N_{F}V_{F}(-D_{f}\ d f)}\end{array}
$$  

where $V_{F}=z F_{0}/100$ is the face value of one futures contract and $z=\$10$ contract size. Using $F=100/(1+f(90/360))$ we have $d F/F\approx-d f(90/360)=-D_{f}$ df. (For continuously compounded rates the latter expression is exact, rather than an approximation.) Setting $d V=0$ gives:  

$$
N_{F}=\left(\frac{V_{s}}{V_{F}}\right)\frac{D_{s}}{D_{f}}\beta_{y}\quad\left(V_{s}>0\mathrm{for}\mathrm{bank}\mathrm{depositand}V_{s}<0\mathrm{for}\mathrm{bank}\mathrm{loan}\right)
$$  

where $\beta_{y}$ is the OLS coe\$cient in the regression: $\Delta y_{s}=\alpha+\beta_{y}\Delta f.$ . A simplifcation of (12.A.2), which works well in practice, is to replace $V_{F}$ with the ‘contract size’ of $\$10$ .  

If you are hedging a long position $V_{s}>0$ in cash-market T-bills (rather than a bank deposit) then the change in the value of the hedge portfolio is:  

$$
\begin{array}{r l}{}&{=V_{s}R_{s}+N_{F}V_{F}(-D_{f}d f)}\\ {}&{=V_{s}(-D_{s}d y_{s})+N_{F}V_{F}(-D_{f}d f)}\end{array}
$$  

where $R_{s}\equiv d S/S$ is the proportionate price change of the T-bill (i.e. the holding period return on the T-bill), which we assume is adequately approximated by $R_{s}\equiv d S/S=-D_{S}d y_{s}$ . Setting $d V=0$ gives:  

$$
N_{F}=-\left(\frac{V_{s}}{V_{F}}\right)\frac{D_{s}}{D_{f}}\beta_{y}
$$  

Hence, if you currently hold (are long) cash market T-bills $(V_{s}>0)$ then (12.A.4) implies you hedge by selling $(N_{F}<0)$ ) interest rate futures contracts, today.  

# Compound Rates  

Strictly speaking the above formulas for $N_{F}$ use continuously compounded yields. When using compound yields, the duration approximations are $d S/S=-D_{s}d y_{s}/(1+y_{s})$ and  

$d F/F=-D_{f}\ d f/(1+f)$ Hence, using compound yields the correct formula is:  

$$
N_{F}=\frac{V_{p}}{V_{F}}\left[\frac{D_{s}\ (1+f)}{D_{f}(1+y_{s})}\right]\beta_{y}
$$  

This correction usually makes little diference in practice.  

Minimum Variance  

Alternatively, we can choose $N_{F}$ to minimise the variance of $d V$ . From (12.A.1):  

$$
\sigma_{d V}^{2}=V_{s}^{2}D_{s}^{2}\sigma_{d y_{s}}^{2}+(N_{F}V_{F})^{2}D_{f}^{2}\sigma_{d f}^{2}+2V_{F}N_{F}D_{s}D_{f}\sigma_{d y_{s},d f}
$$  

Diferentiating (12.A.6) with respect to $N_{F}$ , setting the resulting expression to zero and rearranging gives Equation (12.A.2) for $N_{F}$ , where $\beta_{y}=\sigma_{d y_{s},d f}/\sigma_{d f}^{2}$ is the OLS coe\$cient in the regression $\Delta y_{s}=\alpha+\beta_{y}\Delta f$ .  

# Hedging Portfolio of Cash-Market T-bonds Using T-bond Futures  

It is convenient to include this here even though we do not discuss T-bond futures until Chapter 13. The only additional complication is that the trader who is short a T-bond futures has a restricted choice on which bond to deliver. Hence, the formula for the number of futures contracts in the hedge, includes the ‘conversion factor’ $C F_{C T D}$ of the ‘cheapest to deliver bond’:  

$$
N_{F}=\frac{V_{p}}{V_{F}}\left(\frac{D_{s}}{D_{f}}\right)\beta_{y}C F_{C T D}
$$  

# EXERCISES  

# Question 1  

It is 1 January and you expect to receive $\$100$ in 2 months’ time which you wish to place in a bank deposit for a further 5 months, on which you will receive LIBOR.  

Explain what Eurodollar futures contract you would use to hedge your cash (spot) market position. What are the risks in the hedge you have chosen?  

# Question 2  

Explain whether you would undertake a long or short Eurodollar futures hedge if you plan to borrow money in 2 months’ time (at the then prevailing 180-day LIBOR rate).  

# Question 3  

In 3 months’ time you will issue $\$100$ (market value), 6-month commercial bills. After a further 3 months you will issue $\$200$ of 6-month commercial bills. You have decided to hedge your positions using Eurodollar futures contracts, with $F=99$ (per $\$100$ nominal) with a contract size of $\$10$ .  

Explain how you would hedge your position. What are the risks in the hedge?  

# Question 4  

It is 3 January 2019. On 2 January there was an interest rate reset on your existing $\$100$ bank loan, based on 180-day LIBOR. The next reset date is on 2 July 2019. The loan ends on 2 July 2020. The current Eurodollar futures price is $F=97$ (per $\$100$ nominal) for all maturities.  

How many futures contracts will you use to hedge the remaining interest rate payments and will you go short or long the futures contracts? Assume a parallel shift in the yield curve.  

# Question 5  

On 20 January a US Corporate Treasurer realises that she will issue $\$100$ (market value) of 180-day commercial paper on 25 June. The September-Eurodollar futures IMM index $=92.0\$ (contract size $\$10$ ). Today, how can she hedge her exposure to the new issue of commercial bills, on 25 June? How many futures contracts are required? Assume a parallel shift in the yield curve.  

# Question 6  

It is 15 March 2019 and today you take out a 5-year US dollar loan for $\$1.5\mathrm{m}$ with payments linked to 180-day LIBOR ( $+100$ bps). (The ‘tenor’ in the loan repayments is every 6 months).  

Carefully explain the steps you might take to hedge this position using a strip of (90-day) Eurodollar futures (contract size, $\$10$ ). What is the optimal number of futures contracts for each reset date?  

The current futures price is $F=\$99$ (per $\$100$ nominal). When the 90-day yield rises by $1\%$ then on average, the 180-day yield rises by $0.9\%$ .  

# Question 7  

On 20 February a US corporate treasurer realises she will have to borrow money on 17 July by issuing $\$50$ of commercial paper (market value $\$4,820,000$ with a maturity of 180 days.  

On 20 February the September-Eurodollar futures IMM index quote is $I M M=92.00.$ . The contract size is $\$10$ .  

How many futures contracts does she need to hedge against a possible rise in 180-da commercial paper rates between today and 17 July? Assume a parallel shift in the yield curve  