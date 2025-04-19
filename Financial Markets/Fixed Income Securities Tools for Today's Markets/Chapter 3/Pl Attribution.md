---
tags:
  - bond_investing
  - carry_roll_down
  - interest_rates
  - p_and_l_attribution
  - term_structure
aliases:
  - P&L Breakdown
  - Profit and Loss Attribution
  - Return Attribution
key_concepts:
  - Attribution reports
  - Cash carry
  - Changes in rates
  - Changes in spreads
  - Coupon income
  - Financing arrangements
  - Forward loan example
  - P&L component parts
  - Term structure scenario
---

# 3.8 P&L ATTRIBUTION  

As mentioned earlier, breaking down P&L or return into component parts is extremely useful for understanding how money is being made or lost in a trading book or investment portfolio. In addition, attribution reports can often catch errors of many sorts (e.g., buying or selling the wrong bond; buying instead of selling or vice versa; incorrect market or position data feeds).  

P&L attribution can be quite detailed, but, for the purposes of this. chapter, the focus is on a single bond rather than a portfolio; the holding period is fixed at a coupon payment period; and attribution is to four factors:. cash carry, carry-roll-down, changes in rates, and changes in spreads.6.  

Cash carry captures interim cash flows from a bond investment, typically from coupons and from financing arrangements (i.e., borrowing funds to buy bonds or borrowing bonds to short them). The example of this section ignores financing, however, which is the subject of Chapter 10..  

Carry-roll-down captures the P&L or return from changes in price when. neither rates nor spreads change. The previous section described how rates not changing might be modeled as realized forwards or as an unchanged. term structure. The example of this section assumes realized forwards.  

Because "carry" and "roll-down" are used differently by different practitioners, the nomenclature adopted here requires some elaboration. Broadly speaking, carry is meant to convey how much a position earns due to the passage of time, holding everything else constant. A clean example is a par bond when the term structure of interest rates is flat and unchanging. In that case, because the bond's price is always par, its carry is clearly its coupon income minus costs of financing. Another clean example is a premium bond when the term structure, again, is flat and unchanging. In that case, because the bond's price is pulled to par over time (Figure 3.1), its carry is clearly its coupon income minus the decline in price minus costs of financing.  

Roll-down, broadly speaking, is meant to convey how much a position. earns as it matures and is valued at a different part of the term structure,. holding everything else constant. A clean example of this concept is a forward loan. Referring to the rates in Table 3.4, say that, on November  

13, 2020, an investor makes a six-month loan, one year forward, at $0.2429\%$ , and has adopted the unchanged term structure scenario for P&L attribution. Six months later, the investor's position will have matured to a six-month loan, six months forward to be valued at the "unchanged" rate of $0.1746\%$ , which is the six-month rate, six months forward, on November 13, 2020. Hence, holding everything else constant, the forward loan has gained in value: the investor had locked in a loan rate of. $0.2429\%$ on November 13, 2020, and, six months later, the loan is valued at $0.1746\%$ In other words, the loan increased in value because it rolled down the curve.  

While there are some cases in which it is clear how to separate carry. from roll-down, there are many cases in which it is not so clear. Consider a. premium bond when the term structure is upward sloping and unchanging.. The resulting P&L would be a combination of carry - coupon, pull-to-par,. and financing costs - and roll-down, as the bond's cash flows are discounted at lower rates.  

This text takes the position that the important division in P&L attribution is between what happens due solely to the passage of time and what happens when rates and spreads change. Furthermore, to be consistent with the nomenclature in forwards and futures markets, discussed in Chapter 11, the phrase cash carry is preserved to mean coupon income minus financing costs. Therefore, carry-roll-down here denotes P&L or return due to the passage of time excluding cash carry. The name reflects carry-roll-down's being a mix of what might otherwise be classified as either carry or roll-down.  

The remaining two components of P&L or return described in this. chapter, those due to changes in rates and to changes in spreads, are relatively self-explanatory and are discussed presently.  

The text now turns to a detailed. $\mathrm{P}\&\mathrm{L}$ attribution for the US Treasury 7.625s of 11/15/2022 over the period November 13, 2020, to May 14, 2021. Note that both of these pricing dates are Fridays, so that settlement is on November 16, 2020, and May 17, 2021, respectively. Therefore, full prices given here include one and two days of accrued interest, respectively, and an investor over this holding period does not receive the coupon paid on. November 15, 2020, but does receive the coupon paid on May 15, 2021.  

The computation and results of the P&L attribution are given in Tables 3.6, 3.7, and 3.8. The first row of Table 3.6 gives the market price and spread of the 7.625s of $11/15/2022$ as of the beginning of the period, November 13, 2020. This spread of $-1.16$ basis points is relative to the benchmark Treasury term structure on November 13, 2020, which is reported in the second column of Table 3.7. The computation of spread from market price is not shown here but can be computed along the same lines as Equation (3.14).  

The second row of Table 3.6 computes a price for the bond as of the. end of the period, May 14, 2021, assuming realized forwards - given in the third column of Table 3.7 - and an unchanged spread of -1.16 basis points.  

TABLE 3.6 Data for the P&L Attribution of the 7.625s of 11/15/2022 from November 13, 2020, to May 14, 2021. Spreads Are in Basis Points, and Percent Change Is Relative to Price on November 13, 2020..   


<html><body><table><tr><td>Pricing Date</td><td>Term Structure</td><td>Spread</td><td>Price</td><td>Change</td><td>Percent Change</td></tr><tr><td>11/13/2020</td><td>11/13/2020</td><td>-1.16</td><td>114.87654</td><td></td><td></td></tr><tr><td>5/14/2021</td><td>RealizedForwards</td><td>-1.16</td><td>111.11555</td><td>-3.76099</td><td>-3.2739%</td></tr><tr><td>5/14/2021</td><td>5/14/2021</td><td>-1.16</td><td>111.29847</td><td>0.18292</td><td>0.1592%</td></tr><tr><td>5/14/2021</td><td>5/14/2021</td><td>-7.27</td><td>111.39690</td><td>0.09843</td><td>0.0857%</td></tr></table></body></html>  

TABLE 3.7Term Structures of Forward Rates for the P&L Attribution of the 7.625s of 11/15/2022 from November 13, 2020, to May 14, 2021. Rates Are in Percent.   


<html><body><table><tr><td colspan="4">TermStructuresofForwardRates</td></tr><tr><td>Term</td><td>11/14/20</td><td>Realized Forwards</td><td>5/14/21</td></tr><tr><td>0.5</td><td>0.1013</td><td>0.1746</td><td>0.0154</td></tr><tr><td>1.0</td><td>0.1746</td><td>0.2429</td><td>0.1008</td></tr><tr><td>1.5</td><td>0.2429</td><td>0.2185</td><td>0.1833</td></tr><tr><td>2.0</td><td>0.2185</td><td></td><td></td></tr></table></body></html>  

Once again, this spread calculation can be done along the lines of Equation (3.14). The change in price from 114.88, in the first row of Table 3.6, to 111.12, in the second row of the table, represents what happens to the bond price due to the passage of time alone: the realized forwards scenario is taken here to mean no change in rates, and the spread is also unchanged. Therefore, the dollar difference in these prices,. $-3.76$ and the difference as a percentage of the initial price,. $-3.27\%$ , is attributed to carry-roll-down and reported as such in Table 3.8. The carry-roll-down is large and negative because the bond has a coupon rate very much above the market rate and, consistent with the discussion in Section 3.2, its price is pulled down to par over time..  

The third row of Table 3.6 computes a price for the bond as of May 14, 2021, assuming the actual Treasury term structure on that date, given in the fourth column of Table 3.7, and a still-unchanged spread from the beginning of the period. Yet again, this price can be computed along the lines of Equation (3.14). The difference between the resulting price of 111.30 and the price of 111.12 in the second row represents the P&L due to a change in rates - from the realized forwards scenario of "no change" to the actual term structure on May 14, 2021. The differences of 0.18 and $0.16\%$ are reported in Table 3.8 as the rates component row of the attribution. This component  

TABLE 3.8P&L Attribution of the 7.625s of 11/15/2022 from November 13, 2020, to May 14, 2021. Returns Are in Percent.   


<html><body><table><tr><td>Component</td><td>P&L</td><td>Return</td></tr><tr><td>Cash Carry</td><td>3.81250</td><td>3.3188</td></tr><tr><td>Carry-Roll-Down</td><td>-3.76099</td><td>-3.2739</td></tr><tr><td>Rates</td><td>0.18292</td><td>0.1592</td></tr><tr><td>Spread</td><td>0.09843</td><td>0.0857</td></tr><tr><td>Total</td><td>0.33286</td><td>0.2898</td></tr></table></body></html>  

of the attribution is positive because, as is clear from Table 3.7, rates fell.   
from the realized forwards scenario to the actual rates on May 14, 2021.  

The fourth and final row of Table 3.6 gives the market price of the bond on May 14, 2021, along with its. $-7.27$ basis-point spread relative to the. benchmark Treasury term structure on that date. This spread is actually computed in Equation (3.14). The difference between the May 14, 2021, market price and the price in the third row of the table represents the spread component of the attribution, as the only change from the third to the fourth rows is the spread. The differences of 0.10 and. $0.09\%$ are reported as such in Table 3.8. This component is positive because the bond's spread fell from November 13, 2020, to May 14, 2021; that is, the bond became richer relative to the benchmark Treasury curve..  

Table 3.8 summarizes the P&L and return attribution of the 7.625s of 11/15/2022 over the six-month period from November 13, 2020, to May 14, 2021. The first row, which has not yet been discussed, is the cash carry of 3.8125, that is, the coupon payment on May 15, 2021. (Recall that because the pricing date is on May 14 and the settlement date on May 17, the investor receives the May 15 coupon payment.) As a whole, the table breaks down the total dollar P&L of 0.33 and the total return $0.2898\%$ into the component parts of cash carry, carry-roll-down, rates, and spread. Note that the sum of the cash carry and carry-roll-down return components equals $0.0449\%$ , which is the six-month rate plus the bond spread on May 14, 2021, all divided by two, that is $(0.1013\%-0.0116\%)/2$ . This is, of course, no coincidence. As highlighted in the previous section, the annual return of any bond under the realized forward scenario is the short-term rate plus the spread, or half of that over a six-month horizon.  

A trader or investor can use $\mathrm{P}\&\mathrm{L}$ and return attribution in several ways. First, as mentioned earlier, any surprises here might be due to errors in building positions, booking positions, or data feeds. Second, because cash carry and carry-roll-down can be computed at the beginning of the period, the trader or investor can decide whether the cash flow properties of the position are acceptable. More specifically, a trade or investment that is expected to do well in the long run but expected to bleed cash in the short run may or may not be acceptable in all institutional settings. In the present example, it is known at the beginning of the period that the "no change" case will result in a positive cash flow of. $3.81250-3.76099$ or about 0.05 cents before. financing costs. Once financing costs are considered, this central case might be negative and might, in that case, be unacceptable..  

A third use of. $\mathrm{P}\&\mathrm{L}$ and return attribution is as an ex-post check on. performance. Did the investor or trader have an ex-ante view on rates and,. if so, how did realized rate changes compare with that view? Was there a. view about how the spread of the bond would evolve and, again, if so, how did that view compare with the realized spread? Many traders and investors like to ask the following, when setting up a position: What could happen. to this position that would convince me that I don't understand the relevant market forces? They would then promise themselves to exit the position if it. turned out that their understanding was flawed. P&L and return attribution. is a valuable tool in that discipline by revealing exactly where money is made. or lost.  

# DVO1, Duration, and Convexity  

This chapter, along with Chapters 5 and 6, are about measuring and hedg-. ing interest rate risk. Market participants need to understand how fixed income prices change when interest rates change to take a view on the future level or term structure of interest rates, to ensure that a portfolio of assets keeps pace with a portfolio of liabilities, or to hedge one fixed income instrument or portfolio with another. But how exactly should a "change" in rates be defined? Chapters 1 through 3 show that pricing in fixed income markets can be expressed in terms of discount factors, par rates, spot rates, forward. rates, yields, and spreads. Which of these quantities should be assumed to change and by how much?.  

In answering this question, there are two overarching trade-offs: simplicity versus empirical reality, and robustness versus model dependence. With respect to the first trade-off, a market maker who is hedging a long position in a 9.75-year bond with a short position in a 10-year bond over a short time period might reasonably rely on the simplest of frameworks, namely, that the yields of the two bonds will move up or down by the same number of basis points, that is, in parallel. A swap desk, by contrast, which is managing the risk of a portfolio of long and short swap positions of different terms, has to account for the reality that changes in rates across the term structure do not move perfectly in sync. With respect to robustness versus model dependence, a pension fund, which hedges the present value of its liabilities relative to the value of its assets, tends to prefer frameworks that are not very sensitive to assumptions about how rates of different terms vary relative to one another. An actively managed fixed income mutual fund, exchange-traded fund, or hedge fund, by contrast, which is in the business of taking views on the level of rates and on the shape of the term structure, might gravitate toward frameworks designed to incorporate subjective views.  

The one-factor metrics and hedges described in this chapter are relatively.   
simple along the lines just discussed, because they assume that rates of all.   
terms move up and down together in some fixed relation. For example, if   
the 30-year par rate changes by one basis point, it might be assumed that.   
the 10-year par rate changes by 0.99 basis points, in the same direction,.  

while the five-year rate changes by 0.8 basis points, in the same direction. The parallel-shift assumption for bond yields is another simple framework described in this chapter.  

The first several sections of this chapter introduce the metrics most often. used to describe interest rate risk, namely, Dvo1, duration, and convexity, and illustrate these metrics by showing how to hedge Norfolk South-. ern Company's 100-year or century bond with a shorter-maturity Treasury. bond. The next sections specialize the discussion to yield-based versions of these metrics, which, while more restrictive in terms of their underlying assumptions, are very intuitive and widely used in practice. The final section presents a stylized case of asset-liability management at a pension fund, which requires choosing between barbell and bullet asset portfolios. Chapters 5 and 6 continue the discussion of risk metrics and hedges with multi-factor and explicitly empirical approaches, respectively..  
