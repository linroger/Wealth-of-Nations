---
tags:
  - asset_swap
  - bond_spreads
  - credit_risk
  - relative_value
  - swap_spread
  - treasury_spread
aliases:
  - Cash-CDS spread
  - I-spread
  - Z-spread
key_concepts:
  - Asset swap spread
  - Credit risk assessment
  - Relative value of bonds
  - Swap spread calculation
  - Yield spread measurement
---

# Relative value analysis
 
## Relative value analysis: bond spreads   

Investors measure the perceived market value, or relative value, of a corporate bond by  measuring its yield spread relative to a designated benchmark. This is the spread over the  benchmark that gives the yield of the corporate bond. A key measure of relative value of  a corporate bond is its swap spread. This is the basis point spread over the interest-rate  swap curve, and is a measure of the credit risk of the bond. In its simplest form, the swap  spread can be measured as the difference between the yield-to-maturity of the bond and  the interest rate given by a straight-line interpolation of the swap curve. In practice  traders use the asset-swap spread and the Z-spread as the main measures of relative value.  The government bond spread is also used. In addition, now that the market in synthetic  corporate credit is well established, using credit derivatives and credit default swaps  (CDS), investors consider the Cash-CDS spread as well, which is known as the  basis .  

Credit derivatives are introduced in the author’s book on structured credit products  (Choudhry 2004b) as well as his paper on the CDS basis (Choudhry 2004a).  

The spread that is selected is an indication of the relative value of the bond, and a  measure of its credit risk. The greater the perceived risk, the greater the spread should be.  This is best illustrated by the credit structure of interest rates, which will (generally) show  AAA- and AA-rated bonds trading at the lowest spreads and BBB- , BB- and lowerbonds trading at the highest spreads. Bond spreads are the most commonly-used  indication of the risk-return profile of a bond.  

In this section we consider the Treasury spread, asset swap spread, Z-spread and basis.  

# Swap spread and Treasury spread  

A bond’s swap spread is a measure of the credit risk of that bond, relative to the interestrate swaps market. Because the swaps market is traded by banks, this risk is effectively  the interbank market, so the credit risk of the bond over-and-above bank risk is given by  its spread over swaps. This is a simple calculation to make, and is simply the yield of the  bond minus the swap rate for the appropriate maturity swap. Figure 1 shows Bloomberg  page IRSB for Pounds sterling as at 10 August 2005. This shows the GBP swap curve on  the left-hand side. The right-hand side of the screen shows the swap rates’ spread over  UK gilts. It is the spread over these swap rates that would provide the simplest relative  value measure for corporate bonds denominated in GBP. If the bond has an odd maturity,  say 5.5 years, we would interpolate between the five-year and six-year swap rates.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/92edccb5b80450892d868f15e5da1ccbe4e90020a822198acb2aadf6bd9d6a1a.jpg)  

# Figure 1 Bloomberg page IRSB for Pounds sterling, showing GBP swap rates and  swap spread over UK gilts  

   Bloomberg L.P. All rights reserved. Reprinted with permission.  

The spread over swaps is sometimes called the  I-spread.  It has a simple relationship to  swaps and Treasury yields, shown here in the equation for corporate bond yield,  

$$
Y=I+S+T
$$  

where  

$Y$  is the yield on the corporate bond  
$I$  is the I-spread or spread over swap   
$S$    is the swap spread 
$T$     is the yield on the Treasury security (or an interpolated yield).  

In other words, the swap rate itself is given by   $T+S$  .  

The I-spread is sometimes used to compare a cash bond with its equivalent CDS price,  but for straightforward relative value analysis is usually dropped in favour of the assetswap spread, which we look at later in this section.  
Of course the basic relative value measure is the Treasury spread or government bond  spread. This is simply the spread of the bond yield over the yield of the appropriate  government bond. Again, an interpolated yield may need to be used to obtain the right  Treasury rate to use. The bond spread is given by:  

$$
B S=Y-T.
$$  

Using an interpolated yield is not strictly accurate because yield curves are smooth in  shape and so straight-line interpolation will produce slight errors. The method is still  commonly used though.  

# Asset-swap spread  

An asset swap is a package that combines an interest-rate swap with a cash bond, the  effect of the combined package being to transform the interest-rate basis of the bond.  Typically, a fixed-rate bond will be combined with an interest-rate swap in which the  bond holder pays fixed coupon and received floating coupon. The floating-coupon will be  a spread over Libor (see Choudhry  et al  2001). This spread is the asset-swap spread and  is a function of the credit risk of the bond over and above interbank credit risk.  Asset  swaps may be transacted at par or at the bond’s market price, usually par. This means that  the asset swap value is made up of the difference between the bond’s market price and  par, as well as the difference between the bond coupon and the swap fixed rate.  

The zero-coupon curve is used in the asset swap valuation. This curve is derived from the  swap curve, so it is the implied zero-coupon curve. The asset swap spread is the spread  that equates the difference between the present value of the bond’s cashflows, calculated  using the swap zero rates, and the market price of the bond. This spread is a function of  the bond’s market price and yield, its cashflows and the implied zero-coupon interest  rates.  

Figure 2 shows the Bloomberg screen ASW for a GBP-denominated bond, GKN  Holdings   $7\%$   2012, as at 10 August 2005. We see that the asset-swap spread is 121.5  basis points. This is the spread over Libor that will be received if the bond is purchased in  an asset-swap package. In essence the asset swap spread measures a difference between  the market-price of the bond and the value of the bond when cashflows have been valued  using zero-coupon rates. The asset-swap spread can therefore be regarded as the coupon  of an annuity in the swap market that equals this difference.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/66d10f999048a4edc84c761fbfccb077f1c97856c41c300c51c7f1c075cb0891.jpg)  
Figure 2 Bloomberg page ASW for GKN bond, 10 August 2005      Bloomberg L.P. All rights reserved. Reprinted with permission.  

# Z-Spread  

The conventional approach for analysing an asset swap uses the bond’s yield-to-maturity  (YTM) in calculating the spread. The assumptions implicit in the YTM calculation (see  Chapter 2) make this spread problematic for relative analysis, so market practitioners use  what is termed the   $\mathrm{Z}$  -spread instead. The   $\mathrm{Z}$  -spread uses the zero-coupon yield curve to  calculate spread, so is a more realistic, and effective, spread to use. The zero-coupon  curve used in the calculation is derived from the interest-rate swap curve.  

Put simply, the   $Z$  -spread is the basis point spread that would need to be added to the  implied spot yield curve such that the discounted cash flows of the a bond are equal to its  present value (its current market price). Each bond cashflow is discounted by the relevant  spot rate for its maturity term. How does this differ from the conventional asset-swap  spread? Essentially, in its use of zero-coupon rates when assigning a value to a bond.  Each cashflow is discounted using its own particular zero-coupon rate. The price of a  bond’s price at any time can be taken to be the market’s value of the bond’s cashflows.  Using the  $\mathrm{Z}$  -spread we can quantify what the swap market thinks of this value, that is, by  how much the conventional spread differs from the Z-spread. Both spreads can be viewed  as the coupon of a swap market annuity of equivalent credit risk of the bond being valued.  
In practice the Z-spread, especially for shorter-dated bonds and for better credit-quality  bonds, does not differ greatly from the conventional asset-swap spread. The   $\mathrm{Z}$  -spread is  usually the higher spread of the two, following the logic of spot rates, but not always. If it  differs greatly, then the bond can be considered to be mis-priced.  

Figure 3 is the Bloomberg screen YAS for the same bond shown in Figure 2, as at the  same date. It shows a number of spreads for the bond. The main spread of 151.00 bps is  the spread over the government yield curve. This is an interpolated spread, as can be seen  lower down the screen, with the appropriate benchmark bind identified. We see that the  asset-swap spread is 121.6 bps, while the Z-spread is 118.8 bps. When undertaking  relative value analysis, for instance if making comparisons against cash funding rates or  the same company name credit default swap (CDS), it is this lower spread that should be  used.  

The same screen can be used to check spread history. This is shown at Figure 4, the Zspread graph for the GKN bond for the six months prior to our calculation date.  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/8982a147828e39e5e3f2e6ab895e63a141620e47898c4792be658fa7181bde6e.jpg)  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/a2ef969a2f99daab6bc161510faf46175e24854f17a1fe26e0d7390d2efa7fc3.jpg)  
Figure 4 Bloomberg page YAS for GKN bond, 10 August 2005 showing Z-spread  history  

   Bloomberg L.P. All rights reserved. Reprinted with permission.  

Z-spread is closely related to the bond price, as shown by:  

$$
P=\sum_{i=1}^{n}\Biggl[\frac{C_{i}+M_{i}}{\bigl(1+\bigl(\bigl(Z+S_{i}+T_{i}\bigr)/\,m\bigr)\bigr)^{i}}\Biggr]
$$  

where $n$    is the number of interest periods until maturity   $P$    is the bond price   $C$    is the coupon   $M$    is the redemption payment (so bond cashflow is all   $C$   plus  $M_{\sun}$  )   $Z$    is the Z-spread   $m$    is the frequency of coupon payments.  

In effect this is the standard bond price equation with the discount rate adjusted by  whatever the  $\mathrm{Z}$  -spread is; it is an iterative calculation. The appropriate maturity swap rate  is used, which is the essential difference between the I-spread and the   $\mathrm{Z}$  -spread. This is  deemed to be more accurate, because the entire swap curve is taken into account rather  than just one point on it. In practice though, as we have seen in the example above, there  is often little difference between the two spreads.  
To reiterate then, using the correct   $Z$  -spread, the sum of the bond’s discounted cashflows  will be equal to the current price of the bond.  

We illustrate the  $Z$  -spread calculation at Figure 5. This is done using a hypothetical bond,  the XYZ plc   $5\%$   of June 2008, a three-year bond at the time of the calculation. Market  rates for swaps, Treasury and CDS are also shown. We require the spread over the swaps  curve that equates the present values of the cashflows to the current market price. The  cashflows are discounted using the appropriate swap rate for each cashflow maturity.  With a bond yield of   $5.635~\%$  , we see that the I-spread is 43.5   basis points, while the Zspread is 19.4 basis points. In practice the difference between these two spreads is rarely  this large.  

For readers benefit we also show the Excel formula in Figure 5. This shows how the Zspread is calculated; for ease of illustration we have assumed that the calculation takes  place for value on a coupon date, so that we have precisely an even period to maturity.  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/f5350059ec049140f1cfede1030cb3e795c39302dc90f663172075b14c424515.jpg)  
Figure 5 Calculating the Z-spread, hypothetical  $5\%$   2008 bond issued by XYZ plc  
# Cash-CDS basis  

The basis is the difference between a bond’s asset swap spread, or alternatively its Zspread, and the CDS price for the same bond issuer. So the basis is given by  

$$
B=D-I
$$  

where   $D$   is the CDS price. Where   $D\mathrm{~-~}I\,>\,0$   it is a positive basis; the opposite is a  negative basis.  

Figure 6 shows page  $\mathrm{G}<\mathrm{go}>$   on Bloomberg, set up to show the Z-spread and CDS price  history for the GKN 2012 bond, for the period March-Spetember 2005. We can select the  “Table” option to obtain the actual values, which can then be used to plot the basis. This  is shown at Figure 7, for the period 22 August to 22 September 2005. Notice how the  basis was always negative during August-September; we see from Figure 6 that earlier in  the year the basis had briefly been positive. Changes in the basis give rise to arbitrage  opportunities between the cash and synthetic markets. This is discussed in greater detail  in Choudhry (2004b).  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/b226182d2e310c4c5976b45945202713d5659889c22d355f873a2e33f8b7236f.jpg)  
Figure 6 Bloomberg graph using screen G <go>, plot of asset-swap spread and CDS  price for GKN bond, April-September 2005      Bloomberg L.P. All rights reserved. Reprinted with permission.  
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/d091cf96114ebf35b6edbcfe6311cd864d905c10da702075ba13246f56ca8fb3.jpg)  
Figure 7 GKN bond, CDS basis during August-September 2005  Data source: Bloomberg L.P.  

A wide range of factors drive the basis, which are described in detail in Choudhry  (2004a). The existence of a non-zero basis has implications for investment strategy. For  instance, when the basis is negative investors may prefer to hold the cash bond, whereas  if for liquidity, supply or other reasons if the basis is positive the investor may wish to  hold the asset synthetically, by selling protection using a credit default swap. Another  approach is to arbitrage between the cash and synthetic markets, in the case of a negative  basis by buying the cash bond and shorting it synthetically by buying protection in the  CDS market. Investors have a range of spreads to use when performing their relative  value analysis.  

