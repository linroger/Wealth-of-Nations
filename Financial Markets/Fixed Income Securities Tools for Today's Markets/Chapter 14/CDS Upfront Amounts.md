---
tags:
  - cds_spread
  - cds_upfront_amounts
  - financial_crisis
  - market_conventions
  - maturity_dates
aliases:
  - CDS Upfront
  - Upfront Amounts
key_concepts:
  - Annual coupon contracts
  - CDS trading like swaps
  - Market conventions simplify CDS
  - Standardized maturity dates
  - Upfront amount compensation
---

# 14.6 CDS UPFRONT AMOUNTS  

Before the financial crisis of 2007-2009, CDS traded like interest rate swaps; that is, the coupon changed every moment with market conditions, and standard maturities were fixed terms from the settlement date. For example, buying $\$1$ million notional of five-year CDS on Genworth at a spread of 558.92 basis points on August 16, 2006, was a commitment to pay $\$55,892$ annually in exchange for compensation in the event of a Genworth default through August 16, 2011. Consequently, as is still true for interest rate swaps today (see Chapter 13), unwinding CDS trades was relatively difficult. For example, to unwind the CDS just described after one month, a trader would most like to sell protection at a fee of 558.92 basis points through August 16, 2011. But at the time of the unwind, on September 16, 2006, the most liquid or on-the-run five-year CDS would mature on September 16, 2011, and might carry a spread of 490 basis points. The trader, therefore, would have to incur relatively high transaction costs to unwind the existing CDS, or. would have to sell protection through the on-the-run CDS and manage the maturity and spread mismatch between the original and the hedging CDS.  

Since the financial crisis, as part of a broader push by regulators to improve operations in this market, CDS have become more standardized. First, maturity dates are limited to pseudo-IMM (international money mar-. ket) dates, that is, the 20th days of March, June, September, or December.. Thus, for example, all five-year contracts traded between June 21, 2021, and September 20, 2021, mature on September 20, 2021; all five-year contracts traded between September 21, 2021, and December 20, 2021, mature on December 20, 2021; etc. Second, all contracts have annual coupons of. either 100 or 500 basis points, with a market determined upfront amount. to compensate for the difference between the market CDS spread and the. standardized coupon. Upfront amounts are described in greater detail later, but, for the present, note how these two changes in market conventions simplify the unwind of CDS. Buying a $\$1$ million five-year CDS on Genworth on August 16, 2021, at a spread of 558.92 actually requires making annual payments of 500 basis points or $\$50,000$ , and - as shown next - an upfront payment of $\$23,190$ . Furthermore, the contract matures on September 20,. 2021. Therefore, to unwind this contract after one month, the trader can. sell a still on-the-run CDS, that is, a CDS with a coupon of 500 basis points. that matures on September 20, 2021, which exactly offsets the future cash. flows of the original CDs.14 If the market upfront payment fell over the. month to. $\$13,000$ , then the trader suffers a loss of. $\$10,190$ relative to the. original purchase price. Unwinding the contract after more time has passed can be more difficult, because the on-the-run contract may have changed, but. some liquidity is likely still available: many market participants likely traded. Genworth CDS between June 21, 2021, and September 20, 2021, and, therefore, have contracts with a coupon of 500 basis points and a maturity of September 20, 2021.  

A short mathematical prelude is needed here before moving to the calculation of upfront amounts. Simple credit risk models assume a constant hazard rate, $\lambda$ , defined such that the probability of default over a short time interval, dt years, equals Adt. If the hazard rate is. $10\%$ and that time interval. is six months, then the probability of default over the six months is $10\%/2$ or $5\%$ , and the probability of "survival," meaning no default, is $95\%$ . To survive over a year requires survival over both the first and second six months, which has a probability of $95\%\times95\%=90.25\%$ And this survival probability, in turn, implies that the probability of default over the year, whether in the first or the second six months, is. $1-90.25\%$ , or $9.75\%$ . Note that breaking the one-year time frame into two six-month periods makes the probability of survival over the year,. $90.25\%$ , greater than $90\%$ $100\%$ minus the annual hazard rate of. $10\%$ ): with $95\%$ survival over the first six months, only that. $95\%$ - not the full $100\%$ - is subject to default over the second six months. Correspondingly, the probability of default over the year, $9.75\%$ , is less than the annual hazard rate of. $10\%$  

More generally, Appendix A14.1 shows that if the hazard rate is applied continuously, then the cumulative survival probability over $T$ years, $C S(T)$ and the cumulative default probability over $T$ years, $C D(T)$ , are,  

$$
C S(T)=e^{-\lambda T}
$$  

$$
C D(T)=1-e^{-\lambda T}
$$  

TABLE 14.10  Calculating the Upfront Amount for 100 Notional Amount of an. Annual Pay Five-Year CDS on Genworth at a Coupon of 500 Basis Points and a CDS Spread of 558.92 Basis Points, as of August 16, 2021. The Recovery Rate Is $40\%$ . Probabilities and the Hazard Rate Are in Percent..   


<html><body><table><tr><td>Year</td><td>Discount Factor</td><td>Cumulative Survival Probability</td><td>Default Probability</td></tr><tr><td>1</td><td>0.998462</td><td>91.099</td><td>8.901</td></tr><tr><td>2</td><td>0.994257</td><td>82.991</td><td>8.109</td></tr><tr><td>3</td><td>0.985062</td><td>75.604</td><td>7.387</td></tr><tr><td>4</td><td>0.973167</td><td>68.875</td><td>6.729</td></tr><tr><td>5</td><td>0.959797</td><td>62.744</td><td>6.130</td></tr><tr><td></td><td>Hazard Rate</td><td></td><td>9.322</td></tr><tr><td></td><td>Value ofFeeLeg</td><td></td><td>21.995</td></tr><tr><td></td><td>Value of Contingent Leg</td><td></td><td>21.995</td></tr><tr><td></td><td>Upfront Amount</td><td></td><td>2.319</td></tr></table></body></html>  

To illustrate the use of these equations with the same annual hazard rate of $10\%$ , the cumulative survival probability over four years is. $e^{-10\%\times4}=$ $67.0\%$ , and the cumulative default probability is one minus that, or $33.0\%$ Note again that, because of the compounding of survival probabilities over many short time intervals, the four-year survival rate of $67.0\%$ is significantly greater than one minus four years at. $10\%$ , or $60\%$ , and, correspondingly, the four-year default rate of. $33.0\%$ is significantly less than. $40\%$  

Appendix A14.2 gives general, algebraic formulae for the market convention of calculating a CDS upfront amount given a quoted CDS spread. The text, however, continues with an example described in Table 14.10: 100 notional amount of a five-year Genworth CDS as of August 16, 2021. The CDS coupon is 500 basis points; the market CDS spread is 558.92 basis points; and the assumed recovery rate is $40\%$ .15 For simplicity, it is assumed that premium payments are annual (instead of quarterly).  

The basic idea behind the market convention is as follows. First, find the hazard rate that makes the Genworth CDs "fair" in the sense that the expected discounted value of paying for protection with the CDS spread - here 558.92 basis points per year - is equal to the expected discounted value of receiving compensation in the event of default - here $100\times(1-40\%)=60$ . This hazard rate turns out to be $9.322\%$ . Second, using that hazard rate, find the expected discounted value to the protection. buyer of paying the actual CDS coupon - here 500 basis points - instead of the CDS spread of 558.92 basis points. That value turns out to be 2.319.. Hence, to buy 100 face amount of Genworth protection at a coupon of 500 basis points, when the CDS spread is actually 558.92, the protection buyer. has to pay an additional 2.319 upfront..  

The first column of Table 14.10 lists the years of the five annual pay-. ments. The second column gives the discount factors from the LIBOR swap curve as of the pricing date. The third and fourth columns give the cumulative survival and default probabilities at the end of each year, computed with Equations (14.4) and (14.5) and a hazard rate of. $9.322\%$ . This hazard rate is shown in the table, and its derivation is given presently..  

Like all CDS, the Genworth CDS in the example can be described as having two legs: a fee leg and a contingent leg. The fee leg comprises the pay-. ments of the premium from the buyer to the seller of protection. At the end of any year in which there has not been a default, the buyer in the current calculation has to pay the CDS spread of 558.92 basis points on the 100 notional amount, or 5.5892. If there is a default over the year, then the buyer has. to pay the accrued coupon from the start of the year to the time of default. If, for example, the default occurred after three months, or one-quarter of. a year, the buyer would have to pay one-fourth of the coupon, or 1.3973;. if the default occurred in the middle of the year, the buyer would have to pay 2.7946. For simplicity, however, the market convention for calculating upfront amounts assumes accrual for half the period, or, in this example, for half of the year. (This assumption has less impact on the calculations in practice, because coupons are actually paid quarterly.).  

Continuing with the example, then, the buyer's payment on the fee leg at the end of the first year is 5.5892 if there is no default over the year, and 2.7946 if there is. The probability of these two contingencies are reported in the table as $91.099\%$ and $8.901\%$ , respectively. Hence, the expected present value of this payment is,  

$$
0.998462[91.099\%\times5.5892+8.901\%\times2.7946]=5.332
$$  

Analogous calculations can be repeated for each of the next four years, using the appropriate survival and default probabilities and discount factors. Then, summing the results gives the present value of the fee leg, reported in Table 14.10, as 21.995.  

With respect to the contingent leg, the seller of protection pays the buyer. 60 in any year that Genworth experiences a default. The expected discounted value of that contingent payment in the third year, for example, is,.  

$$
0.985062\times7.387\%\times60=4.366
$$  

Performing this calculation for each of the five years and summing the results gives the present value of the contingent leg, reported in Table 14.10, as 21.995.  

Because the discounted expected values of the fee and contingent legs are equal, the hazard rate of $9.322\%$ correctly reflects the market CDS spread of 558.92 basis points. Solving for this hazard rate in the first place requires iterating through the calculations just described. For example, after setting up the calculations in Table 14.10 as an Excel spreadsheet, the built-in solver can be used to find the hazard rate that results in equal values for the fee and contingent legs.  

The stage is now set for calculating the upfront amount such that paying this upfront amount at the initiation of the CDS and then paying a running premium of 500 basis points has the same discounted expected value as paying nothing upfront and then a running premium of 558.92 basis points. As derived previously, the expected discounted value of the fee leg making payments of 5.5892 is 21.995. It follows, then, that the value of payments of the standardized coupon of five in the fee leg is $21.995\times5/5.5892=19.676$ Therefore, the required upfront payment is just the difference, $21.995-$ 19.676, or 2.319: an upfront payment of 2.319 and a running premium of five (which is worth 19.676) has the same value as no upfront payment and a running premium of 5.5892 (which is worth 21.995).  

A moment's reflection reveals that the upfront amount is positive whenever the CDS spread is greater than the standardized coupon. If the market CDS spread of Genworth were 450 on August 16, 2021, then the upfront amount turns out to be $-2.051$ . Buying protection by receiving 2.051 upfront and paying a running premium of five has the same value as no upfront amount and paying a running premium of 4.50.16  

This section concludes by emphasizing that the quoting of an upfront. amount from a CDS spread is only a convention, like the relationship. between price and yield-to-maturity. Market participants form their own views on upfront amounts at which they are willing to trade CDS. They may not be willing, for example, to assume a particular recovery rate or that the hazard rate is constant over time. But they all use the accepted market. conventions to calculate upfront amounts from a quoted CDS spread or vice versa.  
