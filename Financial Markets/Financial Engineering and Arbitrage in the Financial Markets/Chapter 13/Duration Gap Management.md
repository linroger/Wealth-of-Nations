---
tags:
  - asset_liability_management
  - balance_sheet
  - duration_gap
  - interest_rate_risk
  - zions_bank
aliases:
  - Duration Gap
  - Interest Rate Exposure
key_concepts:
  - Asset and liability categories
  - Duration Gap Management
  - Interest rate exposure
  - Neutral net worth position
  - Weighted average duration
---

# 13.3 DURATION GAP MANAGEMENT  

The Duration Gap Management serves a very different purpose of the ISGap analysis. Instead of focusing on the repricing risk of the different asset and liability categories, we attempt to describe the interest rate exposure of the existing asset and liabilities in order to assess the risk to the net worth of the bank. We assign durations to all asset and liability categories and we compute the weighted average duration of all assets and liabilities. The duration analysis is mathematically equivalent to the first-order Taylor expansion. The effect on the net worth is equal to the sum of the asset durations times interest rate changes minus the sum of the liability durations times the interest rate changes.  

The Duration Gap analysis is similar in spirit to the market VaR factorization, but instead of multiple yield curve point exposures, we have one duration number describing each asset. and liability category. Conceptually, by producing a composite duration for the whole asset portfolio and a composite duration for the whole liability portfolio, we are assuming parallel yield curve movements. The advantage is the relative simplicity and yet, at the same time, the completeness of the picture. Each balance sheet category's one duration number has a hedge interpretation. And we have the picture of the overall potential effect of interest rate changes on the bank's equity value.  

Let us apply the Duration Gap Management method to Zions' balance sheet. We should be using the market values (many of which are contained in the bank's 10-Q), but in Table 13.10 we are using the accounting numbers to get the relative weights of the different categories. We are making up the intermediate duration numbers.  

We start by computing the weight $w_{i}^{A}=A_{i}/T A$ of each asset line item in the total assets, and the weight $w_{i}^{L}=L_{i}/T L$ of each liability line item in the total liabilities. We perform a detailed. analysis of each line item to determine the modified duration for that item, not shown here. For example, available-for-sale securities could be further broken down into US Treasuries, agencies, corporates, and municipals. One-to-four family residential real estate loans could be broken down into fixed and adjustable, and fixed further into 15-year and 30-year fixed. Each subcategory would be characterized by its own modified duration. The numbers in our table $\cdot D_{i}^{A}$ for asset categories and $D_{i}^{L}$ for liability categories--are already weighted averages of these subcategories. We compute the weighted modified duration of all the assets and the weighted duration of all the liabilities:  

$$
\begin{array}{l}{{\displaystyle{D_{A}=\sum_{i}w_{i}^{A}\times D_{i}^{A}=2.2254}}}\ {{\displaystyle{D_{L}=\sum_{i}w_{i}^{L}\times D_{i}^{L}=0.6469}}}\end{array}
$$  

The raw Duration Gap is equal to the difference of the durations:  

$$
D G=D_{A}-D_{L}=2.2254-0.6469=1.5785
$$  

From this number, we see that the bank should strive to lengthen the duration of its liabilities. or shorten the duration of its assets in order to achieve the neutral net worth position. In the absence of any repricing, interest rate changes alone will change the equity value of the bank.  

Table 13.10 The duration gap analysis for Zions for September 30, 2010   


<html><body><table><tr><td colspan="6">Durationofassets andliabilities</td></tr><tr><td></td><td>Balance</td><td>Ave</td><td></td><td></td><td>Weight X</td></tr><tr><td>(in millions)</td><td>Sept 30 2010</td><td>% rate</td><td>Weight %</td><td>Duration</td><td>Duration</td></tr><tr><td colspan="6">Assets</td></tr><tr><td>Money market investments</td><td>$5,193</td><td>0.27</td><td>10.03</td><td>0.22</td><td>0.0221</td></tr><tr><td>Securities:</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Held-to-maturity</td><td>843</td><td>4.14</td><td>1.63</td><td>9.62</td><td>0.1568</td></tr><tr><td>Available-for-sale</td><td>3,282</td><td>2.68</td><td>6.34 0.11</td><td>3.87</td><td>0.2454 0.0073</td></tr><tr><td>Trading account</td><td>59</td><td>3.63</td><td></td><td>6.62</td><td></td></tr><tr><td>Total securities</td><td>4,185</td><td>2.99</td><td>8.08</td><td></td><td></td></tr><tr><td>Loans held for sale</td><td>189</td><td>4.67</td><td>0.37</td><td>2.20</td><td>0.0081</td></tr><tr><td>Commercial loans:</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Commercial & industrial</td><td>9,402</td><td></td><td>18.16</td><td>1.10</td><td>0.1998</td></tr><tr><td>Owner occupied & leasing</td><td>8,741</td><td></td><td>16.88</td><td>2.27</td><td>0.3832</td></tr><tr><td>Commercialreal estateloans:</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Construction& land development</td><td>4,206</td><td></td><td>8.12</td><td>0.98</td><td>0.0796</td></tr><tr><td>Term Consumer loans:</td><td>7,535</td><td></td><td>14.55</td><td>2.86</td><td>0.4161</td></tr><tr><td></td><td>2,157</td><td></td><td>4.17</td><td>0.77</td><td>0.0321</td></tr><tr><td>Home equity credit line 1-4 Family residential</td><td></td><td></td><td>6.77</td><td>7.88</td><td>0.5335</td></tr><tr><td></td><td>3,504</td><td></td><td>0.71</td><td></td><td></td></tr><tr><td>Construction& other RE</td><td>366</td><td></td><td></td><td>1.12</td><td>0.0080</td></tr><tr><td>Bankcard, revolving, other</td><td>558</td><td></td><td>1.08 0.11</td><td>0.36</td><td>0.0039</td></tr><tr><td>Foreign loans:</td><td>56</td><td></td><td></td><td>0.26</td><td>0.0003</td></tr><tr><td>Net loans/leases excl. FDIC</td><td>36,525</td><td>5.60</td><td>70.54</td><td></td><td></td></tr><tr><td>FDIC-supported loans</td><td>1,150</td><td>11.93</td><td>2.22</td><td>8.23</td><td>0.1827</td></tr><tr><td>Total loans and leases</td><td>37,675</td><td>5.79</td><td>72.76</td><td></td><td></td></tr><tr><td>Total interest-earning assets</td><td>47,241</td><td>4.93</td><td>91.24</td><td></td><td></td></tr><tr><td>Cash and duefrombanks</td><td>1,063</td><td></td><td>2.05</td><td>0.00</td><td>0.0000</td></tr><tr><td>Allowanceforloanlosses</td><td>(1,556)</td><td></td><td>(3.01)</td><td>1.77</td><td>-0.0533</td></tr><tr><td>Goodwill,core,other</td><td>5,029</td><td></td><td>9.71</td><td>0.00</td><td>0.0000</td></tr><tr><td>Total assets</td><td>$51,778</td><td></td><td>100.00</td><td></td><td>2.2254</td></tr><tr><td>LIABILITIESANDEQUITY Interest-bearing deposits:</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Savings and NOW</td><td>$6,187</td><td>0.32</td><td>13.64</td><td>0.66</td><td>0.0900</td></tr><tr><td>Money market</td><td>15,584</td><td>0.63</td><td>34.36</td><td>0.51</td><td>0.1752</td></tr><tr><td>Time under $100,000</td><td>2,103</td><td>1.25</td><td>4.64</td><td>1.08</td><td>0.0501</td></tr><tr><td>Time $100,000 and over</td><td>2,462</td><td>1.21</td><td>5.43</td><td>0.96</td><td>0.0521</td></tr><tr><td>Foreign</td><td>1,563</td><td>0.6</td><td>3.45</td><td>1.16</td><td>0.0400</td></tr><tr><td>Total interest-bearing deposits</td><td>27,900</td><td>0.66</td><td>61.51</td><td></td><td></td></tr><tr><td>Borrowed funds:</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Securities sold,not yet purchased</td><td>38</td><td>4.33</td><td>0.08</td><td>3.22</td><td>0.0026</td></tr><tr><td>Fed funds and security repos</td><td>874</td><td>0.14</td><td>1.93</td><td>0.18</td><td>0.0035 0.0034</td></tr><tr><td>FHLB advances and other borrow: Long-term debt</td><td>238 1,927</td><td>5.34/4.74 16.45</td><td>0.52 4.25</td><td>0.65 5.34</td><td>0.2270</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Total borrowed funds</td><td>3,068</td><td>10.82</td><td>6.76</td><td></td><td></td></tr><tr><td>Total interest-bearing liabilities</td><td>30,969</td><td>1.67</td><td>68.28</td><td></td><td></td></tr><tr><td>Non-interest-bearing deposits Other liabilities</td><td>13,787</td><td></td><td>30.40</td><td>0.01</td><td>0.0030 0.0000</td></tr><tr><td></td><td>601</td><td></td><td>1.33</td><td>0.00</td><td></td></tr><tr><td>Total liabilities</td><td>$ 45,357</td><td></td><td>100.00</td><td></td><td>0.6469</td></tr><tr><td>Total shareholders’ equity</td><td>6,421</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Total liabilities and equity</td><td>$51,778</td><td></td><td></td><td></td><td></td></tr></table></body></html>  

A rise in the interest rates will reduce the value of the assets disproportionately more that the value of its liabilities.  

Since the objective of the Duration Gap analysis is to provide a meaningful hedge recommendation, and as the dollar assets normally exceed the dollar liabilities, we are often interested in the Leverage-Adjusted Duration Gap:  

$$
L A D G a p=D_{A}-D_{L}\times{\frac{T L}{T A}}=2.2254-0.6469\times{\frac{45,357}{51,778}}=1.6587
$$  

The interpretation of the Leverage-Adjusted Duration Gap is that the duration of the liabilities must change by more than that indicated by the raw gap in order to immunize the net worth of the bank.  

Note the different emphasis of the Duration Gap from the Maturity Gap analysis. While the. bank may not be able to adjust the relative composition of its loan and deposit portfolios and repricing may take time, it may choose to focus on the durations of each category, or focus on financial hedging. Suppose the management of the bank anticipates a. $0.75\%$ average rise in the interest rates over the next year. The effect of that interest rate rise on the bank's net worth would be:  

$$
\begin{array}{r l}&{\Delta E=(-D_{A})\times\Delta r\times T A-(-D_{L})\times\Delta r\times T L}\ &{\Delta E=(-2.2254)\times0.0075\times51,778-(-0.6469)\times0.0075\times45,357}\ &{\Delta E=-864.20+220.06=-9644.14\mathrm{million}}\end{array}
$$  

In the above calculation, we could have assumed different interest rate changes for total assets and total liabilities, or even for the different categories. For a parallel move in the interest rates assets and liabilities, the calculation can be performed more simply using the Leverage-Adjusted Duration Gap:  

$$
\begin{array}{r l}&{\Delta E=(-L A D G a p)\times\Delta r\times T A}\ &{\Delta E=(-1.6587)\times0.0075\times51,778=-\S644.14\mathrm{million}}\end{array}
$$  

Relating this number to the bank's Income Statement, we see that this size change in the equity value represents roughly 2-6 months' worth of net interest income. The risk is thus not. insignificant. The bank would have to generate that much more in income in order to maintain the current equity value. The alternative is financial hedging in the form of shorting long-term securities, shorting bond futures, or paying fixed on long-term swaps. The choice is often dictated by liquidity considerations, cost, and the fit with the income and repricing strategy. If the largest contributors to the gap-the commercial and residential real estate loans can be reduced or their duration shortened relatively quickly, then bond or note futures could be the best choice, if any hedging is to be undertaken. On the deposit side, Eurodollar, LIBOR or. TBill futures could be used to hedge the cost of money market-indexed deposits.  
