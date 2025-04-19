---
tags:
  - interest_rates
  - mbs
  - mortgage_backed_securities
  - pass_through_securities
  - prepayment_risk
aliases:
  - MBS
  - Mortgage Pools
  - Pass-Throughs
key_concepts:
  - Cash flow distribution
  - Duration and convexity
  - Mortgage pool information
  - Prepayment risk
  - Servicing fee
---

# 9.3 MORTGAGE PASS-THROUGH SECURITIES  

When individual mortgages are combined into pools, one generally needs to know the following information about the pool:  

the principal: $P r i n c=\mathbb{\mathbb{S}}300,000,000$ the weighted average coupon: $W A C=6.5\%$ the pass-through rate, or net coupon: $R=6.0\%$ the weighted average maturity: $W A M=349$ months, or the seasoning: $A g e=11$ months the current PSA: $P S A=175$  

The difference between the $W A C$ coming into the pool from the homeowners and the pass-through rate, $R$ is the servicing fee. The WAM and the Age add up to 360 months.  

Once pools are formed and separated into trusts, the sponsoring agency issues trust certificates. These are called pass-through certificates or pass-throughs, because the owners are entitled to the proportional share of all the cash flow coming into the pool net of the servicing, irrespective of whether the cash flow is from interest, scheduled principal payment, or (any type of) prepayment (e.g. due to curtailment, sale of property, refinancing). The pools are usually assembled from mortgages issued within a few months of each other, with similar sizes and interest rates.  

Trading in mortgage pools, and the pass-through certificates on them, has its own quirks. In specified pool trades, we usually know the pool ID, say Fannie Mae CL201107B4, and the original principal balance on the pool, say $\$325,000,000$ In to-be-announced and stipulated trades, the agency and the pass-through rate are known, but the pool IDs are not known by the buyer in advance, but are subject to established rules and value adjustments.  

Once we know the basic statistics of the pool, we can project the pool's cash flows based. on the current PSA estimate. Table 9.2 shows the projected cash flows for a hypothetical CL201107B4 pool. Note two fundamental differences from an individual mortgage behavior. Even when the pool is newly formed, some mortgages may already be a few months old;. some may have prepaid. More importantly, since prepayments are largely the result of entire. mortgages paying off and falling out of the pool due to sale or refinancing, the scheduled cash flow coming into the pool drops every month. The new scheduled cash flow is computed on. the basis of the principal balance outstanding at the beginning of the month. We show that the. WAC interest, the net interest coming out of the pool, is. $0.5\%/12$ lower.  

Table 9.3 shows the same mortgage pool assuming faster prepayments at the rate of 240 PSA. At this rate of prepayment, the total interest paid by the homeowners into the pool drops significantly. The total principal returned is still $\$300$ million, but it is returned more quickly.. By month 102, only $\$75$ million is still owed; previously over. $\$107$ million was still owed..  

The buyer of a pass-through certificate is entitled to the (proportion of the) total cash flow. of the pool: interest, scheduled principal payment, and principal prepayment. To price the. pass-through, the buyer discounts the total cash flow by an interest rate. That discounting is done under some positive PSA assumption, e.g. 200 PSA. What happens if our assumption is wrong? If interest rates don't change, but prepayments speed up (slow down), the cash flow returned will be smaller (greater) but faster (slower). The PV outcome depends on the shape. of the yield curve. Often the question is posed differently, mixing the change in the interest. rate with the likely response of prepayments..  

Assuming a fairly flat yield curve, what happens to the value of a pass-through when interest rates change? This is a duration-convexity question applied to a security that has an option (a call option) to prepay built into it..  

A corporate bullet bond's response to an interest rate change is predictable. The bond. increases (decreases) in value in percentage terms approximately by the amount equal to the modified duration times the decrease (increase) in the interest rates (yield to maturity).. Actually, the bond increases (decreases) in value more (less) than the duration-predicted move when interest rates decrease (increase). In both cases - interest rate increases and decreases -- the holder of the bond undervalues the bond using the duration method (gains more or loses. less). This is known as the positive convexity' of the price-yield relationship. An amortizing. bond not subject to prepayments is less convex than a bullet (interest-only) structure with a 1arge balloon principal at the end, but it is still convex..  

A mortgage pass-through subject to prepayment behaves differently. As interest rates drop, the bond's duration shortens as prepayments speed up making the bond behave like a shortermaturity bond ("contraction risk"). The drop in the interest rates increases the PV of each individual cash flow ceteris paribus, but the total cash flows decrease. The net effect is that the bond's value goes up less than predicted by the modified duration.  

<html><body><table><tr><td>298,639,486.52 EndPrinc</td><td>297,192,638.44 295,660,427.46 294,043,902.83 292,344,190.30 290,562,490.88</td><td>109,574,270.36 108,358,834.00 107,155,376.18 29,930,142.75</td><td>29,516,873.53 29,107,935.76 245,083.75</td><td>162,322.57 80,631.66 一</td></tr><tr><td>PrepayPrinc</td><td>1,069,734.18 1,155,537.21 ,240,456.57 1,324,415.43 ,407,337.97 1,489,149.50</td><td>1,017,633.47 1,006,345.53 995,168.82 277,965.94 2</td><td>274,127.84 270,329.98 2,276.13</td><td>1,507.52 748.84</td></tr><tr><td>SMM</td><td>0.3569 0.3873 0.4178 0.4484 0.4791 0.5099</td><td>0.9202 0.9202 0.9202</td><td>0.9202 0.9202 0.9202 0.9202</td><td>0.9202 0.9202 0.9202</td></tr><tr><td>SchedEndPrinc</td><td>299,709,220.70 298,348,175.64 296,900,884.02 295,368,318.26 293,751,528.28 292,051,640.38</td><td>110,591,903.83 109,365,179.52 108,150,545.00 30,208,108.70</td><td>29,791,001.37 29,378,265.74 247,359.88</td><td>163,830.08 81,380.50</td></tr><tr><td>Princ.</td><td>290,779.30 291,310.87 291,754.41 292,109.19 292,374.55 292,549.92</td><td>209,895.76 209,090.84 208,289.00 139,677.03 2</td><td>139,141.38 138,607.79 81,566.46</td><td>81,253.66 80,942.07 80,631.66</td></tr><tr><td>Pass int</td><td>2 ,500,000.00 ,493,197.43 ,485,963.19 ,478,302.14 ,470,219.51 ,461,720.95</td><td>554,009.00 547,871.35 541,794.17 151,738.93</td><td>149,650.71 147,584.37 1,644.63</td><td>1,225.42 811.61 403.16</td></tr><tr><td>WAC int</td><td>,625,000.00 1,617,630.55 1,609,793.46 ,601,493.98 ,592,737.81 1,583,531.03</td><td>600,176.41 593,527.30 586,943.68</td><td>164,383.84 162,121.61 159,883.06 1,781.68</td><td>1,327.54 879.25 436.75</td></tr><tr><td>Pmt</td><td>$1,915,779.30 1,908,941.42 1,901,547.87 1,893,603.18 1,885,112.36 1,876,080.95</td><td>810,072.17 802,618.13 795,232.68</td><td>304,060.86 301,262.99 298,490.86 83,348.14</td><td>82,581.20 81,821.31 81,068.42</td></tr><tr><td>Beg princ</td><td>300,000,000.00 298,639,486.52 297,192,638.44 295,660,427.46 294,043,902.83 292,344,190.30</td><td>110,801,799.59 109,574,270.36 108,358,834.00 30,347,785.72</td><td>29,930,142.75 29,516,873.53 328,926.34</td><td>245,083.75 162,322.57 80,631.66</td></tr><tr><td>Month</td><td>2 3 4 5 6</td><td>0 1 10 . 00</td><td>00 346 347</td><td></td></tr></table></body></html>  

<html><body><table><tr><td>298,231,178.17 EndPrinc</td><td>296,344,815.54 294,342,622.52 292,226,454.90 289,998,311.18 287,660,329.77</td><td>77,337,122.48 76,195,847.78 75,070,361.71 14,251,797.82 14,002,925.54</td><td>13,757,749.38 69,395.91 45,791.60 22,662.10 295.55</td></tr><tr><td>Prepay princ</td><td>1,478,042.53 1,595,450.05 1,711,270.91 1,825,360.41 1,937,576.29 2,047,779.02 1,008,582.95</td><td>993,699.15 979,021.25 185,863.14 182,617.50</td><td>179,420.06 905.02 597.19</td></tr><tr><td>SMM</td><td>0.4932 0.5355 0.5780 0.6208 0.6637 0.7068 1.2873</td><td>1.2873 1.2873 1.2873 1.2873</td><td>1.2873 1.2873 1.2873 1.2873</td></tr><tr><td>Sched end princ 299,709,220.70</td><td>297,940,265.59 296,053,893.43 294,051,815.31 291,935,887.47 289,708,108.79 78,345,705.43 2</td><td>77,189,546.93 76,049,382.96 14,437,660.95 14,185,543.04</td><td>13,937,169.44 70,300.93 46,388.79 22,957.64 22,662.10</td></tr><tr><td>290,779.30 Princ</td><td>290,912.58 290,922.10 290,807.22 290,567.42 290,202.39 148,694.71 2 2</td><td>147,575.55 146,464.82 66,757.23 66,254.77</td><td>65,756.10 23,181.60 23,007.12 22,833.96</td></tr><tr><td>,500,000.00 1,491,155.89 Pass int</td><td>1,481,724.08 1,471,713.11 1,461,132.27 1,449,991.56 392,472.00</td><td>386,685.61 380,979.24 72,522.09 71,258.99 70,014.63</td><td>467.41 346.98 228.96 113.31</td></tr><tr><td>1,625,000.00 1,615,418.88 WAC int</td><td>1,605,201.08 ,594,355.87 ,582,893.30 1,570,824.19 425,178.00 418,909.41</td><td>412,727.51 78,565.60 77,197.24</td><td>75,849.18 506.36 375.89 248.04 122.75</td></tr><tr><td>$1,915,779.30 1,906,331.47 Pmt</td><td>1,896,123.19 1,885,163.09 1,873,460.72 1,861,026.58 573,872.71 566,484.97</td><td>559,192.33 145,322.82 143,452.01 141,605.28</td><td>23,687.96 23,383.02 23,082.00 22,784.85</td></tr><tr><td>300,000,000.00 298,231,178.17 Beg princ</td><td>296,344,815.54 294,342,622.52 292,226,454.90 289,998,311.18 78,494,400.14 77,337,122.48</td><td>76,195,847.78 14,504,418.18 14,251,797.82 14,002,925.54</td><td>93,482.53 69,395.91 45,791.60 22,662.10</td></tr><tr><td>Month 2 3</td><td>4 5 6 100 1 10</td><td>00 00 00</td><td>346 347 349</td></tr></table></body></html>  

![](2e4dd241e6332fe0ab91e77d3a8c3f68a9f7c9a037e728a48b7fe30e7af4bd90.jpg)  
Figure 9.2 The negative convexity of a mortgage pass-through  

As interest rates increase, the bond's duration lengthens as prepayments slow down, making the bond behave like a longer-maturity bond ("extension risk"). As interest rates increase, we lose the present value due to discounting alone. We also lose the present value because the actual cash flows will occur later.  

This phenomenon of underperformance relative to the straight-line duration response is known as the "negative convexity" of mortgage bonds (the same holds for corporate callable bonds). Often, instead of, or in addition to, the duration and stated maturity of the mortgage bond, one needs to know the weighted average life (WAL) of the pass-through. The WAL is computed as the principal-weighted time average given the PSA assumption. What is really helpful is the schedule of WALs given different PSA assumptions.  

Figure 9.2 shows the intuitive meaning of negative convexity. The dashed straight tangent line is the trajectory of the present value (price) using the duration approximation. The convex. line above is the price-yield function of an amortizing bond assuming no change in prepayments from the current level. The more convex line above that is the price-yield function of a straight bullet bond. The concave line below the straight dashed duration approximation line is the price-yield function of an amortizing (pass-through) bond subject to prepayment (call) risk. The distance between the actual and the duration-projected price line is the convexity. It is positive in up and down scenarios for a bullet/amortizing bond with no prepayments.. It is negative in up and down scenarios for a mortgage pass-through. In our illustration, the duration is the same for both bonds. The tangent line is downward-sloping, reflecting the negative price-yield relationship.  

Let us also illustrate the negative convexity numerically. We discount the projected cash flows of the mortgage pass-through in Table 9.3 at 240 PSA using the yield to maturity of $6.0\%$ monthly. The total dollar amount is $\$300$ million. We blip the yield up and down by 1 bp to estimate the PVBP and the modified duration of the pass-through to be  

$$
M o d D=-\frac{299,861,602.97-300,138,512.88}{300,000,000\times(0.0601-0.0599)}=4.615
$$  

If the yield to maturity moves down to $5.5\%$ , and the prepayments stay at the same 240 PSA speed, then the PV of the cash flows will be $\$307,070,471$ The duration-predicted new price will be:  

$$
^{\mathrm{~\tiny~5~}}=300,000,000\times(1-M o d{\cal D}\times\Delta y)=300,000,000(1+4.615\times0.005)=306,922
$$  

However, if, at the same time as the yield drops from $6\%$ to $5.5\%$ , the prepayment speed increases from $240~\mathrm{PSA}$ to $300\mathrm{PSA}$ , then the price of the pass-through (the PV of its cash flows) will increase only to $\$306,101,402$ (we rerun the cash flow projections and discount the total flow by. $5.5\%/12$  
