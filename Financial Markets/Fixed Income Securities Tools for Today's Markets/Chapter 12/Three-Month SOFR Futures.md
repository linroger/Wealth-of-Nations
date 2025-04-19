---
tags:
  - daily_compounded_sofr
  - futures_contracts
  - hedging
  - interest_rate_risk
  - sofr_futures
aliases:
  - 3-month SOFR futures
  - SOFR futures contracts
key_concepts:
  - contract settlement
  - daily compounded SOFR
  - hedging exposure to SOFR
  - settlement rate
  - three-month contracts
---

# 12.4 THREE-MONTH SOFR FUTURES  

Like one-month SOFR futures, three-month contracts are designed to hedge exposure to SOFR and are subject to daily settlement. There are three differences, however. First, and most obviously, three-month contracts hedge exposure over three months, with the exact determination of dates described presently. Second, the settlement rate of the three-month contract is based not on average SOFR over the reference period, but rather on daily compounded SOFR. Third, the three-month contract is scaled to hedge a $\$1$ million 90-day investment, which means that the $\mathrm{P}\&\mathrm{L}$ on one contract from a one-basis-point decrease in the final settlement rate is set equal to,  

$$
\$1,000,0000\times0.01\%\times{\frac{90}{360}}=\S25
$$  

Table 12.7 lists the first four three-month contracts, along with their prices and rates, as of January 14, 2022. The first three letters of the ticker, "SFR," denote the three-month SOFR contract, while the following letter and digit, as for other futures contracts, denote the delivery month and last digit of the year. The "Start Date" of the reference period is the IMM (International Monetary Market) date corresponding to the contract month, where IMM dates are defined as the third Wednesday of March, June, September, and December. The "Last Trade Date' of a contract,. which is also the last day of the reference period, is the business day before the next IMM date. And the "Valuation Date," which is the day of the last daily settlement payment, is the business day after the last trade date. For. the June three-month SOFR contract, for example, the reference period for the calculation of the final settlement rate is from the June IMM date, or June 15, 2022, inclusive, to the September IMM date, or September 20, 2022, inclusive. The contract stops trading on September 20, 2022, and the. last daily settlement payment is on September 21, 2022, which is the date that SOFR for September 20, 2022, is published..  

TABLE 12.7  Selected Three-Month SOFR Futures Contracts, as of January 14, 2022. Rates Are in Percent.   


<html><body><table><tr><td>Ticker</td><td>Delivery Month</td><td>StartDate (inclusive)</td><td>Last Trade Date</td><td>Valuation Date</td><td>Price</td><td>Rate</td></tr><tr><td>SFRZ1</td><td>Dec</td><td>12/15/2021</td><td>03/15/2022</td><td>03/16/2022</td><td>99.940</td><td>0.060</td></tr><tr><td>SFRH2</td><td>Mar</td><td>03/16/2022</td><td>06/14/2022</td><td>06/15/2022</td><td>99.640</td><td>0.360</td></tr><tr><td>SFRM2</td><td>Jun</td><td>06/15/2022</td><td>09/20/2022</td><td>09/21/2022</td><td>99.350</td><td>0.650</td></tr><tr><td>SFRU2</td><td>Sep</td><td>09/21/2022</td><td>12/20/2022</td><td>12/21/2022</td><td>99.125</td><td>0.875</td></tr></table></body></html>  

Let $r_{i}$ denote SOFR for date $i.$ , and let $D$ denote the total number of days in the reference period. As in the cases of one-month SOFR futures and fed fund futures, SOFR for any non-business day is taken as the value of SOFR on the previous business day. The final settlement rate of a three-month SOFR futures contract, $R$ , is then defined such that,.  

$$
\begin{array}{l}{{\displaystyle1+\frac{R D}{360}=\left(1+\frac{r_{1}}{360}\right)\left(1+\frac{r_{2}}{360}\right)\cdot\cdot\cdot\left(1+\frac{r_{D}}{360}\right)}}\ {{\displaystyle R=\left[\left(1+\frac{r_{1}}{360}\right)\left(1+\frac{r_{2}}{360}\right)\cdot\cdot\cdot\left(1+\frac{r_{D}}{360}\right)-1\right]\frac{360}{D}}}\end{array}
$$  

The right-hand side of Equation (12.9) gives the value of an investment of one unit of currency, compounded daily at realized SOFR rates, from days one to $D$ . The left-hand side is the value of an investment of one unit of currency at the term rate $R$ for $D$ days. Equating the two sides of this equation, therefore, means that $R$ is the realized term rate that summarizes daily compounded SOFR over the reference period. Solving for $R$ gives Equation (12.10). To illustrate with an extremely simple example, note that there are 98 days in the reference period of the June three-month SOFR contract. Assume that SOFR over the 42 days from June 15 to July 26, inclusive of both, is $0.51\%$ , while SOFR over the 56 days from July 27 to September 20, inclusive of both, is $0.76\%$ . (Note that these two periods correspond to periods between FOMC meetings listed in Table 12.6.) Then, using Equation (12.10),  

$$
\begin{array}{l}{{R=\left[\left(1+{\displaystyle{\frac{0.51\%}{360}}}\right)^{42}\left(1+{\displaystyle{\frac{0.76\%}{360}}}\right)^{56}-1\right]{\displaystyle{\frac{360}{98}}}}}\ {{R=0.653\%}}\end{array}
$$  

The final settlement price would be 100 minus the percentage rate, or. $100-0.653=99.347$ . This price and the rate in Equation (12.11) are, as. it turns out, nearly equal to the price and rate of the June contract given in Table 12.7.  

To illustrate hedging with three-month SOFR futures, consider the following simple example. As of January 14, 2022, a company plans to borrow $\$10$ million from its bank for the 98 days between June 15, 2022, to September 21, 2022, at daily compounded SOFR plus a spread. To hedge the risk that SOFR is higher over that time period, the company can sell June contracts. Because the loan is for $\$10$ million over 98 days, while each. contract is scaled to a $\$1$ million 90-day loan, the number of contracts to be sold is,  

$$
\frac{\$10,000,0000\times98}{\$1,000,000\times90}=10.89
$$  

The top panel of Table 12.8 describes the performance of the hedge in three interest rate scenarios. Consider the scenario in which the realized contract rate turns out to be $0.35\%$ . By the definition of that rate in Equations (12.9) and (12.10), the interest in this scenario on the SOFR component of the bank loan (i.e., ignoring the spread) over the 98-period. ending September 21, is $-\S10,000,000\times0.35\%\times98/360=-\S9,\$ 527.78. The P&L from the hedge, that is, from selling 10.89 contracts at $0.65\%$ that expire at $0.35\%$ , for a loss of 30 basis points per contract, is $-30\times$ $\$25\times10.89=-98,167.50$ . Ignoring daily settlement payments, this panel assumes that this futures $\mathrm{P}\&\mathrm{L}$ is realized on the June contract's valuation date, which is also September 21. Summarizing this scenario, then, the com-. pany's relatively low interest cost and its loss on its futures hedge gives a total. obligation of about $\$17,695$ . In the scenario in which the final settlement rate is $0.65\%$ , the interest cost is about $\$17,694$ , and the futures $\mathrm{P}\&\mathrm{L}$ is zero. And if the final settlement rate is. $0.95\%$ , then the realized interest cost is. relatively high, but, offset by futures gains, again giving a net cost of about. $-\$17,694$ . Hence, with the three-month SOFR futures hedge, the interest cost is successfully locked in at $0.65\%$ , that is, the rate at which the futures contracts are initially sold. (The net amount would be exactly. $\$17,694.44$ in every scenario, by the way, if the number of contracts in Equation (12.12) were taken to more decimal places.)  

TABLE 12.8Hedging the Interest Cost of Borrowing $\$10$ Million from June 15, 2022, to September 21, 2002, as of January 14, 2022, with June Three-Month SOFR Contracts, Priced Initially at $0.650\%$ . The Hedge, Not Tailed, Sells 10.89 Contracts. The Tailed Hedge Sells 10.84 Contracts. Rates Are in Percent. Other Entries in Dollars.   


<html><body><table><tr><td>Final Settle- ment Rate</td><td>Loan Interest</td><td>Futures P&L</td><td>Net</td></tr><tr><td colspan="4">Futures P&L Realized at End - Hedge Not Tailed</td></tr><tr><td>0.35</td><td>-9,527.78</td><td>-8,167.50</td><td>-17,695.28</td></tr><tr><td>0.65</td><td>-17,694.44</td><td>0.00</td><td>-17,694.44</td></tr><tr><td>0.95</td><td>-25,861.11</td><td>8,167.50</td><td>-17,693.61</td></tr><tr><td colspan="4">Futures P&L Realized at Start - Hedge Not Tailed</td></tr><tr><td>0.35</td><td>-9,527.78</td><td>-8,187.35</td><td>-17,715.13</td></tr><tr><td>0.65</td><td>-17,694.44</td><td>0.00</td><td>-17,694.44</td></tr><tr><td>0.95</td><td>-25,861.11</td><td>8,221.38</td><td>-17,639.73</td></tr><tr><td colspan="4">Futures P&L Realized at Start - Hedge Tailed</td></tr><tr><td>0.35</td><td>-9,527.78</td><td>-8,149.76</td><td>-17,677.54</td></tr><tr><td>0.65</td><td>-17,694.44</td><td>0.00</td><td>-17,694.44</td></tr><tr><td>0.95</td><td>-25,861.11</td><td>8,183.64</td><td>-17,677.48</td></tr></table></body></html>  

The second and third panels of the table return to the discussion earlier. in the chapter on the impact of daily settlement payments. The second panel illustrates the issue with the extreme assumption that, immediately after the June contracts are sold on June 14 at a rate of. $0.65\%$ , the futures rate jumps to its final settlement value and remains at that level until the end of the loan period on September 21. In the $0.35\%$ scenario, the P&L of. $-\$8,167.50$ is fully realized with the daily settlement payment at the close of business on. June 14 and has to be financed over the 250 days to September 21 at. $0.35\%$ This brings the total futures loss to. $-\$8,167.50(1+0.35\%\times250/360)=$ $-\$8,187.35$ . In the $0.65\%$ scenario, there is no futures. $\mathrm{P}\&\mathrm{L}$ , so nothing changes from the first panel. And in the. $0.95\%$ scenario, the futures gain. of $\$8,167.50$ is fully realized on June 14 and can be reinvested at $0.95\%$ to September 21, bringing the total gain to. $\$8,221.38$ . The sums of each. of these accumulated $\mathrm{P}\&\mathrm{L}$ numbers and the respective loan interest num-. bers in the second panel of the table give three net quantities that are no longer virtually the same. The cost of financing the daily settlement loss in the first scenario and the interest on the daily settlement gain in the third sce-. nario result in net positions that are not so well hedged as in the first panel.  

The differences are not particularly large, because rates are low. But the text continues by describing how to adjust the hedge: interest rates may eventually return to higher levels..  

The second panel of Table 12.8 reveals that, incorporating daily settlement payments, selling 10.89 contracts is too many. When rates. fall and futures P&L is negative, financing costs drive overall losses too. high. And when rates rise and futures. $\mathrm{P}\&\mathrm{L}$ is positive, interest earned. drives overall gains too high. Roughly speaking then, the daily settlement. feature grows any P&L from a futures contract today into that. $\mathrm{P}\&\mathrm{L}\times(1+$ $R_{0}D/360)$ as of the expiration date, where $R_{0}$ is the futures rate today. To. offset this growth, a correction used in practice, called tailing the hedge, is simply to divide the number of contracts by. $(1+R_{0}D/360)$ . In the present example, tail the hedge by reducing the number of contracts from 10.89 to $10.89/(1+0.65\%\times250/360)=10.84$ .The third panel shows. the P&L of this tailed hedge. In the. $0.95\%$ scenario, for example, the. futures P&L of $30\times\mathbb{5}25\times10.84=\mathbb{5}8,130.00$ , which is assumed to be. realized immediately, is invested at a rate of. $0.95\%$ to grow to a total gain of $\$130.00(1+0.95\%\times250/360)=\$183.64$ . All in all, comparing the net quantities in the second and third panels of the table, the tail does reduce the variance of the outcome. The correction is not perfect, of course,. because the tail reduces the number of contracts by today's futures rate,. whereas daily settlement grows by the rate in the relevant horizon. Note also that the tail needs to be adjusted over time, as the prevailing futures rate changes and as the number of days to contract expiration falls..  

The hedging example of this section is very simple in that the company's borrowing dates coincided exactly with the reference period of the June futures contract. If, instead, the company were borrowing for the same number of days, but over a different calendar period, say from April 15 to July 22, the futures hedge still calls for about 11 contracts, but split between March and June. With no view on the relative amount of interest rate risk over the 61 days covered by the March contract (April 15 to June 14, inclusive of both) and the 37 days covered by the June contract (June 15, inclusive, to July 22, not inclusive), the most straightforward split is 11 times 61/98, or about seven in March, and 11 times 37/98, or about four in June.  
