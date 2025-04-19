---
tags:
  - cpr
  - mortgage_valuation
  - prepayment_modeling
  - refinancing
  - s_curve
aliases:
  - Mortgage Prepayments
  - Prepayment Models
key_concepts:
  - CPR and mortgage rates
  - Mortgage pool characteristics
  - Prepayment model drivers
  - Refinancing S-curve
  - Refinancing incentive function
---

# 15.6 PREPAYMENT MODELING  

The complex behavior of prepayments, combined with their importance in.   
mortgage valuation, has given rise to a large industry of building models to.   
predict prepayments as a function of interest rates and other variables. While some highlights are presented in this section, and Appendix A15.2 presents.   
some of the more technical issues encountered, a fuller description is beyond.   
the scope of this chapter..  

Prepayment models are often divided into separate modules, one for. each driver of prepayments. The most notable drivers, mentioned earlier, are refinancing, turnover, defaults, and curtailments. Traditionally, a module makes a set of assumptions that depend on various parameters. These. parameters are then estimated historically, using the vast amount of data available on the prepayment behavior of mortgage pools. Some parameters. might also be implied from prevailing market prices of various pools. Most recently, artificial intelligence and machine learning technologies have also been brought to bear on the problem of predicting prepayments..  

At the heart of most refinancing modules is an S-curve, which describes. refinancings, often in terms of CPR, as a function of some incentive function. The incentive function might be the difference between the existing. mortgage rate and the current mortgage rate; the ratio of the existing rate to the current rate; the present value of the savings from refinancing; or even the monthly savings from such a refinancing. The S-curve than maps the refinancing incentive into a CPR. Figure 15.2 shows the S-curves of a particular model for the three pools summarized in Table 15.5. The horizontal axis here is simply the change in the current mortgage rate. Because existing. mortgage rates are fixed, of course, rising current mortgage rates imply less. of an incentive to prepay, while falling current mortgage rates imply more. of an incentive to prepay.  

![](ff6ab7c3470172684c777890374ed59ab1a2491dedcab3f085b201adea65abbb.jpg)  
FIGURE 15.2 Refinancing S-Curves for Three Mortgage Pools.  

The name "S-curve" comes from the shape of the functions. For large increases in rates, or, equivalently, very low incentives and high current mortgage rates, CPR is very low, while for large decreases in rates, or very high incentives and low current mortgage rates, CPR is very high. The curves in the figure do not look much like an "S," but the faster a curve moves from low to high CPR, the more the curve looks like something like an "S." In any case, the shape of the S-curve is different for each pool, and can depend on all of the characteristics discussed in the context of Table 15.5 (e.g., average loan size, creditworthiness). According to the models behind Figure 15.2, MA3538 prepays faster than CA2979, but, for a large enough decrease in mortgage rates, the CPR of CA2797 comes close to catching up. Figure 15.3 shows some empirical evidence with which these two S-curves might have been estimated. As the current coupon mortgage rate (which is defined herein) declined dramatically from between. $3.50\%$ and $4.00\%$ at the time of origination to less than. $1.50\%$ in fall 2020, the CPR of both pools rose dramatically. But MA3538 prepaid faster. As rates stayed low and increased somewhat, prepayments on both remained relatively high, but MA3538, on average, continued to prepay faster. By the way, this figure also shows why refinancing models are not cast as an optimization problem.  

![](b0afe85a9bd915e96f413fdb018fada44bc7f7c8f5cddb9315e86ec0f0805b19.jpg)  
FIGURE 15.3 One-Month CPR for FN MA3538 and FN CA2797 and the 30-Year Current Coupon Rate.  

If homeowners exercised their prepayment options with the efficiency of bond issuers exercising their call options, the pools in the figure would have experienced such dramatic prepayments through September 2020 that little to no principal would remain outstanding.  

Returning to Figure 15.2, the CPR of AI4813 is much lower than that of the other pools and picks up relatively slowly as rates decline. Contrasting its characteristics with those of CA2797 and MA3538, Table 15.5 reports that AI4813 was issued in June 2011, with a correspondingly shorter current WAM and WALA than the other pools. Its current WAC is essentially the same as that of CA2797. The current average loan size of AI4813 is. significantly smaller than that of either of the other pools, while its creditworthiness is marginally higher than that of CA2797. AI4813 is between the other two pools with respect to loan purpose, and the percentage of brokered originations is somewhat lower. The most likely explanation for the lower S-curve of AI4813, therefore, is not these loan characteristics but rather a. prepayment phenomenon known as burnout..  

When a seasoned or older pool has been through a period of relatively. low rates and experienced significant prepayments, it is most likely that the. homeowners with the greatest propensity to prepay have already prepaid and are no longer in the pool. With the remaining loans in the pool less likely to prepay, the pool experiences some degree of burnout. Figure 15.4 illustrates burnout in the case of AI4813. As the mortgage rate fell from about $4.00\%$ at the time of origination to between less than. $2.00\%$ and about  

![](e945a09e594e193e78c1d031840e64d883d4569fb872904c09bfba2958b3e5e7.jpg)  
FIGURE 15.4 One-Month CPR for FN AI4813 and the 30-Year Current Coupon Rate.  

$2.50\%$ from late 2012 through the first half of 2013, CPR increased dramatically, to a peak of about. $34\%$ . Rates then rose and fell again to between. $2.00\%$ and $2.50\%$ , and CPR reached a similar peak of over. $30\%$ in fall 2016. Rates subsequently rose a second time, peaking in November 2018, before starting on a third and more dramatic decline. This time, however, even when rates fell to $2.00\%$ , CPR never rose above $20\%$ . As a burned-out. pool, it was not until sometime after mortgage rates has fallen to new lows of. below $1.50\%$ that prepayments rose again, this time to a peak above. $40\%$ From a modeling standpoint, burnout introduces the significant complication that the S-curve depends not only on the current characteristics of a pool but also on the history of rates experienced by the pool.  

Mortgage professionals might also take the surge of AI4813 prepayments in 2021, as depicted in Figure 15.4, as evidence of a media effect. After a precipitous decline in mortgages rates, or after a decline in which mortgage rates reach new lows, media reports and party conversations encourage even those borrowers with low propensities to refinance to do so. Once again, this effect considerably complicates the determination of the S-curve.  

Another module of prepayment modeling captures turnover. A common approach to these modules is to start, at issue, from some base rate of turnover, which increases over time according to a seasoning ramp. This choice reflects the empirical regularity that homeowners are unlikely to move soon after taking out a mortgage. The exact specification of the seasoning ramp can depend on factors other than mortgage age, most obviously the season, as homeowners are more likely to move at certain times of the year,  

like soon before schools open rather than soon after. While prepayments.   
due to turnover are for the most part independent of mortgage rates, there.   
is a significant interaction. Borrowers are less likely to move if they have below-market mortgage rates, that is, if they would pay significantly higher.   
mortgage rates after selling their homes and buying new ones. This phe-.   
nomenon is known as the lock-in effect..  

As for modules for default, only a few observations are recorded here. Investors in agency MBS experience defaults as prepayments, but defaults are nevertheless tracked and modeled separately, as involuntary rather than voluntary prepayments. Inputs to these models include credit scores at the time of origination, because credit scores are typically not updated after issuance. While LTVs are not updated either, they can be estimated over time, at the loan level, by using data on home prices in a relevant region. Home prices are important in determining defaults, because a homeowner without cash - but with a home valued in excess of its mortgage balance - can sell the home and pay off the mortgage rather than default.  
