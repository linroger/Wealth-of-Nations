---
tags:
  - forward_bucket
  - interest_rate_risk
  - key_rate
  - municipal_bonds
  - term_structure
  - yield_curve
aliases:
  - Forward Bucket
  - Forward-Bucket
  - Wellesley Bonds
key_concepts:
  - Forward bucket interpretation
  - Forward rate curve
  - Key rate vs forward bucket
  - Term structure shifts
  - Wellesley general obligation bonds
---

# 5.6 FORWARD-BUCKET'O1S  

Key-rate and partial $^{\ '}01s$ are particularly convenient in that they translate directly into hedging with liquid instruments, whether on-the-run or near on-the-run Treasuries or swaps of the most liquid terms. But the shifts themselves are not very intuitive. Shifting the 10-year par rate by a basis point does not mean that the 10-year segment of the term structure shifts, while all other segments stay constant: shifting the 10-year par rate has implications for discounting all cash flows out to 10 years. Furthermore, as mentioned earlier, shifting one par rate, while holding all other rates constant, can imply odd shifts in spot or forward rates. Forward-bucket $^{\bullet}O1s$ , by contrast, are more easily interpretable in terms of changes in the shape of the term structure. They do not, however, provide the same direct visibility into hedging with liquid instruments as do key-rate and partial $^{\ '}01s$  

This section illustrates the use of forward-bucket $^{\circ_{1s}}$ with reference to the general obligation bonds of the Town of Wellesley, Massachusetts, issued in May 2020.4 Table 5.4 lists the first nine bond series sold at that time. Note that, for the tax reasons explained in Section O.2, it is common for municipalities to issue bonds with a coupon of $5\%$ even though market yields are much lower.  

Using the yields in Table 5.4, the analytical tools of Part One can be. used to calculate a term structure of forward rates, which is graphed in. Figure 5.4.5 The idea behind forward-bucket. $^{\ '}01s$ is to shift "buckets," that. is, individual segments of the forward term structure, directly. For purposes. of exposition, this section breaks the term structure into three segments: one to two years; three to five years; and six to nine years. Figure 5.4 shows, for example, a $+10$ -basis-point shift of the three- to five-year segment. In. practice, practitioners choose buckets most suitable to their businesses. A money-market desk, for example, which trades very heavily in short-term instruments, might have many buckets in the short end of the curve and few further on. A swaps desk, on the other hand, which trades evenly across maturities from one to 30 years, might not have nearly as many buckets in the short end but many more evenly spaced buckets across the rest of the curve.  

IABLE 5.4  Selected General Obligation Refunding Bonds Issued by the Town of Wellesley, Massachusetts, in May 2020. Coupons and Yields Are in Percent.   


<html><body><table><tr><td>Maturity</td><td>Principal</td><td>Coupon</td><td>Yield</td></tr><tr><td>06/01/2021</td><td>1,175,000</td><td>5.00</td><td>0.75</td></tr><tr><td>06/01/2022</td><td>1,205,000</td><td>5.00</td><td>0.80</td></tr><tr><td>06/01/2023</td><td>1,210,000</td><td>5.00</td><td>0.84</td></tr><tr><td>06/01/2024</td><td>1,225,000</td><td>5.00</td><td>0.90</td></tr><tr><td>06/01/2025</td><td>1,235,000</td><td>5.00</td><td>0.96</td></tr><tr><td>06/01/2026</td><td>1,250,000</td><td>5.00</td><td>1.01</td></tr><tr><td>06/01/2027</td><td>1,255,000</td><td>5.00</td><td>1.06</td></tr><tr><td>06/01/2028</td><td>1,265,000</td><td>5.00</td><td>1.11</td></tr><tr><td>06/01/2029</td><td>1,270,000</td><td>5.00</td><td>1.18</td></tr></table></body></html>  

![](3361ff7b7b656b43daba2f71940d33ee7e3200bb80a978577454a3842f67e412.jpg)  
FIGurE 5.4  Town of Wellesley General Obligation Forward Rate Curve with a 10-Basis-Point Shift of the Three- to Five-Year Forward Bucket, as of June 1, 2020.  

Forward-bucket $^{\ '}01s$ are computed analogously to any other inter-. est rate risk metric: price the bond or portfolio with the current term structure; shift a forward-bucket by one basis point; reprice the bond or.  

TABLE 5.5 Forward-Bucket Exposures and Hedging of Selected Town of Wellesley General Obligation Refunding Bonds, as of June 1, 2020. The 5s of 06/01/2029 are Hedged with the 1.205s of 06/01/2029.   


<html><body><table><tr><td>(1)</td><td>(2)</td><td>(3)</td><td>(4)</td><td>(5)</td><td>(6) Hedged</td></tr><tr><td></td><td>5s of</td><td>5s of</td><td>5s of</td><td>1.205s of</td><td>5s of</td></tr><tr><td></td><td>06/01 2022</td><td>06/01 2025</td><td>06/01 2029</td><td>06/01 2029</td><td>06/01 2029</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1-2yr Shift</td><td>0.02099</td><td>0.02324</td><td>0.02578</td><td>0.01972</td><td>0.00239</td></tr><tr><td>3-5yr Shift</td><td>0</td><td>0.03112</td><td>0.03492</td><td>0.02862</td><td>0.00098</td></tr><tr><td>6-9yr Shift</td><td>0</td><td>0</td><td>0.03983</td><td>0.03642</td><td>-0.00337</td></tr><tr><td>Total</td><td>0.02099</td><td>0.05437</td><td>0.10053</td><td>0.08475</td><td>0</td></tr></table></body></html>  

portfolio with the new term structure; and subtract one price from another,. observing the usual sign convention. Table 5.5 reports forward-bucket $^{\ '}01$ profiles computed along these lines. The second to fourth columns give the forward-bucket $^{\ '}01s$ for three of the Wellesley bonds, a two-year bond, a five-year bond, and a nine-year bond, all as of June 1, 2020. For expositional purposes, the fifth column gives the forward-bucket. $^{\ '}01s$ of a fictional nine-year par bond, discounted with the same curve. The final row of the table sums all the forward-bucket. $^{\circ_{1s}}$ , which gives the increase in. price after shifting all forward rates down by one basis point. Hence, the forward-bucket $^{\ '}01s$ in the table decompose these totals into exposures to. individual segments of the term structure..  

The two-year bond, which has no cash flows past two years, has no exposure to the three- to five-year and the six- to nine-year forward-bucket shifts. Similarly, the five-year bond has no exposure to the six- to nine-year shift. As intended, forward-bucket $^{\ '}01s$ clearly convey exposures to individual segments of the term structure. For example, if forward rates in the threeto five-year segment of the curve fall by one basis point, the price of the 5s of 06/1/2029 increases by 3.5 cents per 100 face amount.  

The usefulness of forward-bucket $^{\ '}01s$ to assess curve risk is illustrated in the sixth column of Table 5.5. Say that a market maker hedged the 5s of. 06/01/2029 with the hypothetically liquid, fictional 1.205s of 06/01/2029 using the parallel shift, that is, the total. $^{\circ_{1s}}$ in the last row of the table. Against a purchase of 100 face amount of the 5s of 06/01/2029, the market maker would sell $100\times0.10053/0.08475=118.62$ of the 1.205s. By definition, the total $^{\ '}01$ of this hedged portfolio is zero, but it does have curve. risk, which is computed in the last column of the table..  

The exposure of the hedged portfolio to each forward bucket is the sum of the exposures of the two bond positions. For the one- to two-year forward bucket, for example, the portfolio exposure is,  

$$
100{\frac{0.02578}{100}}-118.62{\frac{0.01972}{100}}=0.00239
$$  

The other two bucket exposures are computed similarly. Taken as a whole,. the forward-bucket $^{\ '}01$ profile of the hedged portfolio, with the first two. exposures positive and the third negative, shows that the market maker's position loses money if the forward curve flattens. For example, in a particular flattening scenario, if one- to five-year forward rates increase, while six- to nine-year forward rates decrease, the position will lose money due to each of the three forward rate shifts. With curve risk quantified in this way,. the market maker can choose between hedging out all curve risk, at some cost, or bearing the risk until the position can be unwound..  

Hedging a bond or portfolio with forward-bucket $^{\ '}01s$ follows along the. same lines as hedging with key-rate. $^{\circ_{1s}}$ If there are five forward buckets, for. example, then five hedging instruments are required. The five unknowns are the face amount of the five hedging instruments, and each of five equations sets the net $^{\ '}01$ of its corresponding forward bucket to zero. While this procedure is perfectly straightforward, an approximate solution is not as immediately apparent as in the case of key-rate $^{\ '}01s$ . Inspection of the sixth. column of Table 5.5 does not reveal the approximate position of a bond or portfolio of bonds that hedges out the residual curve risk. By contrast, inspection of the dollar key-rate Dv01s in the second column of Table 5.3 readily reveals the approximate trades required in the hedging bonds.  
