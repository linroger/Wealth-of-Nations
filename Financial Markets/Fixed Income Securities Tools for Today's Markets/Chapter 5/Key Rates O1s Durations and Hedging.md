---
tags:
  - asset_liability_management
  - bond_hedging
  - duration
  - dv01
  - key_rates
aliases:
  - Duration
  - Dv01
  - Hedging
  - Key Rate
key_concepts:
  - Asset liability management
  - Key rate Dv01s
  - Key rate durations
  - Par bond key rate
  - Pension liabilities hedging
---

# 5.4 KEY RATES: 'O1S, DURATIONS, AND HEDGING  

Unlike their one-factor equivalents in Chapter 4, key-rate Dv01s and dura-. tions are based on change in price, or percentage change in price, for a change. in a single key rate. Mathematically, the DV01 and duration with respect to key rate $k$ are defined as,  

$$
\begin{array}{c}{{D V01^{k}=-\displaystyle\frac{1}{10,000}\displaystyle\frac{\partial P}{\partial y^{k}}}}\ {{D^{k}=-\displaystyle\frac{1}{P}\displaystyle\frac{\partial P}{\partial y^{k}}}}\end{array}
$$  

where $\partial P/\partial y^{k}$ denotes the partial derivative of price with respect to that one key rate. For example, the price of the JNJ 2.10s of 09/1/2040 is 91.2209, at which price its spread to the HQM par-rate curve is $-0.514\%$ . After a 20-year key-rate increase of one basis point, the price of the bond -- at the. same spread -- falls to 91.0790. Therefore, the bond's 20-year key-rate $\mathbf{\nabla}^{\circ}01$ is,  

$$
D V01^{20}=-\frac{1}{10,000}\frac{91.0790-91.2209}{0.01\%}=0.1419
$$  

and its 20-year key-rate duration is,  

$$
D^{20}=-{\frac{1}{91.2209}}{\frac{91.0790-91.2209}{0.01\%}}=15.56
$$  

TABLE 5.2 Key-Rate DV01s and Hedging of the Pension Liabilities in Figure 4.10 with Par Bonds as of Mid-May 2021.   


<html><body><table><tr><td></td><td>Pension Liabilities ($)</td><td>2.560s of 05/15 2031</td><td>3.215s of 05/15 2041</td><td>3.309s of 05/15 2051</td><td>3.365s of 05/15 2061</td></tr><tr><td>PV/Price</td><td>139,786,479</td><td>100</td><td>100</td><td>100</td><td>100</td></tr><tr><td>10yr Shift</td><td>33,192</td><td>0.09125</td><td>0</td><td>0</td><td>0</td></tr><tr><td>20yr Shift</td><td>52,969</td><td>0</td><td>0.15282</td><td>0</td><td>0</td></tr><tr><td>30yr Shift</td><td>57,786</td><td>0</td><td>0</td><td>0.19508</td><td>0</td></tr><tr><td>40yr Shift</td><td>88,766</td><td>0</td><td>0</td><td>0</td><td>0.22437</td></tr><tr><td>Total</td><td>232,713</td><td>0.09125</td><td>0.15282</td><td>0.19508</td><td>0.22437</td></tr><tr><td colspan="2">Hedge Face Amount ($millions)</td><td>36.375</td><td>34.661</td><td>29.622</td><td>39.562</td></tr></table></body></html>  

Table 5.2 takes a preliminary step in using key rates for asset - liability management in the context of the pension fund introduced in Section 4.8. The first column gives the key-rate Dv01s of the pension liabilities in Figure 4.10. The total present value of the pension liabilities is about $\$140$ million, and the Dv01 of those liabilities is $\$232,713$ . The key-rate DV01s decompose that total DV01 into exposures to the four key rates. A 10-year shift of minus one basis point increases the present value of the liabilities by $\$33,452$ ; a 20-year shift of minus one basis point increases value by $\$52,969$ ; and so forth. The exposure to the 10-year shift is relatively low because, as evident from Figure 4.10, the liabilities build up gradually over the first 10 years and because the values of cash flows of relatively near terms have relatively low interest rate sensitivities. The exposure to the 40-year key-rate shift is relatively high because, unlike the other shifts, it affects 30 years of cash flows - from 30 to 60 years out - and because the values of those distant cash flows have relatively high interest rate sensitivities.  

For expositional purposes, four fictional bonds are created for the rest. of the table. (After these results are discussed, the analysis returns to the JNJ. bonds.) The maturities of these fictional bonds are chosen to match the terms. of the key rates exactly, that is, 10, 20, 30, and 40 years, and their coupons. are chosen so that their prices are all par under the HQM par-rate curve in May 2021.  

Given the careful selection of these bonds, each has exposure only to.   
the key rate corresponding to its maturity. The 2.560s of 05/15/2031, for   
example, as of May 15, 2021, are exactly 10-year par bonds. Their price.   
changes only if the 10-year par rate changes. But, by construction, the.   
20-year, 30-year, and 40-year shifts do not change the 10-year par rate..  

Therefore, the 2.560s have exposure only to the 10-year shift, and that exposure also equals the bond's total exposure. With the same logic applying to the other three bonds, key-rate $^{\circ_{1s}}$ are nonzero only when the term of the key rate equals the maturity of the bond.  

Because each of the bonds has such a simple key-rate. $^{\ '}01$ profile, computing the key-rate hedge of the pension liabilities is correspondingly simple. The objective of the hedge is to purchase an asset portfolio that offsets the key-rate exposures of the liabilities. More specifically, the asset portfolio must have a DV01 exposure to the 10-year shift of $\$33,456$ ; to the 20-year shift of $\$52,969$ ; etc. But because the only bond that has any exposure to. the 10-year shift is the 2.560s of 05/15/2031, the full exposure to that shift has to come from that bond. Mathematically, denoting the face amount of the 10-year bond by. $F^{10}$  

$$
F^{10}\times\frac{0.09125}{100}=\$33,192
$$  

Solving, $F^{10}$ is about $\$36.375$ million, which is listed in the bottom row of Table 5.2. Proceeding analogously to hedge the next three key-rate exposures, the equations are,  

$$
\begin{array}{l c r}{{F^{20}\times{\displaystyle\frac{0.15282}{100}}=\S52{,}969}}\ {{{}}}\ {{F^{30}\times{\displaystyle\frac{0.19508}{100}}=\S57{,}786}}\ {{{}}}\ {{F^{40}\times{\displaystyle\frac{0.22437}{100}}=\S88{,}766}}\end{array}
$$  

Each of these equations can be solved on its own to find the hedge face amounts recorded in the table..  

To summarize, because the hedging bonds are par bonds with matu-. rities equal to the terms of the key rates, key-rate hedges can essentially be read off the table. The pension fund must purchase. $\$33,452$ in DV01 from 10-year par bonds; $\$52,969$ in DV01 from 20-year par bonds; and so forth. In this way, the pension fund will be hedged against any combina-. tion of key-rate shifts. The four key rates do not need to move according. to any model or predetermined pattern. The 10-year key rate might move by $+8$ basis points, the 20-year by $+2$ basis points, the 30-year by 0 basis points, and the 40-year by $^{-2}$ basis points (i.e., something like the May 16,. 2021, shift in Figure 5.1), and the hedge should perform relatively well. The. caveat, of course, is that the performance can be eroded to the extent that rates between the key rates change in a way markedly different from the. shapes of the shifts in Figure 5.2. This caveat, however, is more of an issue in this simplified example, with only four key rates over a maturity range of.  

TABLE 5.3 Key-Rate DV01s and Hedging of the Pension Liabilities in Figure 4.10 with Johnson & Johnson Bonds. Indicative Prices Are as of Mid-May 2021.   


<html><body><table><tr><td></td><td>Pension Liabilities ($)</td><td>1.30s of 09/01 2030</td><td>2.10s of 09/01 2040</td><td>2.25s of 09/01 2050</td><td>2.45s of 09/01 2060</td></tr><tr><td>PV/ Price</td><td>139,786,479</td><td>95.357</td><td>91.221</td><td>88.154</td><td>88.157</td></tr><tr><td>HQM Sprd (bps)</td><td>0</td><td>-56.4</td><td>-51.4</td><td>-45.4</td><td>-39.2</td></tr><tr><td>10yr Shift</td><td>33,192</td><td>0.08577</td><td>0.00597</td><td>-0.00393</td><td>-0.00250</td></tr><tr><td>20yr Shift</td><td>52,969</td><td>0</td><td>0.14191</td><td>0.00707</td><td>-0.00473</td></tr><tr><td>30yr Shift 40yr Shift</td><td>57,786</td><td>0 0</td><td>0 0</td><td>0.18494 0</td><td>0.00871 0.21548</td></tr><tr><td></td><td>88,766</td><td></td><td></td><td></td><td></td></tr><tr><td>Total</td><td>232,713</td><td>0.08577</td><td>0.14788</td><td>0.18808</td><td>0.21695</td></tr><tr><td colspan="2">Hedge Face Amount ($millions)</td><td>38.647</td><td>37.239</td><td>29.306</td><td>41.195</td></tr></table></body></html>  

60 years, than it is in practice, for example, with the eight or nine key rates over a maturity range of 30 years used by the JPM Government Bond Fund and the Bloomberg-Barclays US Government Bond Index in Table 5.1.  

With the basics of key-rate hedging understood, the fictional par bonds created for Table 5.2 are replaced by the approximately 10-year, 20-year, 30-year, and 40-year JNJ bonds listed in Table 4.6. The updated analysis is. presented in Table 5.3. The row "HQM Sprd" gives the spread of each of the JNJ bonds to the HQM par-rate curve as of mid-May 2021. These spreads. are all negative, because, with its triple-A rating, JNJ bonds sell at lower rates than HQM par-rates, which represent double- and single-A credits. In. any case, the bond spreads in the table are kept constant as key-rate shifts are applied. No spread is attached to the pension fund liabilities, because, by assumption, their present value is computed directly from the HQM par-rate curve.  

A major difference between Table 5.2, which features fictional, par. bonds, and Table 5.3, which features the JNJ bonds, is that the key-rate DV01 profile of the JNJ bonds is more complex. As of mid-May 2021, the 1.30s of 09/1/2030 mature in less than 10 years, which means that only the 10-year key-rate shift affects their valuation. Their key-rate profile, therefore, is completely concentrated in the risk of a 10-year shift. The other bonds, however, which do not mature in exactly 20-, 30-, and 40-years and which are not priced at par, have small positive or negative exposures to. key rates other than those corresponding most closely to their maturities.  

Because the bulk of each bond's exposure is still at the key rate closest. to its maturity, the hedging problem in Table 5.3 is not conceptually differ-. ent from the earlier table. Solving for the hedging portfolio is more tedious, however, because no key-rate exposure of the liability can be handled in isolation. All of the bonds have exposures to the 10-year shift; three have exposures to the 20-year shift; and so forth. Consequently, the following equations (with key-rate $^{\circ_{1s}}$ rounded for readability) need to be solved together,  

$$
\begin{array}{r l r}&{}&{F^{10}\displaystyle\frac{0.086}{100}+F^{20}\displaystyle\frac{0.006}{100}+F^{30}\displaystyle\frac{-0.004}{100}+F^{40}\displaystyle\frac{-0.003}{100}=\mathfrak{S}33,192}\ &{}&{F^{20}\displaystyle\frac{0.142}{100}+F^{30}\displaystyle\frac{0.007}{100}+F^{40}\displaystyle\frac{-0.005}{100}=\mathfrak{S}52,969}\ &{}&{F^{30}\displaystyle\frac{0.185}{100}+F^{40}\displaystyle\frac{0.009}{100}=\mathfrak{S}57,786}\ &{}&{F^{40}\displaystyle\frac{0.215}{100}=\mathfrak{S}88,766}\end{array}
$$  

Equation (5.9) says that the combined 10-year key-rate $^{\ '}01$ of the asset portfolio must offset the 10-year key-rate $^{\ '}01$ of the liabilities. Equation (5.10) says the same for the 20-year key rate; Equation (5.11) for the 30-year key rate; and Equation (5.12) for the 40-year key rate. The solution, given in the bottom row of Table 5.3, is not the same as that in Table 5.3 but is certainly of the same order of magnitude.  
