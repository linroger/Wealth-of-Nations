---
tags:
  - asset_swap
  - cross_currency_swap
  - equity_for_libor
  - equity_swaps
  - outperformance_swaps
aliases:
  - Asset Swap
  - Equity Linked Deposit
  - Equity Swap
  - Relative Performance Swaps
  - Two-index Swaps
key_concepts:
  - Asset swap description
  - Equity-for-LIBOR swap pricing
  - Gain market exposure
  - Low cost portfolio change
  - Value equity swap
---
# Equity Swaps  

# Aims  

• To demonstrate how equity swaps allow an investor to gain temporary exposure to the stock market without actually buying or selling the stocks in her existing portfolio. The investor can then revert to her original stock portfolio at the termination of the swap.   
• To describe how an ‘asset swap’ may involve a single equity, a basket of equities or a market index (e.g. S&P 500), either in the same currency or in diferent currencies – in the latter case the investor has to decide on whether to hedge the currency risk.   
• To use arbitrage arguments to price an equity-for-LIBOR swap. Somewhat counterintuitively receiving the return on equity and paying LIBOR is a fair swap, since the present values of the two legs are equal.   
• To show how to price a domestic equity-for-domestic equity swap, or a swap of the return on a domestic equity for the return on a foreign equity.   
• To demonstrate how to value an equity swap after inception of the swap. The value of an equity swap to one of the parties may be positive or negative and its value depends on the change in equity prices.  

Equity swaps allow an investor to change her existing stock market risk without necessarily owning stocks or changing the amount of stocks she already holds. An equity swap is an OTC transaction which involves cash fows based on a notional principal amount. One leg of an equity swap is based on the return on a specifc equity ‘portfolio’ such as a single stock, a basket of stocks or a stock index (e.g. S&P 500). The other leg of the swap often has cash fows based on an interest rate, either fxed or foating (LIBOR). The principal in the swap is not exchanged, hence the term ‘notional principal’. Often the notional principal is fxed over the life of the equity swap but some equity swaps have a variable notional principal.  

A ‘cross-currency equity swap’ involves two diferent currencies, for example a US-based investor swapping USD-LIBOR for the return on the FTSE 100 stock index. The currency risk in the swap can be hedged as part of the swap deal.  

An equity swap may also involve cash fows based on two diferent equity indices (i.e. ‘two-index swaps’ or ‘relative performance swaps’). There are also ‘outperformance swaps’ where the equity leg may involve the maximum return on two or more equity indices or two or more baskets of equities.  

Equity swaps can provide a low cost method of altering your current portfolio. Sometimes these cost savings arise from avoidance of withholding taxes or from reductions in transactions costs in illiquid markets or to get round certain market restrictions (e.g. short selling).  

For example, a US investor who directly buys foreign stocks may pay a withholding tax (of say $30\%$ ) on dividends received – but an equity swap on a total return index avoids such a tax. Direct purchase of stocks in emerging markets may involve high transaction cost and credit risk of the counterparty (e.g. local brokerage frm), whereas equity swaps provide a way to minimise such costs, while securing exposure to emerging markets. If you hold stocks in a company in which you work and these have increased in value, you may want to lock in this gain – to do so you can use an equity swap where from today, you pay the return on your company stocks and receive a fxed rate of interest (from the swap dealer).  

An ‘equity linked deposit’ ofers a foor to the value of your investment but also pays out a fraction of any upside on a market index (e.g. S&P 500) – this is a structured product. A bank can ‘structure’ this product by purchasing a put on the S&P 500 (which sets a foor) and also buying an equity swap to receive the return on the S&P 500 (and pay a fxed rate of interest).  

# 37.1 EQUITY-FOR-LIBOR: FIXED NOTIONAL PRINCIPAL  

Equity swaps allow a portfolio manager (Ms Bright) to alter their exposure to the equity market without owning or transferring the equities she already holds. For example, suppose Ms Bright is holding (long-maturity) foating rate notes (FRNs) with a principal of $Q={\mathfrak{S}}100{\mathrm{m}}$ and is normally quite happy with this portfolio. However, suppose she feels that the US stock market (S&P 500) will do rather better than usual over the next year and would like exposure of $\$500$ to the US stock market. After one year she feels the stock market rally will be over and then wishes to return to her long-run desired portfolio of $\$1000$ in FRNs.  

Ms Bright could accomplish this strategy by today (10 January) selling $\$500$ of her FRNs, switching into an S&P 500 tracker fund (or ETF) and then reversing these trades one year later. This might entail high transactions costs – brokerage fees, commissions, bid–ask spreads, adverse market impact on prices etc. Instead, suppose Ms Bright enters a ‘receive-equity returns, pay-LIBOR’ swap on a notional principal of $Q/2=\$500$ with net cash fows paid every 3 months (the tenor in the swap). Each 3-month period, the cash fow from her portfolio of $\$0$ in FRNs plus her swap position is:  

$$
\begin{array}{c}{{\mathrm{Cash\flow\(3\months)}=Q L\ (d a y s/360)+(Q/2)\ \left[R_{S\&P}-L(d a y s/360)\right]}}\\ {{{}}}\\ {{=(Q/2)L(d a y s/360)+(Q/2)R_{S\&P}}}\end{array}
$$  

Notional principal $\mathbf{\tau}=\mathbf{\tau}$ 100,000,000   
Tenor: 3 months   
Day-count LIBOR: days/360   
Days in year: 360  

TABLE 37.1 Ex-post cash fows, receive equity return and pay LIBOR   


<html><body><table><tr><td rowspan="2">Time</td><td rowspan="2"> Days </td><td rowspan="2">LIBOR</td><td colspan="2">S&P 500</td><td rowspan="2">Pay LIBOR</td><td rowspan="2">Receive S&P 500</td><td rowspan="2">Net receipts Swap</td></tr><tr><td>Index</td><td> Return</td></tr><tr><td>10 Jan-01</td><td></td><td></td><td>1,922</td><td></td><td></td><td></td><td></td></tr><tr><td>10 April-01</td><td>91</td><td>5%</td><td>2,041</td><td>6.19%</td><td>1,263,889</td><td>6,191,467</td><td>4,927,578</td></tr><tr><td>10 July-01</td><td>91</td><td>5.35%</td><td>2,137</td><td>4.70%</td><td>1,352,361</td><td>4,703,577</td><td>3,351,216</td></tr><tr><td>10 Oct-01</td><td>92</td><td>5.50%</td><td>2,163</td><td>1.22%</td><td>1,405,556</td><td>1,216,659</td><td>-188,897</td></tr><tr><td>10 Jan-02</td><td>92</td><td>4.95%</td><td>2,268</td><td>4.85%</td><td>1,265,000</td><td>4,854,369</td><td>3,589,369</td></tr></table></body></html>  

where $R_{S\&P}$ is the actual return over 3 months on the S&P 500 index and $L(d a y s/360)$ is the LIBOR rate over the same 3-month period. (The LIBOR rate is fxed at time $t$ and the payments take place ‘days’ later.) Using the swap, Ms Bright has ‘synthetically’ changed the composition of her portfolio, which is now equivalent to holding $\$500$ in FRNs and having $\$500$ invested in the S&P 500. The equity swap will have lower transactions costs than directly buying and selling (an ETF on) the S&P 500 stock index and the FRNs – simply because the swap dealer is very e\$cient at structuring this swap – specialisation in capitalist economies tends to lower ‘costs of production’.  

Suppose the above equity swap is negotiated on 10 January-01, on a notional principal of $\$1000$ when LIBOR is $5\%$ . The frst LIBOR payment 91 days later (10 April) will be (see Table 37.1):  

$$
\mathrm{LIBORcashflow}=\S100\mathrm{m}\left(0.05\right)\left(91/360\right)=\S1.263,889.
$$  

Suppose the rise in the S&P 500 over this 90-day period is $6.19\%$ so the equity cash fow (on 10 April) is:  

$$
\mathrm{Equity}\mathrm{cash}\mathrm{flow}=\S100\mathrm{m}(0.0619)=\S6,191,467.
$$  

Hence, Ms Bright who ‘receives the S&P 500 and pays LIBOR’ would have net receipts on 10 April of $\$4,927,578$ from the equity swap. Hence the portfolio manager receives (pays out) cash when the 3-month return on the S&P 500 index is higher (lower) than (3-month) LIBOR. Note that between April and July the S&P 500 falls and the portfolio manager (Ms Bright) pays out based on the fall in the S&P 500 and also pays out on LIBOR.  

The net receipts from the equity swap clearly depend on the performance of the S&P 500 relative to LIBOR and the portfolio manager could win or lose on the swap, in terms of her net cash receipts over the life of the swap. But this is somewhat immaterial. The purpose of the equity swap is not to hedge her $\$1000$ FRN portfolio but to synthetically transform it so she replicates a $\$500$ exposure to FRNs but also has a $\$500$ exposure to risky equity returns.  

If the initial portfolio had consisted of fxed-coupon bonds then Ms Bright’s equity swap might have involved paying a fxed rate of interest and receiving the return on the S&P 500 on a $\$500$ notional principal. This is an ‘equity-for-fxed interest rate swap’.  

# 37.1.1 Double Exposure  

Consider again the US portfolio manager (Ms Bright) currently holding $Q=\$1000$ in FRNs. Suppose over the next year, Ms Bright now would like a $\$25m$ $(=Q/4)$ exposure to the S&P 500 and a $\$25m$ $(=Q/4)$ exposure to the Russell 2000 index,1 leaving a $\$50\mathbf{m}\left(=Q/2\right)$ exposure to LIBOR. To achieve this she could agree two swaps with a life of 1 year and with cash fows determined every 3 months (say):  

(a) receive the return on S&P 500 and pay LIBOR on a notional of $Q/4$ (b) receive the return on Russell 2000 and pay LIBOR on a notional of $Q/4$  

The original portfolio of FRNs plus these two swaps results in net cash fows each period of:  

$$
\begin{array}{r l}&{=Q.L(d a y s/360)+(Q/4)[(R_{S\mathscr{E}P}-L(d a y s/360)]+(Q/4)[R_{R u s s e l l}-L(d a y s/360)]}\\ &{=(Q/2)\ L(d a y s/360)+(Q/4)R_{S\mathscr{E}P}+(Q/4)R_{R u s s e l l}}\end{array}
$$  

Ms Bright has used the equity swap to synthetically change the composition of her existing portfolio, for a 1-year period. Note also that only a single OTC deal with one swap dealer would be required, since the swap dealer would ‘bundle up’ the two separate swaps. This is an example of structured fnance in the OTC market.  

# 37.2 UNHEDGED CROSS-CURRENCY EQUITY SWAP  

This type of equity swap enables a US investor (Ms Bright) to gain exposure to foreign stocks (FTSE 100), including taking on exchange rate risk if she wishes. The alternative to using the swap would be to purchase the foreign equity directly but again this could involve high transactions cost (e.g. transactions taxes and possible dividend withholding taxes, bid–ask spreads etc.). Instead, Ms Bright, who is holding $Q=\$1000$ in FRNs, could agree to receive payments based on the return on the FTSE 100 (say) and pay 3-month US-LIBOR, on a notional principal of $Q=\$1000$ . The expiry date of the swap might be in 1 year’s time, with a tenor of 3 months. After entering the swap Ms Bright efectively has $\$1000$ invested in both the FTSE 100 and the GBP-USD exchange rate, over the next year.  

Suppose the GBP-USD exchange rate is currently ${\cal E}_{0}=1.5~(\Phi/£)$ . Then $\$1000$ is equivalent to $\pm66.667\mathrm{m}$ . If $R_{F T S E}=4\%$ over the next 3 months then the sterling (GBP) investment increases to $\mathtt{f69.333m}$ but if sterling also depreciates by $2\%$ over the next 3 months (to $E_{1}=1.47\:\S/£)$ then the USD value of the UK investment is $\$101.92$ $(=\pm69.333\times1.47)$ , an increase of about $2\%$ .  

The swap is unhedged, so although the FTSE 100 increases by $4\%$ , the USD swap receipts only increase by around $2\%$ , because of the fall in sterling (GBP). Ms Bright will receive $\$1.92m$ from the swap dealer at the frst payment date (and will pay US-LIBOR). The net cash fows from the FRN plus the unhedged cross-currency swap are:  

$$
\begin{array}{r l}&{\mathsf{V e}t c a s h f l o w s\left(U S D\right)^{2}\approx\mathfrak{H}O L(d a y s/360)+\mathfrak{H}O[R_{F T S E}+R_{F X}^{\left(\mathfrak{G}/\mathfrak{c}\right)}-L(d a y s/360)]}\\ &{=\mathfrak{H}O[R_{F T S E}+R_{F X}^{\left(\mathfrak{G}/\mathfrak{c}\right)}]}\end{array}
$$  

(wnheegraet $R_{F X}^{(\S/£)}=(E_{1}/E_{0})-1$ ciisatehse(‘dretpurrenc’iaotenst)haegaUiSnsDt tShterliUnSgD.exBcrhoandglye rsapteakaindg tshpeoesiftievcet of the swap is to synthetically ‘convert’ the $\$1000$ FRN portfolio into a $\$1000$ portfolio whose return depends on both the performance of the FTSE 100 and the USD-Sterling exchange rate.3  

# 37.3 HEDGED CROSS-CURRENCY EQUITY SWAP  

This works in a similar way to the unhedged swap except that at inception of the swap a fxed exchange rate is agreed (e.g. $E_{0}=1.5$ USD/GBP) which will apply to all currency conversions at each payment date and also to the notional principal. Efectively this means that there is no FX risk. Since $E_{0}=1.5$ USD/GDP, a $\$1000$ notional principal in the swap amounts to $\pm66.667\mathrm{m}$ sterling. If $R_{F T S E}=4\%$ over the next 3 months this becomes $\pm69.333\mathrm{m}$ . But at $t=1$ this is converted at the agreed fxed exchange rate of 1.5 USD/GDP to give $\$103.99$ – a $4\%$ increase on the initial USD investment of $\$1000$ . The net cash fows from the initial holding of $\$2$ in the FRN and the equity swap are:  

Even if sterling falls to 1.47 $(\$12$ after 3 months, this does not afect the conversion from sterling to USD. The hedged cross-currency equity swap locks in the percentage return on the FTSE (in USD) regardless of what happens to the USD-GBP exchange rate.4  

# 37.3.1 Hedging by the Swap Dealer  

Although, in the above example, Ms Bright achieves her desired portfolio by using the equity swap (and hence presumably her desired risk-return trade of), the same cannot be said for the swap dealer. Clearly, in the above examples the swap dealer is exposed to risk due to US interest rates, the S&P 500, the FTSE 100 and the USD-Sterling exchange rate. These positions can be hedged using a ‘strip’ of appropriate futures contracts (i.e. a futures contract for each prospective reset date in the swap). The hedged cross-currency swap with the FTSE 100 involves both equity risk and exchange rate risk for the swap dealer, which can be hedged using stock index futures and currency futures. Of course, the swap dealer will net out all the positions in the whole of her swaps’ book before initiating the diferent hedge positions. Alternatively, the swap dealer could hedge the present value of her swap positions – again using equity, interest rate and currency futures (see below for the calculation of the PV of equity swaps).  

# 37.4 PRICING EQUITY SWAPS  

In this section we:  

• Price an equity-for-LIBOR swap and fnd the (present) value of this swap at any point during the life of the swap.   
• Price an equity-for-fxed interest rate swap and fnd the value of this swap at any point during the life of the swap.   
• Discuss the use of variable notional amounts in swap contracts.   
• Price and then value an equity-for-equity swap, where the equities are in the same currency.   
• Price and then value a cross-country, equity-for-equity swap, where the equities are in diferent countries.  

# 37.4.1 Equity-for-LIBOR Swap: Fixed Notional  

# 37.4.1.1 Pricing  

Equity swaps with a fxed notional principal can be priced using arbitrage arguments. In an equity-for-LIBOR swap:  

A fair swap rate is the exchange of the equity return for LIBOR at each payment date.  

The above conclusion should initially seem counter-intuitive because on average equity returns are higher than LIBOR, so one might think that receiving the equity return and paying LIBOR is advantageous. But arbitrage arguments rule this out. (It’s a bit like pricing stock options using arbitrage arguments, where we also fnd that the option premium does not depend on the ‘real world’ mean growth rate of the stock price.) In pricing this swap we assume any dividends on the stock or stock index are paid only at (the swap) payment dates or alternatively we assume the ‘equity’ is a (traded) ‘total return’ equity index.5  

Essentially, the arbitrage argument replicates the cash fows in this swap by borrowing $\$1$ at LIBOR and investing this $\$1$ in equity at $t_{0}=0$ and at each future reset date. The present value of all of these $\$1$ investments in equity can be shown to equal the present value of $\$1$ invested at LIBOR. Hence a swap of the equity return for LIBOR is a ‘fair deal’ as both sides of the swap have the same present value. We now examine this argument in more detail.  

Consider an investor who receives at time $t_{i}$ the per period equity return ${z_{i}}^{6}$ between $t_{i-1}$ and $t_{i}$ and pays $L I B O R_{i}$ $(=r_{i})$ plus a fxed spread s. The tenor for the LIBOR payments is $m_{i}=$ $d a y s_{i}/360$ and the LIBOR rate $r_{i}$ is fxed at $t_{i-1}$ with payment at $t_{i}$ . Hence net receipts in the swap (on a notional principal of $\$1$ ) on any future payment dates $t_{i}=1,2,\ldots n$ are:  

To price this swap we need to fnd the value of $s$ for which the present value of the net receipts is zero. Consider investing $\$1$ in equities or $\$1$ at LIBOR at each of the times $t_{0},t_{1}$ . . . and $t_{n-1}$ . This results in replicating the cash fows on the equity side and the LIBOR sides of the swap and we show that the PV (at $t=0$ ) for these equity and LIBOR investments are equal when $s=0$ . So an exchange of equity returns for LIBOR (fat) is a ‘fair swap’ that both parties are willing to enter.  

The economic intuition is as follows. Investors must be indiferent between the returns on two diferent investments in risk-adjusted terms otherwise they would buy one asset and sell the other, until the returns are equalised. So in risk-adjusted terms an investment in LIBOR or in individual equities or an equity index must be equivalent. Hence a swap of LIBOR (fat) for equity returns, or returns on one equity-A for returns on equity-B or returns on equity-A for returns on an equity index are all ‘fair swaps’. Let’s consider this for a swap to receive equity returns and pay LIBOR (fat).  

Consider investing $\$1$ at $t=0$ in an equity portfolio. This will be worth $\$1[1+z_{1}]$ at $t=1$ , with $P V=\$1$ at $t=0$ (discounting using the equity return). Similarly $\$1$ invested at LIBOR at $t=0$ is worth $\$1[1+r_{1}m_{1}]$ at $t=1$ , with present value at $t=0$ of $\$1$ (discounting at LIBOR).  

Now move to $t=1$ and invest $\$1$ in equity which will be worth $\$1[1+z_{2}]$ at $t=2$ , which has a PV at $t=1$ of $\$1$ and a PV at $t=0$ of $(\$1d_{1})$ , where $d_{1}=$ discount factor that applies between $t_{0}$ and $t_{1}$ . Similarly, the cash fow from a $\$1$ investment at $t=1$ at LIBOR gives $\$1$ $[1+r_{2}m_{2}]$ at $t=2$ , with PV at $t=1$ of $\$1$ and PV at $t=0$ of $(\$1d_{1})$ – the same PV as for the equity investment. We can repeat this argument for all the other time periods to $t_{n-1}$ . From Table 37.2 we see:  

TABLE 37.2 Equity for LIBOR, cash fows and PV   


<html><body><table><tr><td>Time</td><td>Equity return</td><td>PV (equity return) at t = 0</td><td>LIBOR payments</td><td>PV (LIBOR payments) at t = 0</td></tr><tr><td>t=0</td><td></td><td></td><td></td><td></td></tr><tr><td>t=1</td><td>1+Z1</td><td>1</td><td>1+rm1</td><td>1</td></tr><tr><td>t=2</td><td>1+Z</td><td>d1</td><td>1+rm2</td><td>d1</td></tr><tr><td>t=3</td><td>1+Z</td><td>d2</td><td>1+rm3</td><td>d2</td></tr><tr><td>…</td><td></td><td>…</td><td>…</td><td>…</td></tr><tr><td>t=n</td><td>1+Zn</td><td>dn-1</td><td>1+rnmn</td><td>dn-1</td></tr></table></body></html>  

$$
\begin{array}{c c c}{P V(t=0,e q u i t y)=1+d_{1}+d_{2}+\ldots}&{\ldots+d_{n-1}}\\ {\null}&{\null}&{\null}\\ {P V(t=0,L I B O R)=1+d_{1}+d_{2}+\ldots}&{\ldots+d_{n-1}}\end{array}
$$  

We have replicated the payofs in the swap by borrowing at LIBOR and using the proceeds to invest in equity and shown that a swap involving the equity return for LIBOR is ‘fair’, because they have the same present value.  

# 37.4.1.2 Valuation  

Although the equity-for-LIBOR swap has zero value at inception, its value can change over time as equity prices and interest rates change. We can easily value the equity swap at any date $t$ , which lies between any two payment dates. For example, if $t_{0}<t<t_{1}$ we show in Appendix 37 that the value of the ‘receive-equity returns, pay-LIBOR’ is (Figure 37.1):  

$$
V_{t}=(S_{t}/S_{0})-d(t,t_{1})(1+r_{1}m_{1})
$$  

![](171c3814ec95806f873a719031c1d0b0ac6c556bf03b48efa6852cdd20c1e861.jpg)  
FIGURE 37.1 Value of equity swap at t  

TABLE 37.3 Equity-for-fxed-interest, cash fows and PV   


<html><body><table><tr><td>Time</td><td>Equity return</td><td>PV (equity return) at t = 0</td><td>Fixed interest</td><td>PV (fixed interest) at t = 0</td></tr><tr><td>t=0</td><td></td><td></td><td></td><td></td></tr><tr><td>t=1</td><td>1+Z1</td><td>1</td><td>1 + sp m1</td><td>d(1 +spm)</td></tr><tr><td>t=2</td><td>1+Z</td><td>d1</td><td>1+sp m2</td><td>d(1 +sp m)</td></tr><tr><td>t=3</td><td>1+Z3</td><td>d2 </td><td>1+sp m3</td><td>d(1 +sp m3)</td></tr><tr><td></td><td>…</td><td></td><td></td><td></td></tr><tr><td>t=n</td><td>1+Zn</td><td>dn-1</td><td>1+ sp mn</td><td>d,(1 +sp mn)</td></tr></table></body></html>  

Hence the value of an equity-for-LIBOR swap (at $t>0$ ) depends on the return on the stock since inception, as well as the (present value at $t^{\cdot}$ ) of the next LIBOR payment (which is determined by $r_{1}$ (the LIBOR rate set at $t_{0}$ and payable at $t_{1}$ ).  

37.4.2 Equity-for-Fixed-Interest Swap: Fixed Notional  

# 37.4.2.1 Pricing  

Consider receiving the equity return and paying a fxed interest rate $\mathbf{\epsilon}^{\bullet}s p^{\prime}$ in the swap. We show that the fxed rate in this equity swap is the same as for a plain vanilla fxed-for-foating interest rate swap.  

The swap rate for ‘equity-for fxed interest rate’ is the same as the ‘swap rate’ for $a$ fxed-for-foating interest rate swap.  

In the swap the cash fows to equity are the same as above, repeated in columns 2 and 3 in Table 37.3.  

The fxed-interest cash fows from $\$1$ invested at any time $t-1$ are $(1+s p.m_{t})$ , payable at $t$ with present value at $t_{0}$ of $d_{t}(1+s p.m_{t})$ , for $t=1,2,3,\ldots,n$ , where $d_{t}\equiv d(0,t)$ the discount factor that applies between $t=0$ and $t$ . The PV of the net cash fows in the swap are:  

$$
\begin{array}{r l}&{\quad P V(t=0,e q u i t y)=1+d_{1}+d_{2}+\dotsc+d_{n-1}}\\ &{^p V(t=0,f i x e d s p)=d_{1}(1+s p.m_{1})+d_{2}(1+s p.m_{2})+\dotsc+d_{n}(1+s p.m_{n})}\end{array}
$$  

Equating these two present values and solving for $s p$ (at $t=0$ ):  

$$
s p={\frac{1-d_{n}}{\displaystyle\sum_{i=1}^{n}d_{i}m_{i}}}
$$  

Surprisingly, the equity swap rate in (37.7) is independent of the expected equity return (and the volatility of equity returns) and depends only on the term structure of interest rates. This is counterintuitive but we know it is correct because of the above arbitrage/replication argument.  

Hence the swap rate for ‘equity-for-fxed-interest rate’ is the same as the ‘swap rate’ quoted on a fxed for foating interest rate swap. This should not be too much of a surprise as we have seen that ‘equity-for-LIBOR’ is a fair swap and we know that a ‘fxed-for-foating (LIBOR)’ interest rate swap, is also a fair swap. But a ‘receive-equity, pay-LIBOR’ swap plus a ‘receive-LIBOR, pay-fxed interest rate’ swap, is equivalent to ‘a receive-equity, pay-fxed interest’ swap, which must therefore also be a fair swap. The quoted swap rates for a vanilla interest rate swap and the equity-for-fxed interest swap must be equal, otherwise riskless arbitrage opportunities are possible.  

# 37.4.2.2 Valuation  

Consider the value of the equity-for-fxed-interest swap at $t$ between any two payment dates (e.g. $t_{0}<t<t_{1})$ . The present value of the fxed cash fows at $t$ is the same as above but all discount rates and day-count conventions now start from $t$ (rather than $t_{0}=0\mathrm{\AA}$ ), hence, the fxed leg has:  

$$
\mathbf{\Phi}_{t}^{r}(f i x e d,s p_{o})=d_{t,1}(1+s p_{0}.m_{t,1})+d_{t,2}(1+s p_{0}.m_{t,2})+\ldots+d_{t,n}(1+s p_{0}.m_{t,n}),
$$  

Now consider the equity cash fows. For the equity stream at say $t_{2}$ , this can be replicated by a $\$1$ investment at $t_{1}$ which gives a payout at $t_{2}$ of $(1+z_{2})$ . At time $t$ , this $\$1$ investment at $t_{1}$ is worth $d_{t,1}$ . This argument applies to any payout after $t_{2}$ , so the PV of all these $\$1$ equity investments is:  

$$
P V_{t}(e q u i t y c a s h f l o w s f o r t\ t\ge2)=d_{t,1}+d_{t,2}+\ldots+d_{t,n-1}.
$$  

Note that the last term is $d_{t,n-1}$ since the last $\$1$ investment to replicate the fnal payout at $t_{n}$ takes place at $t_{n-1}$ . Finally we have to deal with the time- $t$ present value of the equity cash fow at $t_{1}$ , which we have already found to be $S_{t}/S_{0}$ . Hence the present value of all the equity cash fows in the swap, at $t$ is:  

$$
P V_{t}(e q u i t y c a s h f l o w s~t_{1}~t o~t_{n})=(S_{t}/S_{0})+d_{t,1}+d_{t,2}+\ldots+d_{t,n-1}
$$  

The value at $t$ of the ‘receive-equity, pay-fxed interest’ is the diference between Equation (37.10) and Equation (37.8), which (after some simplifcation) is:  

$$
V_{t}(e q u i t y-f i x e d)=(S_{t}/S_{0})-d_{t,n}-s p_{0}[d_{t,1}.m_{t,1}+d_{t,2}.m_{t,2}+\ldots+d_{t,n}.m_{t,n}]
$$  

Also, the above valuation formula is consistent with the determination of the swap rate $s p_{0}$ (Equation 37.7). This can be seen by setting $V_{t}(e q u i t y-f i x e d)=0$ , replacing all the $d_{t,i}$ by $d_{o,i}$ , replacing $S_{t}$ by $S_{0}$ and solving for $s p_{0}$ .  

# 37.4.3 Equity Swaps with Variable Notional Principals  

This type of swap is structured so that the notional principal amount at say $t_{4}$ depends on the equity returns realised up to $t_{3}$ . So the principal amount $P A_{3}$ applicable at $t_{3}$ is:  

$$
P A_{3}=(1+z_{1})(1+z_{2})(1+z_{3})
$$  

Hence the net cash fow received at $t_{4}$ for an equity-for-LIBOR or equity-for-fxed interest swap are:  

It turns out that the frst of the above cash fows can be replicated and it is found that a swap of ‘equity-for-LIBOR’ with a variable notional principal, is a fair one. But the second cash fow cannot be replicated and to value an ‘equity-for-fxed interest’ swap with a variable notional principal, we have to make assumptions about the path of equity prices (e.g. they follow a binomial path).7  

# 37.4.4 Equity-for-Equity Swap (Same Currency): Fixed Notional  

Consider a swap where one party receives the return on the S&P 500 and pays the return on the Russell 3000 index or, alternatively, a swap for the return on Microsoft in exchange for the return on Walmart. This type of swap applies to equity returns in the same currency.  

# 37.4.4.1 Pricing  

Using (slight modifcations) of the above arguments for ‘equity-for-fxed’ or ‘equity-for-foating interest rates, it can be shown that equity-for-equity swaps are fair swaps (and hence require no up-front payment at inception).  

A swap of equity returns-A for equity returns-B (in the same currency) is a fair swap.  

# 37.4.4.2 Valuation  

Valuation of equity-equity swaps at time $t$ (i.e. between payment dates) also follows similar arbitrage arguments described above. Suppose $t$ lies between $t_{0}$ and $t_{1}$ then the value of the swap to receive the return on equity-A and pay the return on equity-B is:  

$$
V_{t}(e q u i t y–f o r–e q u i t y)=(S_{t}^{A}/S_{0}^{A})-(S_{t}^{B}/S_{0}^{B})
$$  

where $S_{t}=$ value of the respective portfolios/stocks at time $t\left(t_{0}<t<t_{1}\right)$ .  

37.4.5 Cross-country Equity-for-Equity Swap: Fixed Notional  

# 37.4.5.1 Pricing  

Suppose the swap involves receiving the return on the FTSE 100 (the foreign asset, $S^{f}$ ) and paying the return on the S&P 500 (domestic asset, $S^{d}$ ). The return to investing $\$1$ in the S&P 500, the domestic asset is:  

$$
1+R_{d}\equiv S_{1}^{\mathrm{d}}/S_{0}^{\mathrm{d}}
$$  

The return in USDs, to investing $\$1$ at $t=0$ in the FTSE 100 (the foreign asset, with price $\boldsymbol{S^{f}})$ is:  

$$
\mathrm{\starReturn~USD},\mathrm{foreign~investment}=(1+R_{f})(1+R_{F X}^{{\S}/{\varepsilon}})=(S_{1}^{f}E_{1}^{{\S}/{\varepsilon}})/(S_{0}^{f}E_{0}^{{\S}/{\varepsilon}})
$$  

where $E^{\Phi/£}$ is the USD-GBP spot FX-rate. To replicate the cash fows in both (37.14) and (37.15) requires $\$1$ at $t_{0}$ . Hence the net payof at $t_{1}$ to a cross-currency equity swap is:  

$$
\begin{array}{r}{N e t\ c a s h\ f l o w\ (\mathrm{at}\ t_{1})=(1+R_{f})(1+R_{F X}^{\mathfrak{H}/\mathfrak{L}})-(1+R_{d})}\\ {=(S_{1}^{f}E_{1}^{\mathfrak{H}/\mathfrak{L}})/(S_{0}^{f}E_{0}^{\mathfrak{H}/\mathfrak{L}})-(S_{1}^{d}/S_{0}^{d})}\end{array}
$$  

The payments at all future dates $t_{k}$ takes the same form as above (with $t_{k-1}$ , $t_{k}$ replacing $t_{0}$ , $t_{1}$ , respectively). But as each of these cash fows can be replicated by a $\$1$ investment then:  

A swap of the return on the FTSE for the return on the S&P 500 is $a$ fair exchange.  

# 37.4.5.2 Valuation  

Between any two payment dates, say $t_{0}<t<t_{1}$ , the value of the swap is:  

Value of cross-currency swap at t:  

# 37.5 SUMMARY  

• An equity swap is an exchange of cash fows in the future, where for one leg of the swap the cash fows are determined by the return on a stock or the return on a stock index. The other leg of the swap may involve foating or fxed interest payments or payments based on a domestic or foreign equity (index).   
• The notional principal in an equity swap may be fxed or variable.   
• If a swap involves foreign equities, the ‘return’ in the swap can either be hedged or unhedged, against changes in the spot FX-rate.   
• Equity swaps are used by investment managers to alter the asset composition of their portfolio at low cost, since the desired exposure is obtained without actually buying or selling the assets in the existing portfolio.   
• Equity swaps (with a fxed notional principal) can be priced using arbitrage arguments.   
• A ‘vanilla equity swap’ is usually an exchange of ‘equity returns for fxed interest’ or ‘equity returns for foating (LIBOR) interest’. Somewhat counter-intuitively, a fair exchange is the ‘equity return for the fxed-interest swap rate’ and ‘equity returns for LIBOR’, respectively.   
• After inception, the value of a plain vanilla receive-equity, pay-LIBOR swap, can be either positive or negative (to one of the parties). Its value at $t$ between any two payment dates (e.g. $t_{0}<t<t_{1},$ depends on the equity price rise from the last reset date $(S_{t}/S_{0})$ and the present value of the next (known) LIBOR cash payment $d(t,t_{1})(1+r_{1}m_{1})$ . The value of the swap is $V_{t}=(S_{t}/S_{0})-d(t,t_{1})(1+r_{1}m_{1})$ .   
• Equity-for-equity swaps are fair swaps, if the equity returns are in the same currency (e.g. equity return on Microsoft swapped for the equity return on AT&T). Between any two payment dates (e.g. $t_{0}<t<t_{1},$ , the market value of a ‘domestic equity for domestic equity’ swap, depends on the diference in the return on the two equities (since the last reset date, $t_{0.}^{\cdot\cdot}$ ).   
• A cross-currency equity swap might involve receiving the return on the S&P 500 and paying the return on the FTSE 100. This is a fair swap. The value of a cross-currency equity swap to a US resident (say) depends on the return on the foreign equity (in USD) and the return on the domestic equity (in USD) – the former depends on the change in the exchange rate – so there is FX risk in the swap.  

# APPENDIX 37: VALUATION OF EQUITY-FOR-LIBOR SWAP  

Using replication and arbitrage arguments we show that the value of the ‘receive-equity returns, pay-LIBOR’ swap at any time $t$ when the remaining payment dates are at $t_{1},t_{2},\ldots,t_{n}$ is given by (see Figure 37.A.1):  

$$
V_{t}=(S_{t}/S_{0})-d(t,t_{1})(1+r_{1}m_{1})
$$  

First, we consider cash fows at $t_{2}$ and afterwards. Then we examine cash fows at the next payment date $t_{1}$ and fnd that it is only these cash fows that infuence the value of the swap, at time $t$ $(<t_{1})$ – consistent with Equation (37.A.1).  

As before, equity returns at $t_{2}$ may be replicated by a $\$1$ investment in equity at $t_{1}$ , with PV at time $t$ of $P V(t)=\S1.d(t,t_{1})$ . Similarly a $\$1$ investment in a LIBOR deposit at $t_{1}$ gives $\S1(1+r_{2}m_{2})$ at $t_{2}$ with present value $P V(t)=d(t,t_{1})$ . Hence, the diference in the PVs at $t$ of these two cash fows is zero. This is true for all cash fows at $t\geq2$ .  

Hence it is only the PV of the cash fows at $t_{1}$ that determine the value of the swap at $t$ . Between $t_{0}$ and $t_{1}$ the return on equity is $(1+z_{1})$ and the LIBOR payof is $(1+r_{1}m_{1})$ . Hence at $t$ , the present value of the long-short position is:  

$$
V_{t}(E q u i t y-L I B O R)=P V_{t}(1+z_{1})-P V_{t}(1+r_{1}m_{1})=P V_{t}(1+z_{1})-d(t,t_{1})(1+z_{1})
$$  

where $P V_{t}(1+z_{1})$ is the present value at time $t$ , of the cash fow $(1+z_{1})$ payable at the next reset date $t_{1}$ .  

Realised returns on equity will not be known until time $t_{1}$ . But $\$1$ invested in equity at $t_{0}$ , accrues to $\mathfrak{H}\ (1+z_{1})\equiv S_{1}/S_{0}$ at $t_{1}$ . We can replicate this cash fow by purchasing $N_{0}=1/S_{0}$ units of stock at $t_{0}$ , since this will be worth $N_{0}S_{1}=S_{1}/S_{0}$ at $t_{1}$ . Hence the time- $t$ present value of $(1+z_{1})$ payable at $t_{1}$ is $S_{t}/S_{0}$ :  

$$
V_{t}(E q u i t y-L I B O R)=(S_{t}/S_{0})-d(t,t_{1})(1+r_{1}m_{1})
$$  

Note that this formula is consistent with the swap having zero value at inception – since at $t=0$ , $d(0,t_{1})=1/(1+r_{1}m_{1})$ and $S_{t}=S_{0}$ , so from Equation (37.A.3), $V_{t}=0$ .  

# EXERCISES  

# Question 1  

What are the key features of a plain vanilla equity swap?  

# Question 2  

You are a US investor holding $\$1000$ in stocks which mimic movements in the S&P 500 index. You predict that the UK equity market will increase faster than the US equity market over the next 2 years and that sterling (GBP) will appreciate. To take advantage of your forecasts, what kind of swap might you initiate?  

# Question 3  

A ‘market timer’ switches between equities and cash (which earns interest given by the London Interbank Bid Rate, LIBID), depending on her forecast of whether the stock market will rise above the LIBOR rate.  

How might she use equity swaps to time the market, if she thinks the rise in the stock market will exceed LIBID in each of the next 3 months?  

# Question 4  

Why might a US investor holding $\mathrm{US}\$100m$ in a deposit at LIBOR, with resets every 3 months, fnd an equity swap (on the S&P 500) useful over the next year? Explain why the investor might choose an equity swap with a principal of $\mathrm{US}\$500$ .  

# Question 5  

How can a US investor holding $\$1000$ in a diversifed portfolio of US stocks use an equity swap to facilitate a $25\%$ exposure to the UK stock market, every 3 months for 1 year, without incurring exchange rate risk?  

# Question 6  

Ms Gaga holds $\$100,000$ in an equity swap, with a 6-month tenor, to receive the equity return and pay USD-LIBOR. The 6-month LIBOR rate 181 days ago was $4\%$ p.a. and over the last 181 days the equity return was minus $1\%$ . The day-count convention for LIBOR payments is actual/360. Today, what is the net payment in the swap?  