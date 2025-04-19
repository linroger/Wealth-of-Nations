---
tags:
  - bond_pricing
  - credit_risk
  - fixed_income
  - market_participants
  - yield_spreads
aliases:
  - BTP-Bund spread
  - JNJ bond
  - bond spreads
  - yield spread
key_concepts:
  - European sovereign debt
  - German government bond
  - benchmark bonds
  - coupon effect
  - fixed income securities
  - idiosyncratic factors
  - market-wide interest rates
  - yield spreads
---

# 3.5 SPREADS  

There are many fixed income securities. Their prices all depend in some way. on market-wide interest rates, but also on idiosyncratic factors, like credit risk, tax treatment, and unique supply and demand considerations. To make. sense of pricing in this context, market participants often quote spreads of one instrument or set of instruments relative to others..  

Consider the European sovereign debt market. Because the market per-. ceives the credit characteristics of each country's bond issues differently, some countries typically pay higher interest rates on their bonds than other countries. These differences could be described by comparing individual prices and yield. As of May 2021, for example, the Italian government bond or BTP (Buoni del Tesoro Poliennali) 0.60s of $08/1/2031$ (issued in February 2021) sold at a price of 95.502, or a yield of $1.066\%$ . At the same time, the German government bond or Bund 0.00s of $02/15/2031$ (issued in January 2021) sold at a price of 101.300, or a yield of $-0.132\%$ . Market participants often find it more intuitive, however, to describe the market by saying that the 10-year BTP-Bund spread - in this case just the difference between the two yields --- is $1.198\%$ , or about 120 basis points. Note that one basis point is defined as $0.01\%$ , so that 120 basis points is $1.20\%$ . In any case, spreads of government bonds in many countries are often quoted against a Bund benchmark because Germany is widely regarded as having the strongest credit in the region.  

Yield spreads can also be convenient for trading bonds that are less. liquid than benchmark bonds. For example, in August 2020, Johnson. $\&$ Johnson (JNJ) issued a number of long-term bonds, including its 20-year  

2.10s due 09/1/2040. The pricing of this new issue was quoted as 75 basis points above the on-the-run 30-year Treasury bond, the 1.25s of 05/15/2050. Quoting yield against a Treasury benchmark is not only intuitive, but also facilitates trading in fast-moving markets. A fixed yield spread over a liquid Treasury bond allows the offering price of the JNJ bond to change smoothly and predictably with market levels until the new issue is actually sold.  

While yield spreads are particularly easy to calculate and use, they are. actually difficult to interpret carefully for two reasons. First, in many situations there is no liquid, benchmark bond with exactly the same maturity as the less-liquid bond. Taking the differences in yields, therefore, mixes differences in term with other differences, like credit. In the 20-year JNJ issue,. for example, the spread of 75 basis points includes not only the credit risk. of JNJ relative to the US Treasury, but also the difference between 20- and. 30-year yields. Second, spreads of yields, even of the same maturity, inherit the weakness of yield described earlier and expressed as the coupon effect. Put another way, the yield spread between bonds of the same maturity can be. misleading if their coupons are different and their underlying term structures. have different shapes.  

Bond spreads are a more careful and more meaningful formulation of. expressing price differences as a spread of rates.4 To illustrate, consider. again the US Treasury 7.625s of 11/15/2022. Table 1.3 derives discount factors from a set of newly issued, benchmark Treasury bonds, which did not include the 7.625s of 11/15/2022. Table 1.4 then shows that the 111.3969 market price of the 7.625s of 11/15/2022 is 11.72 cents rich relative to its 111.2797 present value, which is computed using the discount factors. derived from the benchmark bonds. The point of a bond spread is to express. this 11.72 cents of richness as a spread of rates. Bond spreads can be computed relative to par, spot, or forward rates, but this section works with forward rates. The forward rates implied from the discount factors in Table 1.3 are $0.0154\%$ $0.1008\%$ , and $0.1833\%$ , for terms of 0.5, 1.0, and 1.5. years, respectively. Therefore, the 111.2797 present value of the 7.625s of 11/15/2022 is given by,  

$$
\begin{array}{r}{111.2797=\frac{3.8125}{\left(1+\frac{0.0154\%}{2}\right)}+\frac{3.8125}{\left(1+\frac{0.0154\%}{2}\right)\left(1+\frac{0.1008\%}{2}\right)}}\ {+\frac{103.8125}{\left(1+\frac{0.0154\%}{2}\right)\left(1+\frac{0.1008\%}{2}\right)\left(1+\frac{0.1833\%}{2}\right)}}\end{array}
$$  

The bond spread with respect to forward rates is defined as the spread that, when added to each forward rate, sets the bond's present value equal to its market price. In this case, denoting the spread by $s$  

$$
{\begin{array}{r l}&{11.3969={\cfrac{3.8125}{\left(1+{\frac{0.0154^{\circ}\psi_{*}}{2}}+s\right)}}}\ &{\quad\quad+{\cfrac{3.8125}{\left(1+{\frac{0.0154^{\circ}\psi_{*}}{2}}+s\right)\left(1+{\frac{0.1008^{\circ}\psi_{*}}{2}}+s\right)}}}\ &{\quad\quad\quad+{\cfrac{103.8125}{\left(1+{\frac{0.0154^{\circ}\psi_{*}}{2}}+s\right)\left(1+{\frac{0.1008^{\circ}\psi_{*}}{2}}+s\right)\left(1+{\frac{0.1833^{\circ}\psi_{*}}{2}}+s\right)}}}\end{array}}
$$  

Solving, $s=-0.0727\%$ , or about minus seven basis points. The spread is negative because the bond is rich; that is, the market price is above the present value as computed with the benchmark curve. In other words, the benchmark forward curve has to be shifted down to recover the relatively high market price.5  

A bond's spread can be interpreted as its extra return, relative to the benchmark bonds, if rates "stay the same," or if interest rate risk is hedged away. This interpretation is developed in the next section and in Chapter 7.  

Because bond spread can be interpreted as an indicator of relative value, many practitioners routinely compute bond spreads, whether it be spreads of various European government bonds to German Bunds, spreads of cor-. porate bonds to government bonds or swaps, spreads of government bonds to benchmark government bonds, or even spreads of government bonds to swaps. With respect to the last of these, it had once been standard to compute spreads of government bonds only to the most liquid government bonds. But as LIBOR swaps became more and more liquid, and as the idiosyncratic. pricing of individual government bonds became more apparent, market participants began to compute spreads of government bonds to LIBOR swaps. as well. SOFR swaps, which are now replacing LIBOR swaps, may take on the same role in the future..  

# 3.6APPLICATION: SPREADS OF HIGH-COUPON TREASURIES  

To illustrate the use of bond spreads in assessing relative value, the top panel of Table 3.3 and the gray lines in Figure 3.4 report the bond spreads of selected Treasury bonds relative to benchmark Treasury bonds and also relative to SOFR swaps. The benchmark Treasuries, by definition, have zero spreads relative to themselves. Consistent with the analysis of high-coupon bonds in terms of the law of one price in Chapter 1, high-coupon bonds are rich relative to benchmark Treasuries, with bond spreads ranging from $-0.8$ to $-18.9$ basis points. Traders and investors can use these spreads in. their investment decisions. Because these bonds are rich, buying them sacrifices return relative to buying benchmark bonds, implying that there needs to be some reason, not considered here, to purchase these bonds. Conversely, because these bonds are rich, selling or shorting them picks up return relative to benchmark bonds, absent some factor not considered in this analysis.  

As mentioned already, market practitioners sometimes use swaps as a benchmark against which to compute government bond spreads. For the bonds in this example, spreads to SOFR swaps are reported in the bottom panel of Table 3.3 and with the black lines in Figure 3.4. With respect to the relative pricing of high-coupon bonds, the SOFR spreads tell the same story as the Treasury spreads: high-coupon bonds have lower (and more negative) spreads and, therefore, are rich to benchmark Treasury bonds. In fact, the differences between the spreads of high-coupon bonds and of benchmark bonds are about the same whether measured against benchmark bonds or SOFR swaps. With respect to relative pricing across term, however, the results are quite different. Measured against SOFR swaps, longer-term bonds - both high-coupon and benchmark - are much cheaper than shorter-term bonds. Consider, for example, the spreads of the 5.25s of 11/15/2028 and the 8s of 11/15/2021. The difference in their SOFR spreads is $23.5-(-20.8)$ or 44.3 basis points, while the difference in their Treasury spreads is. $-2.1-(-18.9)$ or only 16.8 basis points. And the difference in SOFR spreads between the 3.125s of 11/15/2028 and the 2.875s of 11/15/2021 is $26.4-(-1.9)$ or 28.3 basis points, while the difference in their Treasury spreads, because they are both benchmark bonds, is, by definition, zero. Hence, longer-term bonds look much cheaper relative to short-term bonds when measured against SOFR than against Treasuries.  

TABLE 3.3 Spreads of Selected US Treasury Bonds to Benchmark Treasuries ande to SOFR Swaps, as of May 14, 2021. Coupons Are in Percent, and Spreads Are in Basis Points.   


<html><body><table><tr><td></td><td colspan="2">Benchmark Treasuries</td><td colspan="2">High-Coupon Treasuries</td></tr><tr><td>Maturity</td><td>Coupon</td><td>Spread</td><td>Coupon</td><td>Spread</td></tr><tr><td colspan="5">Spreads to Benchmark Treasuries</td></tr><tr><td>11/15/2021</td><td>2.875</td><td>0.0</td><td>8.000</td><td>-18.9</td></tr><tr><td>11/15/2022</td><td>1.625</td><td>0.0</td><td>7.625</td><td>-7.3</td></tr><tr><td>11/15/2024</td><td>2.250</td><td>0.0</td><td>7.500</td><td>-5.8</td></tr><tr><td>11/15/2026</td><td>2.000</td><td>0.0</td><td>6.500</td><td>-0.8</td></tr><tr><td>11/15/2027</td><td>2.250</td><td>0.0</td><td>6.125</td><td>-2.4</td></tr><tr><td>11/15/2028</td><td>3.125</td><td>0.0</td><td>5.250</td><td>-2.1</td></tr><tr><td colspan="5">Spreads to SOFR Swaps</td></tr><tr><td>11/15/2021</td><td>2.875</td><td>-1.9</td><td>8.000</td><td>-20.8</td></tr><tr><td>11/15/2022</td><td>1.625</td><td>3.1</td><td>7.625</td><td>-4.2</td></tr><tr><td>11/15/2024</td><td>2.250</td><td>5.9</td><td>7.500</td><td>-0.2</td></tr><tr><td>11/15/2026</td><td>2.000</td><td>16.0</td><td>6.500</td><td>14.4</td></tr><tr><td>11/15/2027</td><td>2.250</td><td>22.6</td><td>6.125</td><td>19.0</td></tr><tr><td>11/15/2028</td><td>3.125</td><td>26.4</td><td>5.250</td><td>23.5</td></tr></table></body></html>

Source: Author Calculations.  

![](e394a38ab71ef7416d76dbb05af8163c095b8f434b8efa1ff0dcfdaa6ce97933.jpg)  
FIGURE 3.4  Spreads of Selected US Treasury Bonds to Benchmark Treasuries and to SOFR Swaps, as of May 14, 2021.  

To understand this difference in relative valuations, Figure 3.5 graphs.   
the two forward curves. Past a term of 2.5 years, the SOFR forward curve.   
is not as steep as the Treasury forward curve. This means that the SOFR curve assigns relatively high prices to longer-term Treasury bonds and,.   
consequently, makes their market prices look relatively cheap. Equivalently,.   
SOFR spreads at longer terms need to be larger to get pricing back up to.  

![](ae041b602d75b746364baf34d7e930c1b7250b789648c1844d5e6c6ae914d4a8.jpg)  
FIGURE 3.5  Benchmark Treasury and SOFR Forward Rate Curves, as of May 14, 2021.  

the levels of Treasury forwards. The lesson here to practitioners is that using spreads against a curve from another market may have liquidity. advantages, as mentioned earlier, but can complicate the interpretation of. spreads and trades based on those spreads. In the present case, the relative. cheapness of longer-term, high-coupon Treasuries, as indicated by their relatively large SOFR spreads, is actually a combination of their relative cheapness against the Treasury curve and the relative flatness of the SOFR curve. Furthermore, trades that attempt to lock in these spreads of Treasury. bonds against SOFR spreads, called asset swaps, require trades not only. in Treasuries but in matched-maturity SOFR swaps as well. Chapter 14 discusses asset swap trades in greater detail..  

# 3.7UNCHANGED RATE SCENARIOS FOR P&L ATTRIBUTION  

This section and the next describe how ex-post P&L or returns can be broken down into components so as to understand the sources of profits or losses from a trade or investment. One of these components, carry-roll-down,. is the change in value or the return of a bond or portfolio of bonds over time, assuming that "rates do not change" over the P&L or return horizon. The purpose of this section is to present two commonly assumed scenarios. to represent rates not changing: realized forwards and an unchanged term structure.  

TABLE 3.4  Realized Term Structure of Treasury Forward Rates on Various Dates, as of November 13, 2020. Rates Are in Percent.   


<html><body><table><tr><td>Term</td><td>11/13/20</td><td>05/14/21</td><td>11/15/21</td><td>05/14/22</td></tr><tr><td>0.5</td><td>0.1013</td><td>0.1746</td><td>0.2429</td><td>0.2185</td></tr><tr><td>1.0</td><td>0.1746</td><td>0.2429</td><td>0.2185</td><td></td></tr><tr><td>1.5</td><td>0.2429</td><td>0.2185</td><td></td><td></td></tr><tr><td>2.0</td><td>0.2185</td><td></td><td></td><td></td></tr></table></body></html>  

Table 3.4 illustrates realized forward scenarios as of November 13, 2020, with sequential six-month horizons. The 11/13/2020 column gives. the then-prevailing US Treasury term structure of six-month forward rates.. Using the notation of Chapter 2, the first six-month forward rate, $f(0.5)$ is $0.1013\%$ ; the six-month rate, six months forward,. $f(1)$ , is $0.1746\%$ ; the six-month rate, one year forward,. $f(1.5)$ , is $0.2429\%$ ; etc. The next three. columns give the assumed term structures of forward rates on subsequent. dates. Note that the 11/13/2020 date is selected as a business day approximately six months before 05/14/2021, which is the pricing date for many of. the examples in this text. The 11/15/2021 and. $05/14/2022$ dates are somewhat arbitrarily chosen as business days approximately six months apart.  

Realized forward scenarios assume that today's six-month rate, $t$ years forward, will be the six-month rate $t$ years from now. In terms of the table, the November 13, 2020, six-month rate, six months forward, $0.1746\%$ , is assumed to be the six-month rate in six months, that is, on May 14, 2021. The November 13, 2020, six-month rate, one year forward,. $0.2429\%$ is assumed to be the six-month rate on November 15, 2021; and the November 13, 2020, six-month rate, 1.5 years forward,. $0.2185\%$ , is assumed to be the six-month rate on May 14, 2022. Furthermore, all along. the way, the forward rates slide down the curve. The November 13, 2020, six-month rate, one-year forward, $0.2429\%$ , becomes the six-month rate, six months forward, on May 14, 2021, before becoming the six-month rate on November 15, 2021. And the November 13, 2020, six-month rate, 1.5 years forward, $0.2185\%$ , becomes the six-month rate, one year forward, on May 14, 2021, and the six-month rate, six months forward, on November 15, 2021, before becoming the six-month rate on May 14, 2022..  

The scenario of an unchanged term structure assumes that all forward rates remain the same period after period. In terms of Table 3.4, this scenario assumes that the term structure of forward rates on November 13, 2020, is the same as the term structure on May 14, 2021, November 15, 2021, and May 14, 2022. In terms of rates, $f(0.5)$ stays at $0.1013\%$ $f(1)$ stays at $0.1746\%$ ; and so forth.  

TABLE 3.5Return on a $T$ -Year Zero Coupon Bond Under the Scenarios of Realized Forward Rates and an Unchanged Term Structure, with Annual Periods.   


<html><body><table><tr><td></td><td>RealizedForwards</td><td>Unchanged Term Structure</td></tr><tr><td rowspan="2">Po</td><td>1</td><td>1</td></tr><tr><td>(1+f(1))(1+f(2)).(1+f(T-1))(1+f(T)</td><td>(1+f(1))(1+f(2))..(1+f(T-1))(1+f(T))</td></tr><tr><td rowspan="2">P1</td><td>1</td><td>1</td></tr><tr><td>(1+f(2))…(1+f(T-1))(1+f(T))</td><td>(1+f(1))(1+f(2))..(1+f(T-1))</td></tr><tr><td>P-1 Po</td><td>f(1)</td><td>f(T)</td></tr></table></body></html>  

Chapter 8 characterizes the realized forward scenario as the pure expectations hypothesis and the unchanged term structure scenarios as the pure risk premium hypothesis. For now, however, Table 3.5 gives some insight into bond returns under the two scenarios by deriving the annual return on a zero coupon bond of maturity. $T$ , with annual periods. The price of the. bonds today, $P_{0}$ , are both given by discounting their maturing face value of one unit of currency by the annual forward rates $f(1)$ through $f(T)$ . In one year, the bonds are both. $(T-1)$ -year zeros, and their prices,. $P_{1}$ , differ according to the assumed scenario. Under realized forwards, the first forward rate becomes $f(2)$ , etc., out to $f(T)$ giving the $P_{1}$ value in that column of the table. Under an unchanged term structure, the appropriate forward rates are $f(1)$ through $f(T-1)\colon f(T)$ drops out, because the bond matures in $T-1$ years. The last row of the table gives the one-year return of the bond, which is simply $(P_{1}-P_{0})/P_{0}$ , or $P_{1}/P_{0}-1$  

The table shows that, under realized forwards, the one-year return on the $T$ -year zero is the one-year rate,. $f(1)$ . Appendix A3.3 shows that this. result is very general: under realized forwards, the return on any bond equals the short-term rate. And if the bond trades at a constant spread to the benchmark curve, the return equals the short-term rate plus that spread. To the extent the scenario is considered reasonable, this result is useful for P&L attribution, because any return different from the short-term rate is attributable not to the passage of time, but to other factors, like changes in rates or spreads.  

Under the assumption of an unchanged term structure, the one-year return on the $T$ -year zero is the initial forward rate from. $T-1$ to $T$ .This result does not generalize as easily as the return under realized forwards, and the intuition behind both results becomes clear in Chapter 8. For the purpose of this section, however, suffice it to say that if a trader or investment manager finds the unchanged term structure scenario a more reasonable expression of "rates stay the same," then returns under that scenario can be considered a baseline, and return deviations from that baseline are attributed to other factors.  
