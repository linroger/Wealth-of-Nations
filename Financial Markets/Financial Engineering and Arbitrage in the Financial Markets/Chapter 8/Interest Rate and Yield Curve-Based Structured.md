---
tags:
  - bond_valuation
  - interest_rate_risk
  - inverse_floater
  - structured_products
  - yield_curve
aliases:
  - floating rate bond
  - inverse floater
  - structured notes
  - yield curve structures
key_concepts:
  - cash flow engineering
  - floating rate bond pricing
  - inverse floater coupon payout
  - investor interest rate exposure
  - structured bond building blocks
---

# 8.2 INTEREST RATE AND YIELD CURVE-BASED STRUCTURED PRODUCTS  

Swaps combined with interest rate options (caps/floors and swaptions) are the main building blocks for structured bonds. In Chapter 4, we showed how corporations issue straight bonds and then use swaps to turn fixed bond liabilities into floating, or one currency into another.. Sometimes they issue a highly structured bond and use a dealer to strip it of all complication to leave the company with a simple fixed or floating liability. The driver is often the investor demand for a customized interest rate exposure scenario. The issuer's objective is a lower cost of funding.  

In this section, we go over the cash flow engineering of several popular yield curve structures. We use flow diagrams as the exposition tool with all flows shown in per annum percent-ofprincipal terms (i.e. to convert to dollars they need to be multiplied by a quarterly or semi-annual day-count).  

A sovereign, corporate, or trust issuer sells structured notes to investors. The notes carry coupon interest subject to a formula. The floating coupon formula reflects the investor's view. of the likely future yield curve scenario. If the investor is right, he will receive more interest dollars than on a straight bullet bond. If he is wrong and his interest rate path prediction proves wrong, he will receive less. The investor may also be simply trading later cash flows for earlier. ones. The issuer enters into a series of derivative and option agreements with the structuring. dealer. The derivatives are designed to exactly replicate the coupon formula minus the profit to the dealer minus the funding subsidy to the issuer. The dealer's benefit may also be selling. out of an interest rate risk..  

We start with inverse floaters that pay high interest in low interest rate scenarios and low. interest in high interest rate scenarios. We show a capped floater where the cap on the coupon is traded for a yield enhancement. We look at a callable where a short swaption is traded for a yield enhancement. We end with periodically used designs like range floaters and index amortizing swaps.  

For our examples, we use as a starting point, the hypothetical US LIBOR and Treasury rates as of September 26, 2013 (Table 8.1).  

We use the Bond Math of Chapter 2 and curve building methods of Chapter 3 to give us the forward curve in Table 8.2..  

Using the swap valuation methods of Chapter 4, we present-value (Table 8.3) a 5-year swap to show that the zero-PV semi-annual rate on a 5-year swap against floating 3-month LIBOR is $3.3636\%$  

In order to understand the economics of the deals, the reader should also review the discussion of floating rate note pricing. A floating rate bond (with no margin) is always worth par. on coupon dates and its duration is less than the next coupon reset date..  

# 8.2.1 An Inverse Floater  

An inverse floater is a bond whose coupon payout is equal to a fixed rate minus a short-term floating rate. Such a coupon structure is often demanded during the times of low rate volatility, a steep yield curve, and when investors expect the short-term rates to remain (and be low) or to decrease. The pricing is then attractive as forwards increase with maturity.  

Using the rate inputs as of September 26, 2013, with a 5-year par swap at $3.3636\%$ semiannual, equivalent to $3.3496\%$ quarterly, rounded to. $3.35\%$ , an investor may be offered a.  

Table 8.1 US spot yield curve on September 26, 2013   


<html><body><table><tr><td rowspan="2" colspan="2">Eurodollar (CME)</td><td colspan="3">US Treasury issues</td></tr><tr><td>Maturity</td><td>Coupon</td><td>Yield</td></tr><tr><td>Dec13</td><td>98.83</td><td></td><td></td><td></td></tr><tr><td>Mar14</td><td>98.75</td><td></td><td></td><td></td></tr><tr><td>Jun</td><td>98.51</td><td></td><td></td><td></td></tr><tr><td>Sep</td><td>98.19</td><td>9/30/2015</td><td>1.625</td><td>1.657</td></tr><tr><td>Dec</td><td>97.77</td><td>9/15/2018</td><td>3.125</td><td>3.030</td></tr><tr><td>Mar15</td><td>97.35</td><td>8/15/2023</td><td>4.250</td><td>4.099</td></tr><tr><td>Jun</td><td>96.96</td><td>2/15/2041</td><td>5.375</td><td>5.000</td></tr><tr><td>Sep</td><td>96.65</td><td></td><td></td><td></td></tr><tr><td>Dec</td><td>96.35</td><td colspan="2">Money rates</td><td></td></tr><tr><td>Mar16</td><td>96.10</td><td></td><td></td><td></td></tr><tr><td>Jun</td><td>95.87</td><td>3-moLIBOR</td><td>1.1400%</td><td></td></tr><tr><td>Sep</td><td>95.65</td><td></td><td></td><td></td></tr><tr><td>Dec</td><td>95.44</td><td></td><td></td><td></td></tr><tr><td>Mar17</td><td>95.25</td><td></td><td></td><td></td></tr><tr><td>Jun</td><td>95.08</td><td></td><td></td><td></td></tr><tr><td>Sep</td><td>94.92</td><td></td><td></td><td></td></tr><tr><td>Dec</td><td>94.77</td><td></td><td></td><td></td></tr><tr><td>Mar18</td><td>94.64</td><td></td><td></td><td></td></tr><tr><td>Jun</td><td>94.51</td><td></td><td></td><td></td></tr><tr><td>Sep</td><td>94.41</td><td></td><td></td><td></td></tr><tr><td>Dec</td><td>94.31</td><td></td><td></td><td></td></tr><tr><td>Mar19</td><td>94.22</td><td></td><td></td><td></td></tr><tr><td>Jun</td><td>94.14</td><td></td><td></td><td></td></tr><tr><td>Sep</td><td>94.07</td><td></td><td></td><td></td></tr><tr><td>Dec</td><td>94.00</td><td></td><td></td><td></td></tr></table></body></html>  

5-year structured bond whose quarterly coupon is equal to  

$$
6.50-L_{3m}
$$  

We explain this structure in the diagram of Figure 8.1. To show the reduced cost of funding to ABC Corp., we separate the issuing entity from the company's operations. The two are often the same.  

On the issue date ABC Capital Corp. sells the inverse floater bonds with a quarterly coupon of $6.50\textrm{--}3$ month LIBOR $(L_{\boldsymbol{\lambda}m})$ for 100. It transfers the proceeds to its operations unit. It. enters into a swap with a notional principal of 200 to receive 3.34 and pay. $L_{3m}$ (times the appropriate day-count) on the same dates as the coupon dates. It buys a cap for which it pays 37.4 bp up front or over time the equivalent of 8 bp p.a. running (0.374 is equal to. $0.08/2$ times the sum of the discount factors from Table 8.2). The cap provides protection for the scenario that $L_{3m}$ is above 6.50 on any coupon date. In those cases, the option dealer who sold the cap. will compensate ABC Capital for the difference. If $L_{3m}$ stays below 6.50, ABC Capital will receive nothing. ABC nets 10 bp running which reduces its cost of funding to. $L_{3m}-10$ The swap dealer makes a profit on the swap (paying 3.34 while the fair rate is 3.35); the option dealer's profit is in the price of the cap. The investor gets a desired coupon formula, today paying $6.50-1.14=5.36\%$ well above today's LIBOR of $1.14\%$ . To make the economics of cash flows clear, let us examine two scenarios.  

Table 8.2US forward curve on September 26, 2013   


<html><body><table><tr><td colspan="2">Forward period time (months from today)</td><td colspan="5">Discount</td></tr><tr><td>Start</td><td>End</td><td>100- Eurodollars</td><td>Convexity adjustment</td><td>FRA rate</td><td>Zero rate (to end time)</td><td>factors (to end time)</td></tr><tr><td>0</td><td>3</td><td></td><td></td><td>1.140</td><td>1.140000</td><td>0.9971581</td></tr><tr><td>3</td><td>6</td><td>1.17</td><td>0.000</td><td>1.170</td><td>1.155000</td><td>0.9942499</td></tr><tr><td>6</td><td>9</td><td>1.25</td><td>-0.008</td><td>1.242</td><td>1.183998</td><td>0.9911723</td></tr><tr><td>9</td><td>12</td><td>1.49</td><td>-0.016</td><td>1.474</td><td>1.256479</td><td>0.9875333</td></tr><tr><td>12</td><td>15</td><td>1.81</td><td>-0.024</td><td>1.786</td><td>1.362327</td><td>0.9831435</td></tr><tr><td>15</td><td>18</td><td>2.23</td><td>-0.032</td><td>2.198</td><td>1.501485</td><td>0.9777707</td></tr><tr><td>18</td><td>21</td><td>2.65</td><td>-0.040</td><td>2.610</td><td>1.659657</td><td>0.9714321</td></tr><tr><td>21</td><td>24</td><td>3.04</td><td>-0.048</td><td>2.992</td><td>1.825959</td><td>0.9642197</td></tr><tr><td>24</td><td>27</td><td>3.35</td><td>-0.056</td><td>3.294</td><td>1.988810</td><td>0.9563442</td></tr><tr><td>27</td><td>30</td><td>3.65</td><td>-0.064</td><td>3.586</td><td>2.148245</td><td>0.9478468</td></tr><tr><td>30</td><td>33</td><td>3.90</td><td>-0.072</td><td>3.828</td><td>2.300660</td><td>0.9388619</td></tr><tr><td>33</td><td>36</td><td>4.13</td><td>-0.080</td><td>4.050</td><td>2.446149</td><td>0.9294512</td></tr><tr><td>36</td><td>39</td><td>4.35</td><td>-0.088</td><td>4.262</td><td>2.585540</td><td>0.9196523</td></tr><tr><td>39</td><td>42</td><td>4.56</td><td>-0.096</td><td>4.464</td><td>2.719426</td><td>0.9095022</td></tr><tr><td>42</td><td>45</td><td>4.75</td><td>-0.104</td><td>4.646</td><td>2.847578</td><td>0.8990597</td></tr><tr><td>45</td><td>48</td><td>4.92</td><td>-0.112</td><td>4.808</td><td>2.969826</td><td>0.8883813</td></tr><tr><td>48</td><td>51</td><td>5.08</td><td>-0.120</td><td>4.960</td><td>3.086624</td><td>0.8775003</td></tr><tr><td>51</td><td>54</td><td>5.23</td><td>-0.128</td><td>5.102</td><td>3.198326</td><td>0.8664488</td></tr><tr><td>54</td><td>57</td><td>5.36</td><td>-0.136</td><td>5.224</td><td>3.304687</td><td>0.8552788</td></tr><tr><td>57</td><td>60</td><td>5.49</td><td>-0.144</td><td>5.346</td><td>3.406508</td><td>0.8439988</td></tr></table></body></html>  

Table 8.3 The present value of a 5-year par swap on September 26, 2013   


<html><body><table><tr><td>Zero rate</td><td></td><td colspan="2">Par swap rate = 3.3636</td></tr><tr><td>(to end time)</td><td>Discount factors (to end time)</td><td>Cash flow</td><td>PV of cash flow</td></tr><tr><td>1.140000</td><td>0.9971581</td><td></td><td></td></tr><tr><td>1.155000</td><td>0.9942499</td><td>1.6818</td><td>1.6721</td></tr><tr><td>1.184664</td><td>0.9911674</td><td></td><td></td></tr><tr><td>1.257978</td><td>0.9875185</td><td>1.6818</td><td>1.6608</td></tr><tr><td>1.364726</td><td>0.9831142</td><td></td><td></td></tr><tr><td>1.504816</td><td>0.9777220</td><td>1.6818</td><td>1.6443</td></tr><tr><td>1.663938</td><td>0.9713596</td><td></td><td></td></tr><tr><td>1.831202</td><td>0.9641191</td><td>1.6818</td><td>1.6215</td></tr><tr><td>1.995023</td><td>0.9562112</td><td></td><td></td></tr><tr><td>2.155433</td><td>0.9476774</td><td>1.6818</td><td>1.5938</td></tr><tr><td>2.308828</td><td>0.9386522</td><td></td><td></td></tr><tr><td>2.455132</td><td>0.9292022</td><td>1.6818</td><td>1.5627</td></tr><tr><td>2.595214</td><td>0.9193650</td><td></td><td></td></tr><tr><td>2.729692</td><td>0.9091777</td><td>1.6818</td><td>1.5291</td></tr><tr><td>2.858358</td><td>0.8986989</td><td></td><td></td></tr><tr><td>2.981055</td><td>0.8879853</td><td>1.6818</td><td>1.4934</td></tr><tr><td>3.098249</td><td>0.8770702</td><td></td><td></td></tr><tr><td>3.210303</td><td>0.8659856</td><td>1.6818</td><td>1.4564</td></tr><tr><td>3.316980</td><td>0.8547836</td><td></td><td></td></tr><tr><td>3.419085</td><td>0.8434727</td><td>101.6818</td><td>85.7658</td></tr><tr><td></td><td></td><td>Sum =</td><td>100.0000</td></tr></table></body></html>  

![](92e730eca434c8261da1ff3efa8ed4eaf88ce8ac99725a9ae294f935003cfce3.jpg)  
Figure 8.1A 5-year $6.50\%$ minus 3-month LIBOR inverse floater  

First assume that on some coupon date $L_{3m}$ is $2.00\%$ , i.e. lower than 6.50. The bondholder's coupon is $4.50\%$ . ABC Capital Corp. receives 3.34 on the two swaps, i.e. a total of 6.68. It pays O.08 out of that for the cap and receives nothing from the cap. The remainder, equal to 6.60, plus the $L_{3m}-0.10=1.90$ it receives from ABC Operations as the cost of using the principal funds, gives it a total of 8.50. From that it pays $2\times2.00=4.00\%$ on the floating legs of the two swaps and 4.50 to the bondholders.  

Next assume that $L_{3m}$ is 7.50, i.e. higher than 6.50, on some coupon date. The bondholder's. coupon is zero. ABC Capital Corp. receives 3.34 on the two swaps, i.e. a total of 6.68. It pays 0.08 for the cap, and receives. $7.50-6.50=1\%$ as the cap payoff. It also receives. $L_{3m}-0.10=$ 7.40 from ABC Operations as the cost of using the principal funds. Out of the total of. $6.68-$ $0.08+1.00+7.40=15\%$ ABC Capital pays $2\times7.50=15\%$ on the floating legs of the two. swaps and zero to the bondholders.  

On the maturity date, ABC Operations pay back the principal $\$100$ which is forwarded to the bondholders. The net cost for using those funds to ABC Operations is $L_{3m}$ minus 0.10 irrespective of the level of $L_{3m}$ on any coupon date. The coupon on the bond looks attractive to the investors who do not believe that short-term rates will go up from the currently low level. The fixed portion of the coupon reflects double the current term swap rate net of the cost of the cap. The cap protection tends to be cheap as it has a high strike price. In most cases, the swap and the option dealer are the same, providing the issuer with a competitive quote on the entire behind-the-scenes part of the deal.  

# 8.2.2 A Leveraged Inverse Floater  

The leveraged inverse floater combines three or more swaps and a cap into a single bond. Consider the following quarterly coupon formula offered by ABC Capital to its investors:  

$$
9.60-2\times L_{3m}
$$  

It is easy to see that, compared to the standard inverse floater, all we need to do is add another swap to triple the principal on the swap, lower the strike on the cap, and double the principal on the cap. The summary diagram is shown in Figure 8.2.  

![](a1a2fde4b5ff2fe7e8aa7b866b9931f42745d6a3cf44c94809f1c390fbb3afc1.jpg)  
Figure 8.2A 5-year $9.60\%$ minus 2 times 3-month LIBOR inverse floater  

The structure looks attractive for everyone involved. The investors' coupon on day 1 is $9.60-2\times1.14=7.32$ , which is very attractive compared to the alternatives of $3.34\%$ fixed or $L_{3m}=1.14\%$ floating. The dealer makes a profit on two caps and pays bid on three swaps. The cost of each cap is 16 bp running or 74.8 bp up front, but the principal is 200. The issuer gets $L_{3m}-10$ bp financing. The investors bear the risk in this structure that short rates may. increase rapidly, which would sharply reduce or potentially eliminate the coupon payout.1  

Let us verify that the structure works by examining two scenarios: one with LIBOR below $4.80\%$ and one with LIBOR above $4.80\%$ (all amounts are in percent of the bond principal (100), and per annum, i.e. before multiplication by a day-count fraction). If LIBOR is $2\%$ On a coupon date, then ABC Capital receives 11.92:  

and it pays 11.92:  

If LIBOR is $5.5\%$ on a coupon date, then ABC Capital receives 16.82:  

![](8bdb85052508a58fa2760f5a213e143b149079cfd59674c360ad7fad0bfb4495.jpg)  
Figure 8.3 A 5-year capped floater  

and it pays 16.82:  

$2\times0.16=0.32$ for the caps $3\times5.50\%=16.50$ on the floating legs of the three swaps $0.00\%$ to the bondholders  

# 8.2.3A Capped Floater  

A capped floater is a bond whose coupon is floating, but it is capped. The investor forgoes the upside above the cap for a larger coupon now. The larger coupon comes in the form of extra margin on top of LIBOR. The issuer gets the reduced cost of financing. This structure is much simpler than an inverse floater.  

To structure the deal, ABC Capital Corp. sells the cap embedded in the coupon formula to the dealer and uses the annuitized proceeds to enhance the bond coupon. The diagram in Figure 8.3 shows the structure in which investors in the bond receive the 3-month LIBOR plus 10 bp up to $4.7\%$ . They trade off the unlikely future scenarios of LIBOR above. $4.6\%$ for the extra $0.10\%$ now.  

The investor's coupon is. $L_{3m}~+~10$ bp, but no more than 4.70. ABC get funding at. $L_{3m}\mathrm{~-~}10$ bp. The option dealer buys the 4.60 strike cap for $0.935\%$ up front or $0.20\%$ quarterly premium. If LIBOR on any coupon date is below 4.60, the cap does not pay. ABC Capital Corp. passes the $(L_{\protect3m}-10)$ interest its affiliates pay for using the proceeds of the bond, enhanced by the 20 bp premium it receives for the short cap, to the bondholders. If LIBOR on a coupon date is greater than 4.60, say 5.50, ABC Capital receives 5.40 from its affiliate (the company as a whole pays for using the funds) and O.20 as the premium for the cap. From the total 5.60, it pays the bondholders 4.70 and pays back 0.90 to the dealer as the payoff on the cap.  

# 8.2.4 A Callable  

Fixed rate bonds, floating rate bonds, and all the structured bonds can be issued in a callable. form. In such case, ABC Capital would have the right to call the bonds from the bondholders. at par or at a price specified in advance in a call schedule. The bond may be sold as a 5-year issue callable in or after one year. The call feature is more convenient than a tender offer to repurchase bonds when the issuer wants to refinance the bonds prior to maturity. If ABC. Capital chooses to retain the right to call the bonds, it will bear the cost of a higher coupon demanded by the investors. ABC Capital can also choose to sell that right to a dealer for an upfront fee, or to annuitize it. In that case, the annuitized premium the dealer pays covers that extra cost, leaving ABC with a straight fixed rate liability. The choice depends on ABC's needs and on the deal's pricing. If interest rate implied volatilities are currently high, the dealer might be willing to pay a lot for the call right, potentially reducing ABC's fixed financing cost well. below the fair fixed swap rate. Similar to the capped floater, the premium for the swaption pays. for the excess coupon paid to the bondholders and for the funding subsidy to the company..  

The 5-year bond callable in 1 year can be viewed two different ways. One is a 5-year bullet. bond with a call option to buy the bond at par. The other is a 1-year bond with a 1 year right sell for par a 4-year bond with the same coupon. When selling the call right to the dealer, the issuer usually sells a call swaption, and sometimes enters into a swap to receive fixed in order to convert the bond to a floating rate liability at a LIBOR minus the margin level..  

# 8.2.5 A Range Floater  

A range bond pays a coupon that depends on how many days during the interest accrual period a floating rate stayed within a prespecified range. The issuer desires the low cost of floating financing. It offers investors an enhanced floating (LIBOR plus spread) or fixed coupon rate for each day the floating rate does not leave the range bounds. Investors get no interest rate accrual for days when the rate is outside the range. They are betting that the rate will not jump up and/or down. The range can have upper (range cap) or lower (range floor) bounds or both (range collar). The coupon formula for any interest period might read the following:  

$L_{3m}+100\mathrm{bp}\times\mathrm{Number{of}d a y s w h e r e}0.75<L_{3m}<2.75,$ divided by 365  

The range option embedded in the coupon is sold to an option dealer in exchange for the spread and some extra margin which reduces the issuer's financing (e.g. for. $110~\mathrm{bp}$ ). The structure resembles a capped and floored floater, but it is not the same. In the capped/floored floater, the reference LIBOR rate is checked against the bounds only once at the set time of the interest accrual period. The net premium on the sold cap minus the bought floor that the issuer arranges with the dealer pays for the margin. Either none or one of the options gets triggered on the set date. In the range floater, the coupon rate may be fixed $(4\%)$ or floating $(L_{\it3m}+100)$ , but we check against the bounds every day during the interest accrual period. If, out of 92 days in the interest period, the reference rate has remained within the bounds for 46 days, then we multiply the stated coupon rate by 46/365. That is equivalent to losing half the coupon for the period. The range option can be quite complicated to price and hedge from the dealer's perspective. It is composed of a series of daily digital options. The shorter those are to expiry and the closer to the bound (strike), the more difficult they are to hedge (high gamma).  

# 8.2.6 An Index Principal Swap  

A structure attractive to mortgage bond investors who want the enhanced yield of a prepaymentexposed investment, but want to limit the unpredictability of prepayments is called an index principal (IPS) or index amortizing swap (IAR). As is often the case, the design is driven by the specific investor demand for a callable-like yield enhancement, while the issuer simply wants reduced floating financing. The issuer issues a bond with a formula coupon and principal to. the bondholders, but reverses the cash flows of the bond by entering into an IPS with a dealer. The swap is a fixed for floating swap, except the notional principal of the swap changes over. time. Each period one looks at the principal as of the last period times one minus a percentage taken from an amortization table which might look like this:  

Rate Percent Notional Amortized   
3 $0\%$   
2 $50\%$   
1 100%  

Suppose last period's principal was 100 and the index rate,. $L_{3m}$ , this period is $1.14\%$ . We use 1.14 to interpolate between 1 and 2 in the table to obtain the notional percentage equal to $93\%$ . This period, the new notional principal used to compute interest flows on both sides. of the swap is equal to the last principal times 100 minus the amortized percentage of 93, or 0.07. The new principal is thus 7..  

This procedure is intended to mimic the prepayment behavior of fixed rate mortgages.. As rates go down, homeowners refinance their mortgages. The principals of the mortgage. bonds are reduced. Similarly, the principals of the IPS bonds will be reduced, but based on a prespecified amortization table rather than the actual behavior of homeowners who often do. not refinance optimally.  

The IPS was first popularized in the mid-1990s in the US where over $50\%$ of mortgages are fixed with no prepayment penalties and a large securitized mortgage market exists. Most reference rates used were LIBOR rather than long rates (like the 10-year Treasury) providing for another interesting play on the yield curve and the relative volatility of swaptions and caps.  

# 8.3ASSET CLASS-LINKED NOTES  

Structured notes often have coupon or principal payoffs linked to the performance of equities,. currencies, or commodities. The most popular are equity-linked notes and the most common design is a principal-protected equity participation note (EPN). The design typically relies on using the proceeds (100) from selling the note to purchase a zero-coupon bond (PV of 100) with the face value equal to the principal of the note (100) and using the remainder of the proceeds minus fees to buy equity call options on the desired index. In the standard EPN the options are struck at the money, but there is not enough money to purchase the same principal amount as that of a bond. This results in less than. $100\%$ participation to the investor. To reach fuller participation, the options have to be cheaper, and so they can be purchased out-of-the-money, have barrier knock-out features, or otherwise the principal cannot be fully guaranteed. The same exact EPN design can be applied to currencies or commodities. These notes can also be offered in the form of bank CDs and ETNs..  

# 8.3.1 Principal-Protected Equity-Linked Notes  

The basic design is very simple. Suppose the principal of the note is $\$100$ and the note is sold to investors at par. Five-year zero-coupon rates are at. $4\%$ . The issuing trust sponsored by the selling dealer splits the received $\$100$ into three parts, as depicted in Figure 8.4. The first is a 5-year zero bought for the PV of $\$100$ discounted by 5 years; the second is the underwriting fee and dealer profit; the third is the equity option.  

![](f489a3b2dcd98ff1fbd2c83eefc8e963f1f17691e86962d67c7319bcd8ccb3ed.jpg)  
Figure 8.4 A5-year $60\%$ equity participation note  

The PV of $\$100$ at $4\%$ is $\$82.193$ . We assume that a 5-year at-the-money option on the. index costs $\$23,80$ per $\$100$ principal. We buy index options on $\$60$ principal. At maturity, the investor gets $\$100$ plus $60\%$ of any appreciation of the equity index over the initial level. of the index on the issue date of the note. If the index is the S&P 500 and we start at the 1,300 level and the index moves up $74\%$ over the 5-year period to 2262, the investor will get an. additional $\$44.40$ . The total redemption value of the note will be. $\$144.40$  

Of course, the option embedded in the EPN need not be a straight call. Analogous to the capped floater, we can cap the level of equity appreciation in exchange for a kicker up to that level. Instead of a margin, the easiest way is to boost the participation. The cap is accomplished with the use of an equity call spread. The trust buys at-the-money calls and sells deep out-of-the money calls. Suppose $50\%$ out-of-the-money calls at the time of the issuance trade at 5.20.. The call spread costs $25.80-5.20=20.60.$ For $\$15.48$ we can buy call spreads on $75.1\%$ of the principal. We could thus structure a note with a $75\%$ participation rate up to the cap of $37.50\%$ The $37.50\%$ cap translates into a $50\%$ out-of-the-money call on $75\%$ of the principal. If the index goes up by $74\%$ , the investor would only get $\$137.50$ upon redemption. The capped structure has an advantage over the straight one at lower levels of equity appreciation. At a $50\%$ index rise, the investor gets $\$137.50$ , while the straight $60\%$ participation note investor gets $\$130$ Figure 8.5 shows a capped structure with a higher participation rate.  

Yet another way to increase the participation rate is through a leveraged equity-linked note. Instead of buying calls on $60\%$ or $75\%$ of the principal, we buy two or three calls. To be able to afford those, they need to be packaged into a tight spread, ranged or subject to barriers. Figure 8.6 shows a structure with two return barriers set at $-5\%$ and $10\%$ . The leverage is a factor of two, and the total return cap is set at 20. The investor only gets the equity return if the index during the life of the note never drops below $5\%$ of the original level. If the index stays above the. $-5\%$ lower barrier, the investor gets double the return on the index, but only up to the maximum of $20\%$ . Implicitly, the equity option premium is spent on two at-the-money down-and-out call spreads. Each call spread (long at-the-money call and short $10\%$ out-of-the-money call) has a maximum payout of 10, and is subject to a down-and-out knock-out barrier at. $-5\%$ . We assume that each call spread is worth $\$7.50$ . We spend the total. of $\$15$ on the equity kicker; the dealer's fee is $\$2.807$  

![](c038e15a03ae97b8bdac5c40973e6430bbc47ef49c5b828eaecd5b678540d81f.jpg)  
Figure 8.5A 5-year $75\%$ equity participation note: trade a cap for a higher participation rate  

![](c56eddb3df960446de94521c9c92e335ec3baa4d992f7575f9ac8d97d03506c6.jpg)  
Figure 8.6A 5-year $2\times$ leveraged equity linked note: barrier at $-5\%$ , cap at $20\%$  

Other variations include lookback or Asian features. In a lookback, the investor may be able to lock in the highest level that the index has reached over the life of the note. Lookbacks are quite expensive, so the participation rate achieved may be low. In an Asian option structure, the investor gets the average of the index levels over the life of the option rather than the final value. Asian options are often cheaper than straight calls.  

# 8.3.2 A (Rainbow) Multi-Asset-Linked Note  

The basic design is similar to the above described equity-linked notes, except the asset returnkicker on top of the guaranteed principal is either a best-of-many option or a basket. In the. best-of-many case, the investor may get a $60\%$ participation in the best performing asset class over the life. Typically, the choices are several equity indexes (e.g. FTSE 100, S&P 500 and Nikkei 225) or disparate asset categories (equity, currency, commodity). The choices may be. currency-translated or quantoed. If the note is sold to the Japanese investors, then the FTSE 100 and S&P 500 may be translated into yen, i.e. raw index returns corrected for the currency fluctuation, or quantoed, i.e. raw pound and dollar returns taken as straight percentages and. paid in yen.  

In the rainbow basket case, each asset in the basket may have its own participation rate defined, and the return kicker is defined as the percentage change in the entire basket over the life of the note. For example, the basket may be:  

$$
(20\%\times\mathrm{S}\&\mathrm{P}\thinspace500)+(10\%\times\mathrm{FTSE}\thinspace100)+(10\%\times\mathrm{D}\mathrm{AX})+(10\%\times\mathrm{CAC40})
$$  

A more expensive version of the rainbow case is to define the percentages for each index, and then buy those percentages worth of call options, that is, to buy a basket of options on each index rather than one option on the basket. While dealers are more likely to have the expertise. in multi-equity index rainbows housed in one equity department, the disparate asset class versions of rainbows, e.g. combining commodities with equities, may be harder to handle. The delta hedging by itself may not be hard as long as all indexes and assets have futures traded on. them. The long-term volatility and the correlation exposure are the real risks of the structures on asset baskets.  

# 8.3.3 Principal-At-Risk Notes and Commodity-Tracking ETNs  

Putting all or some principal at risk is accomplished by having the issuing trust not only buy calls but also sell puts or put spreads. Just as in the previous call spread example, the objective is to boost the participation rate. The other use of the principal-at-risk design is the commodity-tracking ETN.  

Suppose, as before, the principal of the note is $\$100$ and the note is sold to investors at. par. Five-year zero-coupon rates are at $4\%$ . The issuing trust splits the received $\$100$ into three parts. The first is a 5-year zero bought for $\$82.193$ equal to the PV of $\$100$ discounted by 5 years; the second is the underwriting fee and dealer profit of. $\$2.357$ ; the third is the. equity kicker worth. $\$15.45$ . The option money is spent on at-the-money calls on. $150\%$ of the principal which cost. $1.5\times\$925.8$ ; the trust also sells an at-the-money put for $\$23.25$ . Thee investor has a 1.5 times leveraged position on the way up and unleveraged downside exposure. The investor's payoff diagram is shown in Figure 8.7..  

![](c64b3209619ff4cd9d50da49435bf70cbb9bed0685ff84ec0a89ca2238cb1775.jpg)  
Figure 8.7 A 5-year 1.5 leveraged principal-at-risk index-linked note  

A common variation on this design is to put a floor under the principal loss. Instead of selling a straight put, the issuing trust sells an at-the-money put, but also buys an out-of-the-money put, say $15\%$ . In an upward-sloping yield curve environment, the $15\%$ out-of-the-money European put can typically be bought cheaply, resulting in little participation loss on the upside.  

The long call-short put position is equivalent to the long forward position. Most commoditytracking ETNs are designed as a combination of a money-market account and a long futures. position. At the time of the issuance, investors pay $\$100$ for the commodity-linked fund. The proceeds are invested in a futures margin account paying a money market interest rate. The fund also takes a long position in the most liquid futures contract with the shortest expiry. Each month or quarter, the ETN is rolled into the new near futures position. The futures gain or loss is added to/subtracted from the account. In this way the ETNs track the performance of the commodity over time. The fund manager's fee is taken out of the interest earned on the margin account. In effect, the ETN is a principal-at-risk floating rate note or a rollover structure where the principal expands or shrinks as the commodity moves up or down. In this design, it is easy to have a short-commodity ETN (sell futures), or a leveraged long and short tracking fund (buy or short futures on twice the principal), since the invested proceeds fully support a margin account, and no money has to be taken out to spend on options.  

Figure 8.8 portrays the idea behind a commodity-tracking ETN assuming the gains or losses on the futures are credited once a quarter. At the start, investors put $\$100$ into the fund. Over the quarter, the money market account earns $4\%$ per annum interest or $\$1$ . The fund manager gets a fee of. $\$0.50$ . The remainder $\$0.50$ pays for fund expenses or is paid out to the investors. Meanwhile the futures position has a gain or loss. If the commodity's return over the quarter. was $10\%$ , the marking to market produces $\$10$ . The fund's net asset value is $\$110$ , and the.  

![](28b15c0ca4da872c2f611163df7b1b656f6ea69858f43354f4a7c245a366a13e.jpg)  
Figure 8.8A commodity-tracking ETN  

process starts again with $\$110$ principal. The funds trade on the stock exchange at a discount or premium to the net asset value as a closed-end fund or ETF.  

Equity index ETNs may offer advantages over ETFs. An ETF takes money in and buys the underlying stocks in the index. As such, an ETF is likely to accumulate at least some tracking error due to the cost of maintaining the index composition by buying/selling individual stocks. In theory, the ETN can avoid that by simply taking a long futures position. Also, ETFs typically pay out dividends as they come, while ETNs may be able to roll over the dividends into an increased principal position, perhaps taxed at a lower capital gains tax rate.  

The main problem with the commodity-tracking ETN design is that tracking the first futures contract is not the same as tracking the spot commodity. This may be especially true for commodities for which the cost-of-carry arbitrage equation does not hold, and these. commodities may often be subject to a contango or backwardation. In a contango, the next futures trades at a price higher than the front futures. As the ETN manager rolls into the next contract, he incurs a cost of selling the expiring futures and buying the next at a higher price, which then drifts down relative to the spot price movements. Since their introduction in 2006, there are several examples of commodity-tracking ETNs posting negative returns despite increasing commodity prices. Regulators, such as FINRA, have written guidelines directing sponsoring institutions to include warnings about the tracking errors associated with futures rollover strategies in the offering materials. Another drawback of an ETN is the credit exposure to the sponsoring bank that backs the money market account..  

The real advantage of the ETN design lies in its flexibility, since the invested funds simply sit in a margin account. The supported futures strategy can be anything and fairly active. Thus ETNs can be designed to track hedge fund strategies like momentum reallocation, long-short or global macro.  

# 8.4INSURANCE RISK STRUCTURED PRODUCTS  

Since the beginning of time, the main ideas behind insurance have been pooling and diversification. Pooling is the idea that, among people buying insurance, some will make claims, many will not. Those who will not in effect subsidize those who will. This works as long as the percentage of claimants is small, which keeps the premiums low for everyone. Diversification comes into play, because insurers cannot hedge the risks of natural or man-made but unpredictable disasters. Selling insurance to a variety of people, and selling a variety of insurance types, sometimes does not reduce risk enough when disasters result in large, concentrated claims. For centuries, insurers have turned to reinsurance markets to share risks. Reinsurance works through syndication. A large concentrated risk is parceled out into smaller prorata pieces and large institutions (reinsurance companies) or wealthy individuals (Lloyd's of London "names"), who normally compete with one another, take unlimited liability risks in the concentrated pool of policies. A "quota-share reinsurance" arrangement involves transferring the risk of a percentage of a "book of business" to a reinsurer.  

The ideas of securitizing insurance risks have floated around since the beginning of the 1990s, with first transactions occurring in the mid-1990s, but it is only in the last decade that the market for the alternative risk transfer (ART), reinsurance sidecars and catastrophe (CAT) bonds has finally arrived. The issuance reached $\$4$ billion in 2006. It stalled as large insurers and reinsurers faced financial headwinds in the 2008 credit crisis. According to the Bermuda-based ARTemis website, the issuance picked up again and topped $\$5$ billion in 2010.  

The design of reinsurance sidecars or CAT bonds follows the path of the loan-backed creditlinked notes. The natural or physical risks to which the CAT bond investor is exposed are often not referenced directly. The bond's exposure is to the payouts on a pool of individual insurance contracts. The contracts' payouts are exposed to the physical risks, but could also be affected by litigation and other factors. Sometimes, the bond's payout is based on modeled rather than actual payouts; and sometimes the bond's payout is linked to the natural disaster directly, via a set of parameters mimicking potential payouts.  

The typical chronology is as follows. An insurer sells hurricane policies to individuals or industrial clients along the Gulf of Mexico. The policy pool becomes large and concentrated in a small geographical area. Instead of turning to a reinsurer, the insurer contacts a special purpose reinsurance trust or company domiciled in the Cayman Islands or Bermuda. The reinsurance vehicle issues the CAT notes to investors. The notes promise to pay a floating interest rate equal to LIBOR plus a very large margin up to $20\%$ . The notes are rated by the rating agencies as junk, perhaps B or $^{\mathrm{B+}}$ . (It is hard to see how S&P or Moody's can evaluate the risks without the help of the insurer...) The proceeds are received by the reinsurance vehicle and can be invested to earn interest; also, the insurer (the cedant) pays into the vehicle company, and for that money the reinsurance company either writes a derivative or a reinsurance contract (often more than one). According to that reinsurance contract, if the disaster covered by the policies takes place, then the trust and the investors lose the principal on the bonds, and the insurer uses the money in the trust to pay the individual policy claims. If the contract is a derivative, then the loss of principal is triggered by prespecified narrowly defined index or event parameters rather than actual claim payouts. Figure 8.9 illustrates a non-derivative structure of a CAT bond. The issuer holds the pool of principal money. If the disaster does not occur, the money is returned to the investor. If the disaster does occur, the money is used to pay the claims on a segregated sub-portfolio of the insurer's policies. The investors in the CAT bonds are hedge funds and specialized catastrophe funds, as well as (life and other) insurers, reinsurers, and pension funds.  

![](033ec06aa8f527a5095c32036f5f21f38143fbbf13b5050d77f6792a637f0343.jpg)  
Figure 8.9 A CAT bond  

In a derivative-based structure of the CAT bond, the loss of principal is triggered by modeled losses or events. The principal lost may then not be equal to the actual payouts with the insurer bearing the basis risk. The typical triggers involve:.  

excess indemnity . total industry loss modeled loss parameter index.  

The excess indemnity simply means a large deductible. The loss of principal is triggered only if the actual claims exceed a certain minimum threshold (e.g. the first. $\$250$ million). Instead of using the insurer's claim losses, one can use total industry losses. The potential for verification or disputes is diminished as the issuing reinsurer can use the services of a large independent data company. For property-casualty claims, one such source may be the. Insurance Service Office, Inc. (ISO)..  

Instead of the actual individual insurer or industry losses, the modeled loss CAT bond involves the use of a catastrophe modeling algorithm based on physical parameters of the actual event (e.g. wind speed). The modeled loss CAT bond allows a faster transfer of the principal money before the claims are paid over time. To minimize the risk of using the wrong. parameters (e.g. gathered over or more heavily weighted by different weather station locations, or time-average speed instead of top speed) that may not correlate well with the actual losses on the geographically spread insured properties, the index-parametric CAT bond uses an index developed by a specialized analytic company. The advantage of the latter is independence and transparency of the index calculating agent.  

Catastrophe modeling has developed as a new field of actuarial science that draws on the. science fields of engineering, seismology and meteorology. The objective is to identify the. many aspects of physical (and human-induced) peril phenomena that can be measured (wind speed change, ground displacement, hail size, etc.), combine them with the data about the insured properties (construction standards, age of structures, building height), and match them to many aspects of the potential damage (roof collapse, HVAC system damage, sprinkler damage). Similar to actuarial science approaches to life insurance, where many factors are. identified that influence conditional life expectancy, the objective is to identify the peril factors and to develop often non-linear deterministic or multivariate probabilistic algorithms that combine them into a predictive model. Similarly on the output side, instead of using the total dollar amount of the loss, the objective is to identify the types of damage that a peril may. cause, model them individually or jointly first, and then combine them into loss estimates by adding the information about the terms of the insurance covering the losses. Besides natural catastrophes (hurricanes, tornados, earthquakes, floods, fire), the modeling can include humanmade ones (terrorism, war, shipping piracy, work accidents, product defects). The advantage. of catastrophe modeling is that the models can produce the entire loss distributions from which one can compute other statistics, e.g. averages over time, maximums, etc. CAT modeling is used by the reinsuring CAT bond issuers, the rating agencies, and the investing funds. The insurance industry works on coordinating the standards for data collection and data sharing..  

# Mortgage-Backed Securities  

Mortgage loans provide financing for residential and commercial real estate. The primary feature of a mortgage is the first lien (mortgage note, encumbrance) right of the lender to foreclose on (liquidate) the property. The lender has the most senior claim in case the borrower defaults. The appetite for mortgage financing around the world is huge. Commercial banks that issue mortgage loans do not have an unlimited amount of capital. In order to replenish the loaned funds, they turn to the mortgage-backed securities (MBS) market.  

In Continental Europe, banks take in deposits and issue unsecured bonds to finance their overall loan activity. They also segregate pools of mortgages on the asset side of the balance sheet and issue covered bonds securitized by these mortgages. In Germany, such a structure is called a Hypothekenpfandbrief. The mortgage loans stay on the balance sheet of the bank; the Pfandbrief is a liability of the bank. Currently the Pfandbrief market is reaching a EUR 1 trillion mark in terms of total outstanding. This form of covered debt refinancing of real estate loans is popular in Germany, but to a lesser extent in Denmark, Spain, and France.  

In the USA most mortgage loans are moved off the balance sheets of the originating banks through the securitization process. Loans are sold in an arm's length transaction to government sponsored agencies (GSEs) or privately-sponsored trusts ("private label' sponsors are banks or Real Estate Investment Trusts, REITs). The GSEs - GNMA, FNMA, FHMC, known by their nicknames Ginnie Mae, Fannie Mae, Freddie Mac, as well as the Federal Home Loan Banks, FHLBs - dominate the market due to their explicit or implicit government guarantee. and the implicit cost of funding subsidy (they are perceived as risk free). Through a variety of securitization programs (e.g. GNMA Platinum or FNMA CL pool prefix) these agencies form pools of purchased mortgages separated into trust vehicles. To be included in the various pools, the mortgages have to be "conforming," i.e. they have to satisfy certain conditions, such as maximum size, loan-to-value ratio, or type of property; otherwise they are placed in special non-conforming pools, such as "jumbo" or "5/1/ Hybrid." FNMA assigns a prefix to each pool's ID number to identify the type of mortgages in the pool. Once the pool of mortgages with similar characteristics is formed, the pool trust issues "pass-through' certificates to investors. These pass-through bonds entitle holders to the proportional share of all cash flows (principal plus interest minus insurance and servicing fees) coming out of the pool. The pass-through certificates can be securitized again into collateralized mortgage obligations (CMOs). The passthroughs are placed into a new trust that issues CMO certificates that are not proportional, but rather divert the interest, principal, and prepayment cash flows unequally among several classes of investors. The primary objective of CMOs is the separation of the total pool cash flow into senior bonds with limited interest and credit risk, mezzanine and junior ("equity") bond classes. subject to a great risk of default, and, even in the absence of default, the risk of the timing of the cash flows. The cash flow timing risk is due to the fact that, in the USA, most residential mortgage loans can be prepaid by the borrower at no penalty. The "prepayment risk" is a form of call risk. Similar to corporate issuers, homeowners often choose to refinance their loans when interest rates decrease. When the homeowner refinances, the old loan is paid off and drops out of the pool. Some prepayments are not interest rate driven, e.g. when homes are sold.  

The MBS market in the USA is gigantic. According to the Securities Industry and Financial Markets Association (SIFMA), as of the end of 2009, there were $\$9.1$ trillion in MBS. bonds outstanding. By comparison, the US Treasury bonds, notes and bills outstanding were $\$7.6$ trillion, the corporate bonds were $\$6.8$ trillion, and the municipals were $\$2.8$ trillion. The. total cap of the US stock market was $\$13.4$ trillion as of December 2010.  

Our discussion proceeds in three stages: the basics of mortgage financing, the prepayment. measurement and risk, and the discussion of the three basic of CMO structures (sequential tranching, planned amortization classes, PACs, and interest-only/principal-only, IO/PO, split). The CMO tranche design is common across many asset-backed securities, including CDOs and CLOs covered in detail in Chapter 10..  
