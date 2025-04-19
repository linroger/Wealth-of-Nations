---
tags:
  - accrued_interest
  - bond_valuation
  - coupon_bonds
  - day_count_conventions
  - intra_year_compounding
aliases:
  - Accrued Interest
  - Day-Count
  - Intra-Year Compounding
key_concepts:
  - Accrued interest calculation
  - Coupon bond example
  - Day-count conventions
  - Intra-year compounding
  - Semi-annual bond yield
---

# 2.2 INTRA-YEAR COMPOUNDING AND DAY-COUNT  

In the real world, the coupons do not accrue and interest rates do not compound over nice.   
annual periods. We tackle things one-by-one. First, we modify our calculations to allow for.   
semi-annual, quarterly, and monthly accrual and compounding periods. Second, we complicate.   
our calculations with different day-counting conventions that exist in different bond markets.   
Last, we tackle the issue of accrued interest which is paid anytime the bond is bought between.   
coupons, i.e. almost always.  

# 2.2.1 Intra-Year Compounding  

Interest rates are always stated on the per year basis, but interest does not have to compound annually. Suppose, for example, that a zero-coupon interest rate is stated as. $5\%$ compounded quarterly. The. $5\%$ does not mean that the borrower pays. $5\%$ of the outstanding principal in interest each quarter. The. $5\%$ rate is per annum, hence we have to divide it by 4 to get the real. interest rate per quarter, which is. $1.25\%$ . Figure 2.7 shows what Jack will receive at maturity if. he lends $\$1,000$ to ABC Company for 12 months on a zero-coupon basis (i.e. no intermediate interest receipts, all interest paid at the end, like on a bank CD) at. $5\%$ compounded quarterly.  

$$
1,000\times\left(1+{\frac{0.05}{4}}\right)\times\left(1+{\frac{0.05}{4}}\right)\times\left(1+{\frac{0.05}{4}}\right)\times\left(1+{\frac{0.05}{4}}\right)=1,050.95
$$  

At the end of 12 months, Jack will receive his. $\$1,000$ back and $\$50.95$ in interest. A $5.095\%$ annually compounded interest rate is economically equivalent to a $5.00\%$ quarterly compounded interest rate. In US consumer finance and retail banking, the $5.095\%$ annual rate is often referred to as APY or annual percentage yield. $(\%\mathrm{APY})$ , while the $5.00\%$ quarterly rate is referred to as APR or the annual percentage rate ( $\%$ APR), with annual (a) or quarterly.  

![](1b095f3f41c3e948b8a0905cf4e6db3862b3adea2c4021d6aa66ab55a0d3d649.jpg)  
Figure 2.7A $5\%$ quarterly compounded rate over 1 year  

(q) added after the rate. The two interest rates ( $\%{\mathbf a}$ and $\%{\bf q}$ ) are just different measuring units for interest in the way that miles (m) and kilometers (km) are used for distance. In general, the conversion formula for any non-annual compounded rate into annual is:.  

$$
1+r_{a}=\left(1+\frac{r_{m}}{m}\right)^{m}
$$  

where $r_{a}$ is the annual equivalent rate and $r_{m}$ is the rate compounded $m$ times per year. Since many bonds in the world pay interest semi-annually, it is common to actually convert non-semi-annual rates to semi-annual using the relationship:  

$$
\left(1+\frac{r_{s}}{2}\right)^{2}=\left(1+\frac{r_{m}}{m}\right)^{m}
$$  

The relationship reflects the property that if the two rates are to be economically equivalent,. interest earned on $\$1$ invested must be identical over the same total interest period; in the. equation, that total period is 1 year. The semi-annual rate is usually referred to as the semiannual bond equivalent yield and is often added in financial tables as the last column under the heading yield. It allows for a quick comparison of relative value between different financial instruments.  

In addition to interest rates (yields) being stated in different compounding forms, bond coupon interest is often paid more than once a year. Just like interest rates, coupon rates are stated on a per annum basis with the word quarterly or semi-annually (. $\overset{\cdot}{g}$ Or $s$ ) added afterward to warn that the stated rate needs to be decompounded to arrive at the real coupon interest. amount.  

Let us revisit our coupon bond example in Figures 2.3 and 2.4. Suppose that now Jack buys a 4-year. $\$1,000$ face value $6\%$ semi-annual coupon issued by ABC. The bond yields. $5\%$ semi-annually. That is, the coupon interest is. $3\%$ or $\$30$ every 6 months, and Jack earns interest at a rate of. $2.5\%$ per 6 months. Figure 2.8 illustrates the semi-annual bond using the sum-of-the-parts valuation method.  

$$
\begin{array}{l}{{\displaystyle{\vphantom{\displaystyle{\frac{1}{\left(1+\frac{03}{2}}\right)}}^{s_{0}}=\frac{530}{\left(1+\frac{0.05}{2}\right)}+\frac{530}{\left(1+\frac{0.05}{2}\right)^{2}}+\frac{530}{\left(1+\frac{0.05}{2}\right)^{3}}+\frac{\S30}{\left(1+\frac{0.05}{2}\right)^{4}}+\frac{\S30}{\left(1+\frac{0.05}{2}\right)^{5}}}}\ {{\displaystyle{\vphantom{\displaystyle{\frac{1}{\left(1+\frac{0.05}{2}\right)}}^{\left(1+\frac{0.05}{2}\right)^{6}}}+\frac{\S30}{\left(1+\frac{0.05}{2}\right)^{7}}+\frac{\S1,030}{\left(1+\frac{0.05}{2}\right)^{8}}}}\end{array}
$$  

# 2.2.2 Day-Count  

Interest compounding is actually even more complicated, partly because the calendar years cannot be divided into equal semi-annual periods, quarters or months, and partly because of multiple day counting conventions designed to deal with that. A day-count convention prescribes two things: how to count days in the coupon accrual periods and how to count days in a year (or half-year).  

Suppose that, on September 30, 2013, ABC issues a $6\%$ semi-annual coupon $\$1,000$ face value bond maturing on September 30, 2015. Coupon accrual periods are October 1 through March 31 and April 1 through September 30. In Figure 2.9 we review three commonly used conventions: 30/360, Actual/Actual (similar to Actual/365), and Actual/360. The word Actual is usually abbreviated to Act.  

![](7f82fad43cecb572eb2625ac4b57385999d10a41a0097064d082ab0bef57550a.jpg)  
Figure 2.8A 4-year $6\%$ semi-annual coupon bond yielding $5\%$ : sum of the parts  

![](e32a0e8cd0f9fa63ff44d29c4d04a8e8a932ba068de75972ae80ca32b62284f2.jpg)  
Figure 2.9 Day-count conventions  

![](5b42f368e7a2504b91f0079a383b5274d7a8c06d18d75836b807ba674da13cab.jpg)  
Figure 2.10 The Act/Act day-count convention  

US corporate bonds follow the 30/360 convention, continental Europe bonds follow a. 30/360 convention modified by how month ends are treated, UK gilts follow Act/365, US. Treasuries follow Act/Act using half-years, and LIBOR money markets follow Act/360. In addition to day-count conventions, different markets may have different delays ranging from. zero to 3 (business) days between the end of the interest accrual period and the actual receipt of interest (and different countries have different holidays and thus business days!). The day-count convention can be followed by letters like m, mf, 2d, etc., to denote the rule on that. For example,. Eurodollar (LIBOR) deposits have a 2-business-day delay, using the UK holiday calendar.  

Not only the coupon accrual, but also discounting has to be modified to follow the correct convention. Let us look at the. $6\%$ semi-annual coupon bond maturing September 2015 in Figure 2.9. Let us assume that the bond follows the Act/Act day-count and that the yield is $5\%$ on the Act/Act basis. Figure 2.10 shows the valuation using the backward discounting. sweep method.  

# 2.2.3 Accrued Interest  

Except by coincidence, bonds are usually purchased between coupon dates. Once the ownership of the bond is transferred, the new owner will receive the full coupon on the next coupon payment date. Yet he will have held the bond only for the fraction of the full coupon period. from the purchase date till the next coupon date. The new buyer reimburses the current one for the portion of the coupon interest accrued from the last coupon date to the date of the purchase. This reimbursement is done "in advance" at the time of the purchase of the bond through the. payment of the accrued interest on top of the quoted price of the bond. The invoice or dirty. price of the bond is equal to the clean price of the bond plus the accrued interest. The clean price is just the present value of the coupons and principal. Bonds are thus quoted clean but settled dirty.  

![](a27a32f5f6d88b3705f9f3f0909db3c0f65ae5d7f17768413b44eee9a6465cd7.jpg)  
Figure 2.11Accrued interest  

The calculation of the accrued interest observes the day-count convention of the bond and involves prorating the current coupon between the coupon already accrued (due the current owner) and the coupon to be accrued (due the new owner). Suppose, on December 7, 2013, Jack purchases from Jill the $6\%$ Act/Act semi-annual coupon September 2015 bond issued by ABC Company. In addition to the clean price, Jack will have to pay Jill the accrued interest for the September 30-December 7, 2013, period. The calculation is illustrated in Figure 2.11.  

In the following sections, in order to keep the presentation uncluttered, we ignore the issues.   
of day-count, intra-year compounding and accruals, and stick to even divisions by 1, 2, or 4,.   
but the reader should at this point be able to modify all calculations to deal with the calendar.  
