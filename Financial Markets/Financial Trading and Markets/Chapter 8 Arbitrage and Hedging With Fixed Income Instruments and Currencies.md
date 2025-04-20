---
tags:
  - arbitrage
  - bond_pricing
  - cash_flows
  - coupon_bonds
  - riskless_bonds
aliases:
  - Bond Arbitrage
  - Fixed Income Arbitrage
key_concepts:
  - Bond portfolio value
  - Bond replication
  - Cash flow series
  - Guaranteed payments
  - Riskless arbitrage
---

# Arbitrage and Hedging With Fixed Income Instruments and Currencies  

# 8.1 ARBITRAGE WITH RISKLESS BONDS  

As we discussed in Chapter 7, traders are very concerned with arbitrage, where riskless arbitrage involves the simultaneous purchase and sale of identical cash flows. The most easily arbitraged financial instruments are often those with guaranteed payments or with payments that are perfectly correlated with other instruments. Consider a set of riskless bonds whose coupon payments and redemption values are guaranteed. Such riskless bonds might be replicated by portfolios of other riskless bonds if their payments are similarly guaranteed and are to be made on the same dates. For example, consider the illustration provided in  Table 8.1 , which consists of three priced riskless bonds, all making payments on the same dates until they mature. The cash flow structure of any one-, two-, or three-year bond (e.g., Bond D) added to the market can be replicated with some portfolio of bonds A, B, and  $C,$   as long as all the cash payments to investors on Bond D are on the same dates as those made by at least one (in this example, two) of the three bonds A, B, and C.   For example, assume that there now exists Bond D, a threeyear,   $20\%$   coupon bond selling in this market for  $\mathbb{S}1360$  . This bond will make payments of   $\S200$   in years 1 and 2 in addition to a   $\mathbb{S}1200$   payment in year 3. We will demonstrate  $\mathsf C$  that a portfolio of bonds A, B, and   can be assembled to generate the same cash flow series as Bond D.  
TABLE 8.1 Coupon Bonds A, B, and C 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/718cc32863756619c4e0300d8b833a28a93022a96551158023d8fb3e1e103e6e.jpg)  

Thus, as we will demonstrate, Bond  $\mathrm{D}$   can be replicated by a portfolio of our first three bonds in the following quantities:    $b_{A}=0,$  ,    $\begin{array}{r}{b_{B}=3_{3}^{1},}\end{array}$  , and    $b_{C}=-\,{\dot{2}}_{3}^{1},$  , which are determined by the following system of equations:  

$$
\begin{array}{c}{200=40b_{A}+60b_{B}+0b_{C}}\\ {200=1040b_{A}+60b_{B}+0b_{C}}\\ {1200=1060b_{B}+1000b_{C}}\end{array}
$$  

This system sets the cash flows each year from Bond D equal to those of a portfolio comprising specific numbers of Bonds A, B, and C. There are many ways to solve this system for the numbers   $(b)$   of Bonds A, B, and   $\mathsf C$   to place in this replicating portfolio. One such way is to start by subtracting the first equation from the second equation, obtaining the following:  

$$
0=1000b_{A}
$$  

This is easily solved for    $b_{A}=0$  . Now, substitute    $b_{A}=0$   into our original second equation:  

$$
200=1040b_{A}+60b_{B}
$$  

Now, we see that    $b_{B}=3_{3}^{1}$  . Substitute this result into our original third equation:  

$$
\begin{array}{c}{1200=1060b_{B}+1000b_{C}}\\ {1200=3533.33+1000b_{C}}\end{array}
$$  

Now, solve this to obtain    $b_{C}=-\,2_{3}^{1},$  .  

Thus, we find from this system that    $b_{A}=0,\ b_{B}=3_{3}^{1},$  , and    $b_{C}=-\,2_{3}^{1}$  . We determine the value of the portfolio replicating Bond D by weighting their current market prices:  $(0\times\S1000)+(\bar{3}_{\bar{3}}^{1}\times\S1055.5\bar{)}+(-\,2_{\bar{3}}^{1}\times889)=\S14\bar{4}4$  Þ  ð Þ  \$1444. Based e portfolio’s price, the value of Bond D is \$1444, although its current market price is \$1360. Thus, a trader can gain an arbitrage profit from the purchase of this bond for   $\S1360$   financed by the sale of the portfolio of Bonds B and C at a price of   $\S1444$  . Shorting the portfolio implies selling  $3_{3}^{1}$    Bonds B and purchasing  $2_{3}^{1}$    Bonds C. Our cash flows in years 1, 2, and 3 will be zero, although we receive a positive cash flow now or time zero equal to   $\S1444\:-\:1360=84.$  . This is a clear arbitrage profit. This arbitrage opportunity will persist until the value of the portfolio equals the value of Bond D.  
Using matrix notation from text Appendix A.2, we have the following system to replicate Bond D:  

$$
\begin{array}{r}{\left[\begin{array}{c}{200}\\ {200}\\ {1200}\\ {\mathbf{cf_{d}}}\end{array}\right]=\left[\begin{array}{c c c}{40}&{60}&{0}\\ {1040}&{60}&{0}\\ {0}&{1060}&{1000}\end{array}\right]\quad\left[\begin{array}{c}{b_{A}}\\ {b_{B}}\\ {b_{C}}\\ {\mathbf{b}}\end{array}\right]}\end{array}
$$  

To solve this system we first invert matrix  CF , then use it to pre multiply vector    $\mathbf{cf_{D}}$   to obtain vector  b :  

$$
\begin{array}{r l r}{\left[\begin{array}{c}{0}\\ {3.33333}\\ {-2.33333}\end{array}\right]=\left[\begin{array}{c}{b_{A}}\\ {b_{B}}\\ {b_{C}}\end{array}\right]=\left[\begin{array}{c c c}{-0.001}&{0.001}&{0}\\ {0.017333}&{-0.0006667}&{0}\\ {-0.018373}&{0.000706667}&{0.001}\end{array}\right]}&{\left[\begin{array}{c}{200}\\ {200}\\ {1200}\end{array}\right]}\\ {{\bf b}}&{=}&{{\bf C F}^{-1}}&{{\bf c f_{d}}}\end{array}
$$  

This simple matrix system yields the same results as our system above. Cash flows, starting with time zero generated by the four-bond arbitrage portfolio, are represented in the following system:  

$$
\begin{array}{r}{\left[\begin{array}{c c c c}{-1000}&{-1055.5}&{-889}&{-1360}\\ {40}&{60}&{0}&{200}\\ {1040}&{60}&{0}&{200}\\ {0}&{1060}&{1000}&{1200}\end{array}\right]\quad\left[\begin{array}{c}{0}\\ {-3.33333}\\ {2.33333}\\ {1}\end{array}\right]=\left[\begin{array}{c}{84}\\ {0}\\ {0}\\ {0}\end{array}\right]}\end{array}
$$  

Thus, by buying Bonds C and D at quantities   $2_{3}^{1}$    and 1, respectively, and shorting Bond B in quantity   ${\dot{3}}_{3}^{1},$  , the arb it rage ur locks in a profit of 84 in time zero, and zero profits in the subsequent three years. The arbitrage portfolio is riskless because all bonds are presumed to be default risk-free and are presumed to be held to maturity, thereby eliminating interest rate and liquidity risk.  

# 8.2 FIXED INCOME HEDGING  

Fixed income instruments provide for fixed interest payments at fixed intervals and principal repayments. In the absence of default and liquidity risk (and hybrid or adjustable features), uncertainties in interest rate shifts are the primary source of pricing risk for many fixed income instruments. In this section, we will define a few terms used in the analysis of fixed income instruments and discuss how to manage interest rate uncertainty.  

# Bond Yields and Sources of Risk  

Assume that we wish to analyze a bond maturing in  $n$   periods with a  face value  (or principle amount) equal to    $F$   paying interest annually at a rate of    $c$  . The annual interest payment is rate    $c$   multiplied by face value    $F$   (or    $c F.$  ) and the bond makes a single payment in time  $n$   equal to  $F$  . Using a standard  present value  model discounting cash flows at a rate of  $k,$   the bond is evaluated as follows:  
$$
P V=\sum_{t=1}^{n}{\frac{c F}{{(1+k)}^{t}}}+{\frac{F}{{(1+k)}^{n}}}
$$  

For example, let    $c$   equal 0.10,  $F$   equal   $\mathbb{S}1000$  ,  $k$   equal 0.12, and  $n$   equal 2. The present value of this bond is computed as follows:  

$$
P V={\frac{100}{(1+0.12)^{1}}}+{\frac{100}{\left(1+0.12\right)^{2}}}+{\frac{1000}{\left(1+0.12\right)^{2}}}=966.20
$$  

Present value is used to determine the economic worth of a bond; the return of a bond measures the profit relative to the investment of a bond. There are several measures of bond return including current yield and yield to maturity. One such simple measurement, current yield , measures the annual interest payments relative to the initial investment required by the bond and is measured as follows:  

$$
\frac{c F}{P_{0}}
$$  

If the bond used in our example can be purchased for   $\S966.20$  , its current yield will be  $10.35\%$  .  

An analyst encounters two problems when using current yield as a return measure. First, the current yield does not account for any capital gain or loss   $(F\mathrm{~-~}P_{0})$   that may accrue when the bond matures. Second, current yield does not account for the time value of money or compounding of the cash flows associated with the bond. Hence, the analyst might wish to compute the bond’s internal rate of return, which is generally referred to as yield to maturity    $(y)$  :  

$$
P V=\sum_{t=1}^{n}{\frac{c F}{(1\!+\!y)^{t}}}+{\frac{F}{(1\!+\!y)^{n}}}
$$  

Yield to maturity is that value for  $y$   that satisfies  Equation (8.3)  (or  $k$   in  Equation (8.1) ). Usually, a solution must be obtained through an iterative process. The yield to maturity (or internal rate of return) for the bond described above is   $12\%$  , computed as follows:  

$$
P_{0}=966.20={\frac{100}{\left(1+0.12\right)^{1}}}+{\frac{100}{\left(1+0.12\right)^{2}}}+{\frac{1000}{\left(1+0.12\right)^{2}}}
$$  

Thus, yield to maturity can be interpreted as that discount rate which sets the purchase price of a bond equal to its present value.  

The  yield to call  for a callable bond is the bond’s yield assuming that it will be called or repurchased by its issuer. Yield to call differs from yield to maturity in three respects. First, cash flows are assumed to cease at the call date rather than the maturity date. Second, the call price is used for the yield computation as the bond’s final cash flow rather than the face value of the bond. Third, and only for some quotations, yield to call as calculated based on the call price and call date is quoted only if the bond is selling at a premium (more than face value); otherwise, yield to call is often quoted as yield to maturity instead. The rationale for this more convoluted convention is that if the bond is selling at a discount rather than a premium, it is less likely to be called and more likely to be held to maturity. In fact,  yield to worst  may apply if the bond has one or more call dates, in which case the yield to worst is the lowest of the yield scenarios assuming that the bond is called

 (or not called) so as to produce the worst possible yield for its owner.  
In general, bond risk might be categorized as follows:  

1.  Default or credit risk : The bond issuer may not fulfill all of its obligations.

 2.  Liquidity risk : An efficient market for investors to resell their bonds may not exist.

 3.  Interest rate risk : Market interest rate fluctuations affect values of existing bonds.  

In addition, if the bond can be called prior to maturity by its issuer, the bond owner faces call risk.  

U.S. Treasury issues are generally regarded as being practically free of default risk. Furthermore, there exists an active market for Treasury issues, particularly those maturing within a short period. Thus, Treasury issues are regarded as having minimal liquidity risk. However, all bonds are subject to interest rate risk. Longer-term bonds are subject to increased interest rate risk due to the increased periods that the yields on longer-term bonds are likely to differ from newly issued bonds. We will discuss hedging this interest risk shortly.  

# Fixed Income Portfolio Dedication  

Fixed income funds seek to ensure relatively stable income levels over given periods of time. Typically, a fixed income fund must provide payments to its creditors, clients, or owners for the given period. For example, a pension fund is often expected to make a series of fixed retirement payments to pension fund participants. Such funds must invest their assets to ensure that their liabilities are paid. In many cases, fixed income funds will purchase assets such that their cash flows exactly match the liability payments that they are required to make. This exact matching strategy is referred to as dedication or laddering and is intended to minimize the risk of the fund. The process of dedication is much the same as the arbitrage transactions discussed above; the fund manager merely determines the cash flows associated with his liability structure and replicates them with a series of default risk-free bonds. For example, assume that a pension fund manager needs to make payments to pension plan participants of  $\mathbb{S}12{,}000{,}000$   in one year,   $\mathbb{4}_{,}000{,}000$   in two years, and  $\mathbb{S}15{,}000{,}000$   in three years. The manager wishes to match these cash flows with a portfolio of Bonds A, B, and C whose characteristics were given above in  Table 8.1 . These three bonds must be used to match the cash flows associated with the fund’s liability structure. For example, in year 1, Bond A will pay   $\S40$  , B will pay  $\S60_{,}$  , and C will pay  $\S0$  . These payments must be combined to total  $\mathbb{S}12{,}000{,}000$  . Cash flows must be matched in years 2 and 3 as well. Only one exact matching strategy exists for this scenario. The following system can be solved for  $b_{A},\,b_{B},$   and  $b_{C}$   to determine exactly how many of each of the bonds are required to satisfy the fund’s cash flow requirements:  
$$
\begin{array}{l}{12,000,000=40b_{A}+60b_{B}+0b_{C}}\\ {14,000,000=1040b_{A}+60b_{B}+0b_{C}}\\ {15,000,000=1060b_{B}+1100b_{C}}\end{array}
$$  

Note the similarity of this system to the system presented in the previous section. There are many ways to solve this system for the numbers   $(b)$   of Bonds   $\mathrm{A},\,\mathrm{B},$   and C to dedicate to the institution’s portfolio of liabilities. One way to start is by subtracting the first equation from the second equation, obtaining the following:  

$$
2,000,000=1000b_{A}
$$  

This is easily solved for    $b_{A}=2000$  . Now, substitute    $b_{A}=2000$   into our original second equation:  

$$
14,000,000=1040b_{A}+60b_{B}
$$  

At this juncture, we see that  $b_{B}\!=\!198{,}666\{2/3\}$  . Substitute this result into our original third equation:  

$$
\begin{array}{l}{15,000,000=1060b_{B}+1000b_{C}}\\ {15,000,000=210,586,670+1000b_{C}}\end{array}
$$  

Now, solve this to obtain  $b_{C}=-195{,}586\{2/3\}$  .  

Thus, we find from this system that    $b_{A}=2000$  ,  $b_{B}=198{,}666{.}67$  , and    $b_{C}=-195{,}586{.}67{,}$  . We can determine the value of the portfolio of liabilities by weighting their current market prices:  $000\times\S1000)+(198,\!666.6{\bar{7}}\times\S1055.5)+(-198,\!586.67\times\!889)=\S37,\!816,\!120.$  Using matrix notation from Chapter 8 Appendix Section A.2, we have the following system to replicate the portfolio of liabilities:  

$$
\begin{array}{r}{\left[\begin{array}{c}{12,000,000}\\ {14,000,000}\\ {15,000,000}\\ {\mathbf{cf}_{\mathbf{L}}}\end{array}\right]=\left[\begin{array}{c c c c}{40}&{60}&{0}\\ {1040}&{60}&{0}\\ {0}&{1060}&{1000}\end{array}\right]\quad\left[\begin{array}{c}{b_{A}}\\ {b_{B}}\\ {b_{C}}\end{array}\right]}\end{array}
$$  

To solve this system, we first invert matrix  CF , and then use it to pre multiply vector    $\mathbf{cf}_{\mathbf{L}}$   to obtain vector  b :  

$$
{\begin{array}{r l r}{2000}&{}&{0}\\ {198666.67}&{}&{={\left[\begin{array}{l}{b_{A}}\\ {b_{B}}\\ {b_{C}}\end{array}\right]}={\left[\begin{array}{c c c}{-0.001}&{0.001}&{0}\\ {0}&{.017333}&{-0.0006667}&{0}\\ {-0.018373}&{0.000706667}&{0.001}\end{array}\right]}\quad{\left[\begin{array}{l}{12,000,000}\\ {14,000,000}\\ {15,000,000}\\ {\mathbf{c}\mathbf{f}_{\mathrm{L}}}\end{array}\right]}}\end{array}}
$$  

This simple matrix system yields the same results as our system above.  

Exact matching or dedication programs can be very effective when liquidity is sufficient to secure appropriately priced bonds with appropriate cash flow structures when needed. However, what if a portfolio manager needs to lock in a cash flow from her portfolio of bonds equal to, say,  $\mathbb{S}1\mathrm{,}000\mathrm{,}000$   on a specific date exactly 12 years, 3 months, and 2 days into the future? If no bonds are available on that date, some sort of approximation must be acceptable. Alternatively, what if such bonds are available, but overpriced? Again, the manager must work with an approximation or accept investment in overpriced bonds. In any case, dedication programs can limit managers with respect to what bonds they can purchase and in what quantities they must be purchased. Next, we will discuss portfolio immunization, which is not always as effective as an interest-rate hedging tool, but does allow for more flexibility.  
# 8.3 FIXED INCOME PORTFOLIO IMMUNIZATION  

As discussed earlier, bonds and certain other debt instruments issued by the U.S. Treasury are often regarded to be practically free of default risk and of relatively low liquidity risk. However, these bonds, particularly those with longer terms to maturity, are subject to market value fluctuations after they are issued, primarily due to changes in interest rates offered on new issues. Generally, interest rate increases on new bond issues decrease values of bonds that are already outstanding; interest rate decreases on new bond issues increase values of bonds that are already outstanding. Immunization models such as the duration model are intended to describe the proportional change in the value of a bond induced by a change in interest rates or yields of new issues.  

# Bond Duration  

Many analysts use present value models to value Treasury issues, frequently using yields to maturity of new Treasury issues to value existing issues with comparable terms. It is important for analysts to know how changes in new-issue interest rates will affect values of bonds with which they are concerned. Bond  duration  measures the proportional sensitivity of a bond to changes in the market rate of interest. Consider a two-year   $10\%$  coupon Treasury issue which is currently selling for   $\S966.20$  . The yield to maturity  $y$   of this bond is  $12\%$  . Default risk and liquidity risk are assumed to be zero; interest rate risk will be of primary importance. Assume that this bond’s yield or discount rate is the same as the market yields of comparable Treasury issues (which might be expected in an efficient market) and assume that bonds of all terms to maturity have the same yield. Further assume that investors have valued the bond such that its market price equals its present value; that is, the discount rate    $k$   for the bond equals its yield to maturity    $y$  . If market interest rates and yields were to rise for new Treasury issues, then the yield of this bond would rise accordingly. However, since the contractual terms of the bond will not change, its market price must drop to accommodate a yield consistent with the market. Assume that the value of an    $n$  -year bond paying interest at a rate of    $c$   on face value  $F$  is determined by a present value model with the yield  $y$   of comparable issues serving as  $k$  the discount rate :  

$$
P V=\sum_{t=1}^{n}{\frac{c F}{(1\!+\!y)^{t}}}+{\frac{F}{(1\!+\!y)^{n}}}
$$  
Assume that the terms of the bond contract,    $n,\,F,$   and  $c$   are constant. Just what is the proportional change in the price of a bond induced by a proportional change in market interest rates (technically, a proportional change in   $[1\,+\,y])?$   This can be approximated by the bond’s  Macaulay simple duration formula  as follows:  

$$
\frac{\Delta P V}{P V}\div\frac{\Delta(1+y)}{(1+y)}\approx D u r=\frac{d P V}{P V}\div\frac{d(1+y)}{(1+y)}=\frac{d P V}{d(1+y)}\times\frac{(1+y)}{P V}
$$  

Equation (8.5)  provides a reasonable approximation of the proportional change in the price of a bond induced by an infinitesimal proportional change in   $(1\,+\,y)$  . To derive this measure of a bond’s interest rate sensitivity ( Equation (8.5) ), we first rewrite  Equation (8.4)  in polynomial form (to take derivatives later) and substitute  $y$   for  $k$   (since they are assumed to be equal):  

$$
P V=\sum_{t=1}^{n}{\frac{c F}{(1\!+\!y)^{t}}}+{\frac{F}{(1\!+\!y)^{n}}}=\sum_{t=1}^{n}c F(1\!+\!y)^{-t}+F(1\!+\!y)^{-n}
$$  

Next, we find the derivative of    $P V$   with respect to   $(1+y)$  :  

$$
\frac{d P V}{d(1+y)}=\sum_{t=1}^{n}\,-t c F(1\!+\!y)^{-t-1}-n F(1\!+\!y)^{-n-1}
$$  

Equation (8.7)  can be rewritten:  

$$
\frac{d P V}{d(1+y)}=\frac{\displaystyle\sum_{t=1}^{n}-t c F(1\!+\!y)^{-t}-n F(1\!+\!y)^{-n}}{(1+y)}
$$  

Since the market rate of interest is assumed to equal the bond yield to maturity, the bond’s price    $P_{0}$   will equal its present value  $P V$  . Next, multiply both sides of  Equation (8.8)  by (1  $+\ y)\div\ P_{0}$   to obtain the bond’s proportional interest rate sensitivity, which is often more practical for portfolio purposes:  

$$
D u r=\frac{d P V}{d(1+y)}\times\frac{(1+y)}{P_{0}}=\frac{\displaystyle\sum_{t=1}^{n}{-t c F(1\!+\!y)^{-t}-n F(1\!+\!y)^{-n}}}{P_{0}}
$$  

Equation   $(8.9\mathrm{a})$   is equivalent to the right side of  Equation (8.5) . Thus, duration is defined as the proportional price change of a bond induced by an infinitesimal proportional change in   $(1+y)$   or 1 plus the market rate of interest:  

$$
D u r=\frac{d P V}{d(1+y)}\times\frac{(1+y)}{P_{0}}=\frac{\displaystyle\sum_{t=1}^{n}\frac{-t c F}{(1+y)^{t}}\,+\,\frac{-n F}{(1+y)^{n}}}{P_{0}}
$$  

Since the market rate of interest will likely determine the yield to maturity of any bond, the duration of the bond described above is determined as follows from  Equation (8.9b) :  

$$
\begin{array}{r}{D u r=\frac{\frac{-1\cdot0.1\cdot1000}{(1+0.12)}\,+\,\frac{-2\cdot0.1\cdot1000}{(1+0.12)^{2}}\,+\,\frac{-2\cdot1000}{(1+0.12)^{2}}}{966.20}=-\,1.907}\end{array}
$$  
This duration level of    $-1.907$   suggests that the proportional decrease in the value of this bond will equal 1.907 times the proportional increase in market interest rates. This duration level also implies that this bond has exactly the same interest rate sensitivity as a  pure discount bond  (a bond making no coupon payments) that matures in 1.907 years. Duration is always positive. Therefore, an increase in interest rates always decreases the value of a bond. However, although the mathematical value for duration is always negative, and we use that negative value for calculations requiring duration, practitioners normally ignore the minus sign when referring to duration. Its negative value is simply understood, and should never be taken to actually imply a positive relationship between interest rates and bond prices.  

Application of the simple Macaulay duration model does require several important assumptions. First, it is assumed that yields are invariant with respect to maturities of bonds; that is, the yield curve is flat. Furthermore, it is assumed that investors’ projected reinvestment rates are identical to the bond yields to maturity. Any change in interest rates will be infinitesimal and will also be invariant with respect to time. The accuracy of this model will depend on the extent to which these assumptions hold.  

# Portfolio Immunization  

Earlier, we discussed bond portfolio dedication, which is concerned with matching cash flows of bond portfolios with required payouts associated with liabilities. This process assumes that no transactions will take place within the portfolio and that cash flows associated with liabilities will remain as originally anticipated. Clearly, these assumptions will not hold for many institutions. Alternatively, one may hedge fixed income portfolio risk by using  immunization  strategies, which are concerned with matching the present values of asset portfolios with the present values of cash flows associated with future liabilities. More specifically, immunization strategies are primarily concerned with matching asset durations with liability durations. If asset and liability durations are matched, it is expected that the net fund value (equity or surplus) will not be affected by a very small shift in interest rates; asset and liability changes offset each other. Again, this simple immunization strategy is dependent on the following:  

1.  Changes in   $(1+y)$   are infinitesimal.  

2.  The yield curve is flat (yields do not vary over terms to maturity).

 3.  Yield curve shifts are parallel; that is, short- and long-term interest rates change by the same amount.

 4.  Only interest rate risk is significant.  

The first assumption, because it allows us to use derivatives to measure sensitivities, can only be an approximation when interest rates change by finite amounts. We will discuss bond convexity shortly as a correction for this scenario. Assumptions requiring flat yield curves and parallel yield curve shifts are useful in that we do not have to distinguish between different rates (e.g., short- and long-term rates) over the term of the bond. Immunization becomes significantly more complicated when we need to analyze fixed income risks such as those related to liquidity and default.  
# Immunization Illustration  

Let us revisit our portfolio dedication illustration discussed in the Fixed Income Hedging section. We note here that our illustration allows for a flat yield curve, such that all yields to maturity equal   $4\%$  . In this illustration, the pension fund manager still has anticipated cash payouts of   $\mathbb{12}{,}000{,}000$  ,  $\mathbb{4}_{}000_{},\!000_{},\!$  , and  $\mathbb{S}15{,}000{,}000$   over the next three years 1, 2, and 3. Now, suppose that the manager seeks to immunize interest rate risk associated with this liability stream with a portfolio. Rather than exactly match the liability outflow streams with bond inflows, the manager will match durations of the liability stream with the duration of the bond investment portfolio. This will ensure that changes in the value of the liability stream induced by interest rate changes are approximately the same as changes in the value of the bond portfolio. This will minimize fluctuations in the net value (assets minus liabilities) of the fund as interest rates vary. Bond details were given in  Table 8.1 . In addition, given the flat yield curve of   $4\%$  , the value of the liability stream is  $\S37{,}817{,}193{.}90$  .  

We calculate bond and liability stream durations as follows:  

$$
D u r_{A}=\frac{\displaystyle\frac{40}{1+0.04}+2\times\frac{1040}{\left(1+0.04\right)^{2}}}{-1000}=-\,1.962
$$  

$$
D u r_{B}=\frac{\displaystyle\frac{60}{1+0.04}+2\times\frac{60}{\left(1+0.04\right)^{2}}+3\times\frac{1060}{\left(1+0.04\right)^{3}}}{-\,1055.5}=-\,2.837
$$  

$$
D u r_{C}=\frac{3\times\cfrac{1000}{\left(1+0.04\right)^{3}}}{-\,889}=-\,3.000
$$  

$$
D u r_{L}=\frac{\displaystyle\frac{12,000,000}{1+0.04}+2\times\frac{14,000,000}{\left(1+0.04\right)^{2}}+3\times\frac{15,000,000}{\left(1+0.04\right)^{3}}}{-37,817,193.90}=-\,2.048
$$  

Portfolio immunization is accomplished when the duration (weighted average duration) of the portfolio of bonds equals the duration   $(-2.048)$   of the liability stream:  

$$
\begin{array}{c}{D u r_{A}\times w_{A}+D u r_{B}\times w_{B}+D u r_{C}\times w_{C}=D u r_{L}}\\ {w_{A}+\qquad\quad w_{B}+\qquad\quad w_{C}=1}\end{array}
$$  

$$
\begin{array}{c c}{-1.962\times w_{A}-2.837\times w_{B}-3.000\times w_{C}=-\,2.048}\\ {w_{A}+\qquad\quad w_{B}+\qquad\quad w_{C}=1}\end{array}
$$  

There is an infinity of solutions to this two-equation, three-variable system. Any solution that both satisfies these two equations and satisfies any other of the manager’s other constraints and/or preferences is acceptable. Next, suppose that the manager already has invested  $^{\S3,781,719.39}$   (  $.10\%$   of the total liability value) into Bond A and wants to hold this investment in Bond A constant at    $w_{A}=0.1$  . We solve for investment weights as follows:  
$$
\begin{array}{c}{-1.962\times w_{A}-2.837\times w_{B}-3\times w_{C}=-\,2.048}\\ {w_{A}+\qquad\quad w_{B}+\qquad w_{C}=1}\\ {w_{A}=3,781,719.39/37,817,193.90=0.1}\end{array}
$$  

Solving this   $3\times3$   system reveals that the immunized portfolio will have the following weights:    $w_{A}=0.1$  ,    $w_{B}=5.204.$  , and    $w_{C}\,{=}\,\,{-}\,4.304$  . Consider the following system:  

$$
\begin{array}{r l}{\left[\begin{array}{c}{-2.048}\\ {1}\\ {0.1}\\ {\textdollar{s}}\end{array}\right]=\left[\begin{array}{c c c}{-1.962}&{-2.837}&{-3}\\ {1}&{1}&{1}\\ {1}&{0}&{0}\end{array}\right]}&{\left[\begin{array}{c}{w_{A}}\\ {w_{B}}\\ {w_{C}}\end{array}\right]}\\ {\mathbf{Dur}}&{\mathbf{w}}\end{array}
$$  

We can solve this system by first inverting matrix  Dur , then using it to pre-multiply vector s  to obtain vector  w :  

$$
\begin{array}{r}{\left[\begin{array}{c}{0.1}\\ {5.256}\\ {-4.356}\end{array}\right]=\left[\begin{array}{c}{w_{A}}\\ {w_{B}}\\ {w_{C}}\end{array}\right]=\left[\begin{array}{c c c c}{0}&{0}&{1}\\ {6.135}&{18.405}&{-5.840}\\ {-6.135}&{-17.405}&{4.840}\end{array}\right]\quad\left[\begin{array}{c}{-2.048}\\ {1}\\ {0.1}\\ {\mathbf{s}}\end{array}\right]}\\ {\mathbf{w}\quad=\quad\begin{array}{c}{\mathbf{Dur}^{-1}}\\ {\mathbf{s}}\end{array}}\end{array}
$$  

This simple matrix system yields the same results as our system above. Note that small rounding differences can have significant effects on the final portfolio weighting results.  

Duration-immunized portfolios are most effective when interest rate changes are infinitesimal. Since interest rate changes are likely to be finite, immunization strategies will be improved if we correct for finite interest rate movements by using convexity. Duration is based on the first derivative of a bond’s price with respect to interest rates. This first derivative, or first order approximation, would be accurate only if the relationship were linear, which it is not. To correct for nonlinear i ties in this relationship, we match asset and liability portfolio convex i ties as well as durations to correct for finite interest rate changes. We will discuss convexity calculations next.  

# Convexity  

We used duration to determine the approximate change in a bond’s value induced by a change in interest rates   $(1\,+\,y)$  . However, the accuracy of the duration model is reduced by finite changes in interest rates, as we might expect. Duration may be regarded as a first order approximation (it only uses the first derivative) of the change in the value of a bond induced by a change in interest rates.  Convexity  is determined by the second derivative of the bond’s value with respect to   $(1~+~y)$  . The first derivative of the bond’s price with respect to   $(1+y)$   is given:  

$$
{\frac{\partial P_{0}}{\partial(1+y)}}=\sum_{t=1}^{n}\,-t c F(1\!+\!y)^{-t-1}-n F(1\!+\!y)^{-n-1}
$$  
We find the second derivative by determining the derivative of the first derivative as follows:  

$$
\begin{array}{c}{{\displaystyle\frac{\partial^{2}P_{0}}{\partial{(1+y)}^{2}}=\left[\sum_{t=1}^{n}-t(-t-1)c F(1\!+\!y)^{-t-2}\right]-[n(-n-1)F(1\!+\!y)^{-n-2}]}}\\ {{=\displaystyle\left[\sum_{t=1}^{n}\frac{(t^{2}+t)c F}{(1+y)^{t+2}}\right]+\left[\frac{(n^{2}+n)F}{(1+y)^{n+2}}\right]}}\end{array}
$$  

Convexity is merely the second derivative of    $P_{0}$   with respect to   $(1+y)$   divided by  $P_{O}$  :  

$$
C o n v e x i t y=\frac{\left[\sum_{t=1}^{n}\frac{(t^{2}+t)c F}{(1+y)^{t+2}}\right]+\left[\frac{(n^{2}+n)F}{(1+y)^{n+2}}\right]}{P_{0}}
$$  

The first two derivatives can be used in a second-order Taylor series expansion to approximate new bond prices induced by changes in interest rates as follows:  

$$
\begin{array}{l}{P_{1}\approx P_{0}+f(1+y_{0})\cdot\left[\Delta(1+y)\right]+\displaystyle\frac{1}{2!}\cdot f^{\prime\prime}(1+y_{0})\cdot\left[\Delta(1+y)\right]^{2}}\\ {P_{1}\approx P_{0}+\left[\displaystyle\sum_{t=1}^{n}\frac{-t c F}{(1+y_{0})^{t+1}}-\frac{n F}{(1+y_{0})^{n+1}}\right]\left[\Delta y\right]}\\ {\qquad+\displaystyle\frac{1}{2}\left[\displaystyle\sum_{t=1}^{n}\frac{(t^{2}+t)\cdot c F}{(1+y_{0})^{t+2}}+\frac{(n^{2}+n)\cdot F}{(1+y_{0})^{n+2}}\right]\cdot\left[\Delta y\right]^{2}}\\ {\qquad=P_{0}+D u r\cdot\displaystyle\frac{P_{0}}{1+y_{0}}\cdot\left[\Delta y\right]+\displaystyle\frac{1}{2}\cdot P_{0}\cdot c o n v e x i t y\cdot\left[\Delta y\right]^{2}}\end{array}
$$  

Consider a five-year,   $10\%$  ,  $\mathbb{\S}1000$  -face-value coupon bond currently selling at par (face value). We might compute the present yield to maturity of this bond as  $y_{0}=0.10$  . The first derivative of the bond’s value with respect to   $(1\,+\,y)$   at  $y_{0}=0.10$   is found from  Equation (8.12)  to be 3790.78 (duration is   $3790.78\ \times\ 1.1\ \div\ 1000=4.1698)$  ); the second derivative is found from  Equation (8.13)  to be 19,368.34 (convexity is   $19{,}368.34{\div}1000=19.36834{,}$  , or rounded at 19.37). If bond yields were to drop from 0.10 to 0.08, the actual value of this bond would increase to 1079.85, as determined from a standard present value model. If we were to use the duration model (first-order approximation from the Taylor expansion, based only on the first derivative), we estimate that the value of the bond increases to

 1075.8157. If we use the convexity model second-order approximation from  Equation

 (8.16) , we estimate that the value of the bond increases to 1079.6894.  

Note that this second estimate with the second-order approximation generates a revised bond value that is significantly closer to the bond’s actual value as measured by the present value model. Therefore, the duration and immunization models are substantially improved by the second order approximations of bond prices (the convexity model). The fund manager wishing to hedge portfolio risk should not simply match durations (first derivatives) of assets and liabilities, he should also match their convex i ties (second derivatives).  
Now, let us reconsider our portfolio dedication illustration from  Section 8.2  and the portfolio immunization illustration from above. In this illustration, the pension fund manager has anticipated cash payouts of   $\mathbb{S}12{,}000{,}000$  ,   $\mathbb{14,000,000,}$  , and   $\mathbb{S}15{,}000{,}000$   over the next three years. We calculate bond A, B, and   $\mathsf C$   convex i ties along with that for the liability stream as follows:  

$$
C o n v_{A}=\frac{2\times\cfrac{40}{\left(1+0.04\right)^{3}}+6\times\cfrac{1040}{\left(1+0.04\right)^{4}}}{1000}=5.405
$$  

$$
C o n v_{B}=\frac{2\times\displaystyle\frac{60}{\left(1+0.04\right)^{3}}+6\times\displaystyle\frac{60}{\left(1+0.04\right)^{4}}+12\times\displaystyle\frac{1060}{\left(1+0.04\right)^{5}}}{-1055.5}=10.298
$$  

$$
C o n v_{C}=\frac{12\times\cfrac{1000}{\left(1+0.04\right)^{5}}}{-\;889}=11.095
$$  

$$
C o n v_{L}=\frac{2\times\cfrac{12,000,000}{\left(1+0.04\right)^{3}}+6\times\cfrac{14,000,000}{\left(1+0.04\right)^{4}}+12\times\cfrac{15,000,000}{\left(1+0.04\right)^{5}}}{-37,816.120}=6.375
$$  

Portfolio immunization is accomplished when the weighted averages of the duration and the convexity of the portfolio of bonds equals the duration and convexity (6.375) of the liability stream:  

$$
\begin{array}{c}{D u r_{A}\times w_{A}+D u r_{B}\times w_{B}+D u r_{C}\times w_{C}=D u r_{L}}\\ {C o n v_{A}\times w_{A}+C o n v_{B}\times w_{B}+C o n v_{C}\times w_{C}=C o n v_{L}}\\ {w_{A}+\qquad\quad w_{B}+\qquad\quad w_{C}=1}\end{array}
$$  

$$
\begin{array}{c}{-1.962\times w_{A}-2.837\times w_{B}-3\times w_{C}=-2.048}\\ {5.405\times w_{A}+10.298\times w_{B}+11.095\times w_{C}=6.375}\\ {w_{A}+\qquad\quad w_{B}+\qquad\quad w_{C}=1}\end{array}
$$  

The single solution to this   $3\times3$   system of equations is    $w_{A}=0.106$  ,    $w_{B}=5.166.$  , and  $w_{C}\,{=}\,\,{-}\,\,4.272$  . Again, rounding in calculations does affect final results; with less rounding,  $w_{A}=0.100151$  ,    $w_{B}=5.207593,$  , and  $w_{C}=-4.30774$  . Nevertheless, this system provides an improved immunization strategy when interest rate changes are finite.  

# 8.4 TERM STRUCTURE, INTEREST RATE CONTRACTS, AND HEDGING  

Thus far in this chapter, we have discussed fixed income arbitrage and hedging without use of derivative instruments such as forward and futures contracts. Also, in  Section 8.3 , we assumed that yield curves were flat, and that shifts in the yield curve are parallel.  
Here, we will discuss long-term interest rates as a function of short-term rates, both originating at time zero (spot rates, based on loans originating now or time zero) and shortterm rates originating in the future (forward rates, based on loans originating in the future at rates locked in now). In fact, we will argue that long-term interest rates are related to a combination of short-term rates on loans originating now (spot rates) and on loans originating in the future (forward rates). More specifically, the long-term spot rate will be expressed as a geometric mean of short-term spot and forward interest rates. In addition, we will discuss how to use forward and futures contracts to arbitrage fixed income instruments and to hedge fixed income portfolios. At the end of this section, after having discussed the relationship between long-term spot rates and short-term rates, we will discuss the evolution of short-term rates.  

# The Term Structure of Interest Rates  

The  term structure of interest rates  is concerned with interest rates on debt securities and how these rates vary with respect to varying dates of maturity. For example, term structure might be concerned with why the interest rate on debt maturing in one year is   $2\%$  versus   $5\%$   for debt maturing in 20 years. Generally at a given point in time, we observe longer-term interest rates exceeding shorter-term rates ( normal yield curves ), although this is not always the case (e.g., the years 1980  1983 when we observed  inverted yield curves ).  

The  pure expectations theory  states that long-term spot rates (interest rates on loans originating now) can be explained as a product of short-term spot rates and short-term forward rates (interest rates on loans committed to now but actually originating at later dates). Where  $y_{t,t-1}$   is the ate on a one-period, zero-coupon instrument originated at time  $_{t-1}$   to be repaid at time  t , the pure expectations theory defines the relationship between longand short-term interest rates as follows:  

$$
(1+y_{0,n})^{n}=\prod_{t=1}^{n}(1+y_{t-1,t})
$$  

Thus, one plus the long-term spot rate  $y_{0,n}$   is defined as  $n$  -th root minus one of the product of the one-period spot rate    $y_{0,1}$   plus one and a series of one-period forward rates  $y_{t-1,t}$  plus one. In other words, the long-term spot rate    $y_{0,n}$   can be determined based on the short-term spot rate  $y_{0,1}$   and a series of one-period forward rates  $y_{t-1,t}$   as follows:  

$$
y_{0,n}=\sqrt[n]{\prod_{t=1}^{n}(1+y_{t-1,t})}-1
$$  

Consider an example where the one-year spot rate  $y_{0,1}$   is   $5\%$  . Investors are expecting that the one-year spot rate one year from now will increase to   $6\%$  ; thus, the one-year forward rate    $y_{1,2}$   on a loan originated in one year is   $6\%$  . This means that investors can lock in an interest rate of  $6\%$   on a one-year loan originating in one year and maturing in two years. Furthermore, assume that investors are expecting that the one-year spot rate two years from now will increase to  $7\%$  ; thus, the one-year forward rate  $y_{2,3}$   on a loan originated in two years is   $7\%$  . Based on the pure expectations hypothesis, what is the three-year spot rate? This is determined with  Equation (8.21)  as follows:  
$$
\begin{array}{l l}{y_{0,n}=\sqrt[n]{\prod_{t=1}^{n}(1+y_{t-1,t})}-1=\sqrt[3]{(1+y_{0,1})(1+y_{1,2})(1+y_{2,3})}-1}\\ {\ }\\ {\ \ \ \ \ \ \ \ \ \ \ =\sqrt[3]{(1+0.05)(1+0.06)(1+0.07)}-1=0.05997}\end{array}
$$  

# Term Structure Estimation With Coupon Bonds  

The  spot rate  is the yield at present prevailing for zero coupon bonds of a given maturity. The    $t$   year spot rate is denoted here by    $y_{0,t},$   which represents the interest rate on a loan to be made at time zero and repaid in its entirety at time    $t.$  . Spot rates can be estimated from bonds with known future cash flows and their current prices. We can obtain spot rates from yields implied from series of coupon bonds if the law of one price holds.  

These next few sub-sections are concerned with how interest rates or yields vary with maturities of bonds. The simplest bonds to work with from an arithmetic perspective are pure discount notes , that is, notes that make no interest payments. Such notes make only one payment at one point in time—on the maturity date of the note. Determining the relationship between yield and term to maturity for these bonds is quite trivial. The return obtained from a pure discount note is strictly a function of capital gains; that is, the difference between the face value of the note and its purchase price. Short-term U.S. Treasury bills are an example of pure discount (or zero coupon) notes. Coupon bonds are somewhat more difficult to work with from an arithmetic perspective because they make payments to bond holders at a variety of different periods typically every year or every 6 months.  

# Boots trapping the Yield Curve  

The yield curve can be obtained empirically by examining the payoffs associated with a bond simultaneously with the bond’s purchase price. Let    $D_{t}$   be the discount function for time  $t;$   that is,    $D_{t}=\dot{1}/(1+\,y_{0,t})^{t}$  . This means that a coupon payment    $c F$   or payment to face value  $F$   made at time    $t$   will be discounted by multiplying it by the discount function    $D_{t}$  :  

$$
P V=\sum_{t=1}^{n}c F\times D_{t}+F D_{n}=\sum_{t=1}^{n}c F/(1\!+\!y_{0,t})^{t}+F/(1\!+\!y_{0,n})^{n}
$$  

A little algebra on the    $D_{t}$   equality above produces the following spot rate:  

$$
y_{0,t}=(1/D_{t})^{1/t}-1
$$  

Thus, one can obtain spot rates    $y_{0,t}$   from the bond’s current purchase price    $P_{0}$   and expected future cash flows from coupon payments  $c F$   and face value  $F$  . Consider a  $\mathbb{S}1000$  face value bond making a single interest payment at an annual rate of   $5\%$   (see  Table 8.2 ). Suppose this bond is currently selling for 102 (actually meaning   $102\%$   of its face value, or  
TABLE 8.2 Boots trapping Spot Rates 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/6e5195fc76e0b09934035cc07173d2f6186b110a26cc0c7b15f0dcd37d02d966.jpg)  

1020) and that it matures in one year when its coupon payment is made. The one-year spot rate implied by this bond is determined as follows:  

$$
\begin{array}{c}{1020=(50+1000)\times D_{1}=(1050)/(1+y_{0,1})^{1}}\\ {D_{1}=1020/1050=(0.9714286)^{1/1};\;1/0.9714286-1=y_{0,1}=0.0294}\end{array}
$$  

The one-year spot rate is  $2.94\%$  . However, a difficulty arises when the bond has more than one cash flow. As spot rates may vary over time, there may be a spot rate for each period, hence, a spot rate for each cash flow. Now, consider a   $\mathbb{S}1000$   face value, two-year, bond making interest payments at an annual rate of   $5\%$   (again, see  Table 8.2 ). Suppose that this bond is currently selling for 101.75 (meaning   $101.75\%$   or 1017.5) and that it matures in two years when its second coupon payment is made. The two-year spot rate implied by this bond is boots trapped from the one-year bond as follows:  

$$
\begin{array}{c}{1017.5=50\times0.9714286+(50+1000)\times D_{2}}\\ {D_{2}=[1017.5-(50\times0.9714286)]/[50+1000]=0.9227891}\\ {(1/.9227891)^{1/2}-1=y_{0,2}=0.0410}\end{array}
$$  

Boots trapping simply means to make use of the rate (the one-year rate) or information that is already known to obtain the desired result (the two-year rate). The three-year spot rate  $y_{0,3}$   implied by the three-year bond from  Table 8.2  is boots trapped from the one-year and two-year bonds as follows:  
$$
\begin{array}{c}{1015.0=50\times0.9714286+50\times0.9227891+(50+1000)\times D_{3}}\\ {D_{3}=[1015-(50\times0.9714286)-(50\times0.9227891)]/[50+1000]=0.8764658}\\ {(1/.8764658)^{1/3}-1=y_{0,3}=0.0449}\end{array}
$$  

Boots trapping to map out the  $n$  -year yield curve requires that there be one bond maturing in each year  $t$   for    $t=1$   to    $n$   so that its  $D_{t}$   can be used to determine (bootstrap) the    $D_{t}$   for the bond maturing in one-year subsequent ( Figure 8.1 ). Thus, one starts by determining  $D_{1},$   then    $D_{2}$   and so on until all    $D_{t}$   values have been determined through year  $n$  .  

If we accept the Pure Expectations Theory for the term structure of interest rates, we can obtain forward rates from spot rates. Any  $i.$  -year forward rate,  $y_{t-i,t},$   from year    $t-\,i$   to year    $t$  is determined from   $\large(D_{t}/\hat{D_{t-i}}\large)^{1/i}-\,1$  . For example, the two-year spot rate is a function of the one-year spot rate and the one-year forward rate on a loan originating in one year as follows:  

p ﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃ p ﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃ 
$$
y_{0,2}=0.0410={\sqrt{(1+y_{0,1})(1+y_{1,2})}}-1={\sqrt{(1+0.0294)(1+y_{1,2})}}-1
$$  

We can use this relationship to solve for the one-year forward rate on a loan originating in one year as follows:  

$$
\begin{array}{c}{(1+0.0410)^{2}=(1+0.0294)(1+y_{1,2})}\\ {y_{1,2}=\displaystyle\frac{(1+0.0410)^{2}}{(1+0.0294)}-1=0.052731}\end{array}
$$  

Similarly, we can solve for the one-year forward rate on a loan originating in two years, forward rate  $y_{2,3},$   as follows:  

$$
\begin{array}{c}{(1+0.0449)^{3}=(1+0.0294)(1+0.052731)(1+y_{2,3})}\\ {y_{2,3}=\displaystyle\frac{(1+0.0449)^{3}}{(1+0.0294)(1+0.052731)}-1=0.052744}\end{array}
$$  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/99f501fb52b2cbb478ab7b0ee13cf9a75efde2a1e10d6b7a4437d202efbcf1af.jpg)  

FIGURE 8.1 Mapping the yield curve.  
The two-year forward rate on a loan originating in one year, forward rate  $y_{1,3},$   is determined as follows:  

$$
\begin{array}{c c}{(1+0.0449)^{3}=(1+0.0294)(1+y_{1,3})^{2}}\\ {y_{1,3}=\displaystyle\sqrt{\frac{(1+0.0449)^{3}}{(1+0.0294)}}-1=0.052737}\end{array}
$$  

which is identical to  

p ﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃﬃ 
$$
y_{1,3}=\sqrt{(1+0.052731)(1+0.052744)}-1=0.052737
$$  

# Simultaneous Estimation of Discount Functions  

A coupon bond might be treated as a portfolio of pure discount notes, with each coupon payment being treated as a separate note maturing on the date the coupon is paid. Consider an example involving three bonds whose characteristics are given in  Table 8.3 . The three bonds are trading at known prices with a total of eight annual coupon payments among them (three for bonds F and  $\mathrm{G}$   and two for bond E). Bond yields or spot rates must be determined simultaneously to avoid associating contradictory rates for the annual coupons on each of the three bills.  

Let  $D_{t}$   be the discount function for time  $t;$   that is,  $D_{t}=1/(1\,+\,y_{0,t})^{t}$  . Since  $y_{0,t}$   is the spot rate or discount rate that equates the present value of a bond with its current price, the following equations may be solved for discount functions then spot rates:  

$$
\begin{array}{c}{947.376=50D_{1}+1050D_{2}}\\ {904.438=60D_{1}+60D_{2}+1060D_{3}}\\ {981=90D_{1}+90D_{2}+1090D_{3}}\end{array}
$$  

This system of equations might be represented by the following system of matrices:  

$$
\begin{array}{r l r}{\left[\begin{array}{c c c}{50}&{1050}&{0}\\ {60}&{60}&{1060}\\ {90}&{90}&{1090}\end{array}\right]}&{{}\left[\begin{array}{c}{D_{1}}\\ {D_{2}}\\ {D_{3}}\end{array}\right]=\left[\begin{array}{c}{947.376}\\ {904.438}\\ {981}\\ {\mathbf{P}_{0}}\end{array}\right]}\end{array}
$$  

To solve this system we first invert matrix CF, and then use this inverse to pre multiply  $P_{0}$   $d$  vector  to obtain vector :  

$$
\begin{array}{r}{\left[\begin{array}{c c c}{-0.001}&{-0.03815}&{0.0371}\\ {0.001}&{0.00181667}&{-0.00177}\\ {0}&{0.003}&{-0.002}\end{array}\right]\quad\left[\begin{array}{c}{947.376}\\ {904.438}\\ {981}\end{array}\right]=\left[\begin{array}{c}{D_{1}}\\ {D_{2}}\\ {D_{3}}\end{array}\right]=\left[\begin{array}{c}{0.943377}\\ {0.85734}\\ {0.751316}\end{array}\right]}\\ {\mathbf{C}\mathbf{F}^{-1}\qquad\qquad\qquad\qquad\mathbf{P}_{0}\qquad=\qquad\mathbf{d}}\end{array}
$$  

TABLE 8.3 Coupon Bonds E, F, and G  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/dcfabe901845b21e4f62d757eebff1c6820f6b9a72a9d2b6f2987058d223aca9.jpg)  
Thus, we find from solving this system for vector  $d$   that    $D_{1}=0.943377,$  ,    $D_{2}=0.85734,$  , and  $D_{3}\,{=}\,0.751316$  . Since    $D_{t}=\bar{1/}(1\,+\,\dot{y}_{0,t})^{t},$  ,  $1/D_{t}=(1\,+\,y_{0,t})^{t}\,\!,$  , and    $y_{0,t}=1/D^{1/t}\,-\,1$  . Thus, spot rates are determined as follows:  

$$
\begin{array}{c}{\displaystyle\frac{1}{D_{1}}-1=0.06=y_{0,1}}\\ {\displaystyle\frac{1}{D_{2}^{1/2}}-1=0.08=y_{0,2}}\\ {\displaystyle\frac{1}{D_{3}^{1/3}}-1=0.10=y_{0,3}}\end{array}
$$  

Note that there exists a different spot rate (or discount rate) for each term to maturity; however, the spot rates for all cash flows generated by all bonds at a given period in time are the same. Thus,    $y_{0,t}$   will vary over terms to maturity, but will be consistent for all bonds in a given time period. Thus, for example, the values of the three bonds are determined as follows:  

$$
947.376=50D_{1}+1050D_{2}={\frac{50}{\left(1+0.06\right)^{1}}}+{\frac{1050}{\left(1+0.08\right)^{2}}}
$$  

$$
904.438=60D_{1}+60D_{2}+1060D_{3}={\frac{60}{\left(1+0.06\right)^{1}}}+{\frac{60}{\left(1+0.08\right)^{2}}}{\frac{1060}{\left(1+0.10\right)^{3}}}
$$  

$$
981=90D_{1}+90D_{2}+1090D_{3}=\frac{90}{\left(1+0.06\right)^{1}}+\frac{90}{\left(1+0.08\right)^{2}}\frac{1090}{\left(1+0.10\right)^{3}}
$$  

Any other bond with cash flows paid at the ends of some combination of years one, two, and three must have a value that is consistent with these three spot rates. For example, a  $2\%$   $\mathrm{H}$  three-year  coupon Bond   must be valued as follows:  

$$
P_{H}=20D_{1}+20D_{2}+1020D_{3}={\frac{20}{\left(1+0.06\right)^{1}}}+{\frac{20}{\left(1+0.08\right)^{2}}}{\frac{1020}{\left(1+0.10\right)^{3}}}=802.36
$$  

A different market price for Bond   $\mathrm{H}$   will lead to an arbitrage opportunity. In addition, prices for Bonds  $\mathrm{E,~F,}$   and   $\mathrm{G}$   above will lead to the following forward rates:  

$$
\begin{array}{c c}{y_{1,2}=\displaystyle\frac{\left(1+0.08\right)^{2}}{\left(1+0.06\right)}-1=0.10}\\ {\displaystyle y_{2,3}=\displaystyle\frac{\left(1+0.10\right)^{3}}{\left(1+0.06\right)\left(1+0.10\right)}-1=0.14}\\ {\displaystyle y_{1,3}=\sqrt{\frac{\left(1+0.10\right)^{3}}{\left(1+0.06\right)}-1}=0.12}\end{array}
$$  

Again, contract or bond contracts that are inconsistent with these rates lead to arbitrage opportunities.  
# 2 The Evolution of Short-Term Rates  

As we discussed earlier in this section, the yield curve depicts varying spot rates over associated terms to maturity. Understanding the nature of the uncertainty that drives spot and forward rates, particularly short term rates is essential to understanding fixed income instruments. The  Merton (1973)  term structure model prices bonds based on the assumption that short-term interest rates (more precisely, instantaneous spot    $r_{0}$   and forward rates  $r_{t})$   are related to an arithmetic Brownian motion process    $Z_{t},$   similar to the stock price model in Section 7.1:  

$$
d r_{t}=\mu d t+\sigma d Z_{t}
$$  

Instantaneous rates    $r_{t}$   following arithmetic Brownian motion are normally distributed, and normal distributions are often very easy to work with. On the other hand, changes in interest rates are unrelated to historical or long-term mean rates    $\bar{r}.$  . This means that directional moves for short term interest rates cannot be predicted based on available information, particularly when the drift    $\mu$   is low compared to interest rate volatility    $\sigma$  . The range of potential interest rate changes is from an unreasonable negative infinity to positive infinity. Negative interest rates are very possible under Brownian motion, but may seem less likely (though not impossible) in practice.  

These problems that can produce negative interest rates and constant interest rate volatility can be alleviated with the  Rendleman and Bartter (1980)  geometric Brownian motion process model for short-term interest rates:  

$$
d r_{t}=\mu r_{t}d t+\sigma r_{t}d Z_{t}
$$  

In this model, the long-term interest rate is log normally distributed with drift parameter    $\mu$  and volatility parameter    $\sigma,$   a handy quality for modeling in continuous time. As interest rates  $r_{t}$   approach zero, the drift    $\mu r_{t}$   and rate volatility    $\sigma r_{t}$   approach zero, and rates will not turn negative. Volatility and drift will increase as rates increase from zero in this geometric Brownian motion process.  

Unfortunately, neither of these models capture the tendency for short term interest rates to revert towards some long-term mean rate  $\bar{r}$   as we often observe in actual financial markets. This long-term mean interest rate  $\bar{r}$   is not necessarily (though could be) the same as the longterm spot rate that we discussed earlier, but the mean of short-term rates over an extended period of time. For example, we might observe that when the short-term spot rate exceeds the long-term mean rate   $(r_{0}>\bar{r})$  , the drift might be expected to be negative so that the shortterm rate drifts down towards the long-term mean rate. We might say that the interest rates are currently high in this scenario, and we expect for them to drop towards the long-term mean. When the short-term rate  $r_{0}$   is less than the long-term rate   $(r_{0}<\bar{r})$  , the drift might be expected to be positive. Thus, the short-term rate has a tendency to revert to its long-term mean  ${\bar{r}},$  , whose value might be the value justified by economic fundamentals such as capital productivity, long-term monetary policy, etc.  
Define the term  $0<\lambda<1$   to be a constant that reflects the speed of the mean-reverting adjustment for the instantaneous rate  $r_{t}$   towards its constant long-term mean rate  $\bar{r}.$  ; that is,    $\lambda$  is the mean reversion factor, sometimes called a “pullback factor.” This pullback factor is typically estimated or calibrated based on a statistical analysis of historical data. Let    $\sigma d Z_{t}$  represent random shocks or disturbances to    $r_{t}$  . If volatility    $\sigma$   is assumed to be independent of the short-term rate (e.g., it is a constant), the following defines the  Ornstein-Uhlenbeck

 (Uhlenbeck & Ornstein, 1930) mean reverting process, also known as a  Vasicek process

 (Vasicek, 1977) in fixed income analysis:  

$$
d r_{t}=\lambda(\bar{r}-r_{t})d t+\sigma d Z_{t}
$$  

The Ornstein-Uhlenbeck process is sometimes called an elastic random walk. The OrnsteinUhlenbeck process has two  onents, the mean reversion component    $\lambda(\overline{{r}}~-~r_{t})$   and the Brownian motion component  $\sigma d Z_{t}$  t . The Brownian motion component is the disturbance factor that causes the short-rate  $r_{t}$   to diverge from the long-term mean rate  $\bar{r}$  . The mean reversion component draws the short term rate  $r_{t}$   back towards the long term mean rate  r . A higher value for  $\lambda$   implies a faster reversion   $(\lambda<1)$   by the short-term rate  $r_{t}$   to the long term mean rate    $\bar{r}$  .  

If    $\lambda$   were zero, there would be no mean reversion and the process would be a Brownian motion. One drawback to the Vasicek interest rate model is that interest rate shifts have a normally distributed component, leading to the unfortunate result that it is possible for the interest rate to become negative. Obviously, this creates an arbitrage opportunity when cash is available for investors to hold.  Figure 8.2  depicts a simulation of a Vasicek process over length of time 200, with  $r_{0}=0.05,$  , and    $\sigma=0.02$   and    $\lambda=0.1$  . Also notice in  Figure 8.2 that the process can drop below zero.  

The Vasicek yield curve model has a number of desirable characteristics. The model captures the empirical tendency for interest rates to revert towards some sort of mean rate. The model is driven off short term interest rates, much as actual interest rates might be impacted by the Federal Funds rate, the “overnight” bank-to-bank controlled by the central bank (Fed). However, there are a number of problems with the Vasicek model in characterizing the behavior of the yield curve:  

1.  The Vasicek model is likely to apply only in reasonably “normal” scenarios. For example, in situations involving crises such as hyperinflation, mean reversion is not likely to characterize the behavior of interest rates.

 2.  Because it is based on Brownian motion, the Vasicek model does not allow for discrete jumps in the interest rate process.

 3.  The Vasicek model produces the result that all short- and long-term rate shifts over terms to maturity are perfectly correlated.  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/9b061e088f0376e15061cc2cdbe4279e9fd1f8d79a2bf8dd3d39526a151eedbb.jpg)  
FIGURE 8.2 Simulation of Vasicek process:  $r_{0}=0.05,$  ,  $\sigma=0.02$   and  $\lambda=0.1$  .  
4.  Related to the difficulty put forth just above, the Vasicek model assumes only a single underlying risk factor when, in fact, there is significant evidence that there may well be multiple factors. For example, sometimes the yield curve can “twist;” that is, long- and short-term rates can move in opposite directions. Multiple risk factors can often explain such “twisting.”  

5.  Finally, the Vasicek model allows for the possibility of negative interest rates, even for negative real interest rates, a phenomenon that we should expect to observe rarely, if at all. We discussed a solution to this problem earlier (Bartter and Rendleman), and will introduce the Cox-Ingersoll-Ross model shortly as an alternative.  

Why work with an interest rate model that presents all of these difficulties? As with most other financial models, we simply balance realism and ease of model building. The Vasicek model does capture some of the characteristics of a reasonable interest rate process and it is rather easy to work with, particularly in terms of parameter calibration. In addition, it is useful and sometimes very straightforward to adapt this framework into more realistic alternative depictions of interest rate processes.  

The “square root correction” in the Cox Ingersoll Ross Model (CIR:  Cox, Ingersoll, & Ross, 1985 ) eliminates the potential problem of negative interest rates in the mean reverting Vasicek model:  

ﬃﬃﬃﬃ 
$$
d r_{t}=\lambda(\overline{{r}}-r_{t})d t+\sigma_{r}\sqrt{r_{t}}d Z_{t}.
$$  

As in the Vasicek model, the mean reversion component draws the short-term rate back towards the long-term rate. However, notice that the nominal (not proportional) volatility of rates is not constant; it declines as the interest rate declines. That is, as the short term rate  $r_{t}$   approaches zero, the random component of interest rate changes    $\sigma{\sqrt{r_{t}}}d Z_{t}$  ﬃﬃﬃﬃ  will also approach zero. First, this characteristic is more realistic for interest rates, as the volatility of rates tends to be reduced as interest rates approach zero. Second, this process ensures that rates will not drop to or below zero, eliminating arbitrage opportunities for investors holding cash. Both represent advantages of CIR over the Vasicek model.  

# 8.5 ARBITRAGE WITH CURRENCIES  

Currency arbitrage can exist when currency prices are not consistent with respect to other currencies or with respect to goods or financial instruments in different countries. Thus, there exist many potential types of currency (foreign exchange or FX) arbitrage opportunities. Here, we discuss triangular arbitrage and absolute purchase power parity (PPP), scenarios that often do not require derivative securities to exploit. When no-arbitrage conditions force prices to retain consistency, triangular arbitrage and PPP can be used to hedge currency risk.  

# Triangular Arbitrage  

Triangular arbitrage  exploits the relative price difference between one currency and two other currencies. Suppose, for example, the buying and selling prices of EUR1.0 is USD1.2816. However, another currency, the South African Rand (SFR), has a price (buying or selling) equal to USD0.2000 or EUR0.1600. Is there a triangular arbitrage opportunity?  
There is if there is a price discrepancy for SFR in terms of USD and EUR. Note that the price of SFR in terms of both dollars and euro imply that 1 EUR is worth 1.25 USD:  

$$
\mathrm{SFR}1=\mathrm{USD0.2000}=\mathrm{EUC0.1600}
$$  

Since   $\mathrm{USD}0.20=\mathrm{EUC}0.16,$  , dividing both figures by 0.16 implies that  $\mathrm{USD}1.25=\mathrm{EUR}1.$  . But, this is inconsistent with the currency price information given above, which states that  $\mathrm{USD}1.2816=\mathrm{EUR}1.0$  . Even without knowing which pair of currencies is relatively mispriced, we can exploit an arbitrage opportunity taking advantage of the price in consist encies. So, we will start rather arbitrarily with one pair, the SFR and USD. In terms of the SFR, it appears that the USD is too strong relative to the EUR, so we will start by selling USD0.20 for SFR1 as per the price given above. We will cover the short position in USD by selling EUR0.16, which actually nets us   $0.16\times\mathrm{USD}1.2816=\mathrm{USD}0.2051.$   We will cover our short position in EUR by selling SFR at the price listed above. Positions from our three transactions are summarized and totaled in  Table 8.4 .  

Because of our price inconsistency, we will earn USD0.0051 every time that we execute this series of transactions. Existence of such arbitrage profits should be exploited by arbitrageurs, whose arbitrage transactions will ultimately force down the price SFR in terms of USD and force up the price of SFR in terms of EUR until the discrepancy is eliminated.  

# Purchase Power Parity, Arbitrage, and Hedging in FX Markets  

In a world economy characterized by free trade, complete certainty and no market frictions (such as transactions costs), we would expect that exchange rates will be regulated by  purchase power parity  (PPP). PPP is an example of the  law of one price , which simply states that securities offering the same cash flow characteristics or baskets offering the same commodities must sell for the same price. PPP states that the values of currencies relative to each other are determined by the quantity of goods they will purchase. This condition holds both in spot markets and forward markets (we will discuss forward markets in the next section). Currency traders creating arbitrage portfolios should force the PPP to hold. Violations of this parity condition should lead traders to purchase the less expensive currency sell the more expensive currency.  

One well-known (though somewhat tongue in cheek) test of PPP is the “Big Mac standard” popularized by  The Economist . MacDonald’s Corporation’s Big Mac hamburgers are generally regarded to be more or less identical all over the world. Given PPP, then the Big Mac should sell for the same price in each country. For example, suppose that the Big Mac cost   $\S4.60$   in a U.S. restaurant and costs  d 3.62 (GBP3.62) in the UK; Further suppose that  

TABLE 8.4 Triangular Arbitrage 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/54d96dc70a9883fa784e3610859fe9433020fbf94aa9ff7f943ab06aa4f8787e.jpg)  
the dollar/pound exchange rate is  $\S1.46/\mathfrak{L}$  ; that is, GBP1 has the same value as USD1.46. At this exchange rate of  $\S1.46/\xi,$  , the British pound appeared overvalued by approximately  $15\%$   relative to the U.S. dollar. However, we need to recognize that Big Macs are not easily exported from countries where they are under priced, which might prevent absolute PPP from holding in this instance. Nor does this relationship among prices account for differences in taxes, subsidies, labor, and other production costs.  

# Purchase Power Parity in Spot Markets  

Purchase power parity states that two commodities must sell for the same price (after adjusting for relative currency values). PPP is the primary basis for international comparisons of prices, income and expenditures. In spot markets, the price of a commodity in a foreign market (e.g.,  $P_{\mathrm{{UK0}}}$  —the price in the UK) multiplied by the exchange rate at present (  $\left.S_{0}\right.$  —the dollars per pound exchange rate) should equal the price of the commodity in domestic markets (e.g.,  $P_{\mathrm{US0}}$  —the price in the United States):  

$$
P_{\mathrm{US0}}=S_{0}\times P_{\mathrm{US0}}
$$  

This condition is known as PPP in spot markets or absolute PPP. In the absence of market frictions in both commodity and exchange markets, and with the ability to freely transport commodities between markets, the potential for arbitrage should force absolute PPP in spot markets to hold. For example, if the spot price of gold in U.S. markets is USD1400 per ounce and UK1000 in British markets, the spot exchange rate must be USD1.400/GBP (Great Britain Pounds). Any single deviation from these rates will lead to an arbitrage opportunity. We will discuss changes in exchange rates and forward markets for exchange in the next section.  

# 8.6 ARBITRAGE AND HEDGING WITH CURRENCYFORWARD CONTRACTS  

In friction less markets, currency arbitrage opportunities exist when forward currency exchange rates are inconsistent given prices of commodities or rates associated with financial instruments in different countries. Here, we will discuss triangular arbitrage in forward markets and relative PPP, scenarios that do require certain derivative securities.  

# Parity and Arbitrage in FX Markets  

In a world economy characterized by free trade, complete certainty, and no market frictions (such as transactions costs), we can argue that the following conditions will hold in equilibrium:  

1.  Purchase power parity (PPP)

 2.  Interest rate parity (IRP)

 3.  Forward rates equal expected spot rates

 4.  The Fisher effect

 5.  The international Fisher effect Collectively, these conditions are often referred to as the  international equilibrium model .  
Violations of these conditions imply either arbitrage opportunities or frictions that prevent the exploitation of arbitrage opportunities.  

# Purchase Power Parity  

We argued above that PPP states that two commodities must sell for the same price (after adjusting for relative currency values). In forward markets, as in spot markets, the price of a commodity in a foreign market (e.g.,    $P_{\mathrm{{UK1}}}$  —the forward price in the UK) multiplied by the forward exchange rate   $\scriptstyle{\mathcal{F}}_{1}.$  —the dollars per pound forward exchange rate) should equal the price of the commodity in domestic markets (e.g.,    $P_{\mathrm{US1}}$  —the forward price in the United States):  

$$
P_{\mathrm{US1}}=F_{\mathrm{1}}\times P_{\mathrm{US1}}
$$  

This condition is known as PPP in forward markets. In the absence of market frictions in both commodity and exchange markets, and with the ability to freely transport commodities between markets, the potential for arbitrage should force absolute PPP in spot or forward markets to hold.  

The combination of PPP conditions in both spot and forward markets leads to the  relative PPP  condition. Consider a basket of groceries in the United States, which costs   $20\;\mathrm{dol}.$  lars   $(P_{\mathrm{US0}}=\S20.00)$  ). Assume that the same basket of groceries can be purchased in the United Kingdom for 12.50 pounds   $(P_{\mathrm{UK}0}=£12.50)$  . Further assume that the exchange rate of dollars for British pounds   $(S_{0})$   is 1.6; that is, 1.6 dollars buys one pound. Purchase power parity holds here in the spot market, since an American can exchange 20 dollars for 12.5 pounds in the foreign exchange market and purchase the same basket of commodities as he could in the United States.  

If in one year, the price of the basket were to increase by  $10\%$   to USD22 (perhaps due to inflation) in the United States, and increase by   $8\%$   in the United Kingdom, what would we expect to see happen to the exchange rate of dollars for pounds   $(F_{1})?$   Recall that the PPP Theorem states that the same basket of commodities must cost the same in any two economies, given relevant exchange rates. Furthermore, changes in price levels in one economy will be matched by either offsetting changes in its currency value (exchange rates), changes in prices in the second economy, or some combination of the two. Thus, since the price of goods in the United States increased by   $10\%$   and the price of goods in the United Kingdom increased by   $8\%$  , the exchange rate should increase by   $1.8512\%$   to 1.6296 dollars for one pound   $(F_{1}=1.6296)$  ). Thus, the change in the exchange rate   $(\Delta S)$   under PPP must be:  

$$
\Delta S=\frac{F_{1}}{S_{0}}-1=\frac{1.6296}{1.6000}-1=\frac{P_{\mathrm{US1}}/P_{\mathrm{US0}}}{P_{\mathrm{US1}}/P_{\mathrm{US0}}}-1=\frac{22.00/20.00}{13.50/12.50}-1=0.01851.
$$  

Note that the country with the higher inflation rate will have its currency devalued relative to the country with the lower inflation rate. More generally, if   $(\pi_{\mathrm{{US}}})$   represents the U.S. inflation rate and   $(\pi_{\mathrm{HK}})$   represents the UK inflation rate, then the following holds:  

$$
\frac{(1+\pi_{\mathrm{US}})}{(1+\pi_{\mathrm{US}})}=\frac{F_{1}}{S_{0}}
$$  
Equation 8.23  is the general mathematical definition or statement of PPP. It provides the relationship between forward and spot rates of exchange as a function of relative inflation rates in relevant countries.  

# Example 1: Purchase Power Parity Violation and Arbitrage  

Consider the following violation of PPP. The exchange rates of dollars for pounds are 1.6000 and 1.6296 in the spot and one-year forward markets, respectively. Assume that gold is selling for   $\S400$   per ounce in American spot markets and for  d 250 in British spot markets. The one-year forward price of gold is   $\S440$   in American markets and    $£280$   in British markets. We might wish to assume that inflation rates in the United States and the UK are, respectively,  $10\%$   and   $12\%$  . In this case, we should be able to demonstrate an arbitrage opportunity. Consider the following transactions in forward markets (future prices are locked in now by taking positions in forward contracts):  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/06e707f8001f8dff46eda20a4ae5cf1160f3cc253cfca6abac53d0c8488ee23d.jpg)  

Because all prices are locked in by spot and forward contracts, we are able to lock in a profit of  d 10 by engaging the above transactions. The change in exchange rates does not coincide appropriately with the countries’ relative gold price changes. You should be able to demonstrate for yourself that  Equation (8.23)  does not hold for this example. Whenever Equation (8.23)  does not hold, we should either be able to exploit an arbitrage opportunity or identify a constraining market friction.  

How do we know that we should purchase gold in the United States at time one? Consider the following:  

$$
\frac{(1+\pi_{\mathrm{US}})}{(1+\pi_{\mathrm{US}})}=\frac{(1+0.10)}{(1+0.12)}<\frac{F_{1}}{S_{0}}=\frac{1.6296}{1.6}
$$  

The forward price of the pound   $(\S1.6296)$   increased relative to the dollar while the inflation rate affecting the dollar is less than for the pound. This means that the forward price of gold in the United States is too low relative to the  $\mathrm{{UK},}$   the forward price of gold in the UK is too high relative to the United States, and the forward price of pounds is too high relative to dollars.  
# Interest Rate Parity  

Interest rate parity  states that anticipated currency exchange rate shifts will be proportional to countries’ relative interest rates. Continuing the above example, assume that the current nominal interest rate in the United States is   $12\%.$  , and the spot exchange rate of dollars for pounds is 1.6. Based on these rates, what must be the nominal interest rate in the UK? To avoid arbitrage opportunities in the market for interest bearing securities, interest rate parity must hold:  

$$
\frac{(1+i_{\mathrm{US}})}{(1+i_{\mathrm{UK}})}=\frac{F_{\mathrm{1}}}{S_{\mathrm{0}}}=\frac{(1+0.12)}{(1+i_{\mathrm{UK}})}=\frac{1.6296}{1.600}
$$  

Thus, the interest rate in the UK must be   $9.9636\%$  . If the British interest rate were lower, arb it ra gers would borrow at the lower British rate, exchange pounds for dollars, and then loan at the higher American interest rate. Thus, interest rate parity holds that a strategy of borrowing money in one currency, immediately exchanging that currency for a second that is immediately loaned, will enable the investor to break even on the loans if futures contracts are used to lock in future exchange rates.  

# Example 2: Interest Rate Parity Violation and Arbitrage  

Here, we continue to assume that exchange rates of dollars for pounds are 1.6 and 1.6296 in the spot and one-year forward markets, respectively. Assume that nominal interest rates are   $12.5\%$   in the United States and  $12\%$   in the United Kingdom. Again, we should be able to demonstrate an arbitrage opportunity. Consider the following transactions in markets for interest bearing securities and forward exchange (forward prices are locked in now by contracts):  

Time Zero Positions 
 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c42aca73a558579b7d5399d08e70836db66c80a63e7e685578da84dfe885cd52.jpg)  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/c66c4bf35289990f7c6af2e37ff34aa8d7e7cd0c231f73ee961f802129614c09.jpg)  
Time One Positions  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/efc91946c6e3b3e7e887b27c335db49752fd0a85890f0680a92aeb1713cd41ed.jpg)  

Here, we are able to lock in a profit of  $\S15.74$   by engaging the above transactions. The change in exchange rates did not coincide appropriately with the countries’ relative interest rates. You should be able to demonstrate for yourself that  Equation (8.24)  does not hold for this example. Whenever  Equation (8.24)  does not hold, we will be able to locate an arbitrage opportunity or a friction that prevents its exploitation.  

# Exchange Rate Expectations  

The third of the four parity relations states that the prevailing forward rate of exchange equals the expected spot rate at the time of delivery:  

$$
F_{1}=E[S_{1}]
$$  

Speculators will force  Equation (8.26)  to hold, at least approximately, through their trading activity. However, its violation does not necessarily represent an arbitrage opportunity.  

# The Fisher Effect  

The  Fisher effect  within a given country states that the relationships among the nominal interest rate   $(i)$  , the real interest rate   $(i^{\prime})$   and the expected inflation rate    $E(\pi)$   are given by Equation (8.27) :  

$$
(1+i)=(1+i^{\prime})(1+E(\uppi))
$$  

The Fisher effect provides a definition for the real rate  $i^{\prime}$    of interest in an economy in terms of the nominal rate  $i$   and the inflation rate    $\pi$  .  Equation (8.27)  provides a definition, but does not necessarily indicate an arbitrage opportunity.  

# The International Fisher Effect  

The international counterpart to the Fisher effect is the final parity condition—the  international Fisher effect . The international Fisher effect draws from the Fisher effect and purchase and interest rate parity. For example, the following states the international fisher effect for the United States, the United Kingdom:  

$$
\frac{(1+i_{\mathrm{US}})}{(1+i_{\mathrm{UK}})}=\frac{(1+E[\pi_{\mathrm{US}}])}{(1+E[\pi_{\mathrm{UK}}])}\times\frac{(1+i_{\mathrm{US}}^{\prime})}{(1+i_{\mathrm{UK}}^{\prime})}
$$  
Thus, the Fisher effect specifies the relationships among real and nominal interest rates and inflation rates. The international Fisher effect extends this relation among countries, indicating that real interest rates among countries will be identical. If this condition were not to hold, arb it rage urs would borrow in countries with low real interest rates and lend in countries with higher nominal interest rates. Alternatively, they might be able to exploit arbitrage opportunities arising from violations in PPP. Please take time to notice the relationships among  Equation (8.23) through (8.28)  and how additional equalities can be created from them.  

# 8.7 HEDGING EXCHANGE EXPOSURE  

Multinational companies face a number of risks not experienced by companies operating in only one country. Among the most significant of these risks is exchange rate uncertainty and fluctuations. Transaction exposure is a firm’s risk arising from settlement of obligations denominated in foreign currencies. The following are sources of transaction exposure:  

1.  Purchasing or selling goods or services on foreign-denominated credit

 2.  Borrowing or lending with foreign-denominated notes

 3.  Taking positions in forward exchange contracts

 4.  Buying or selling assets denominated in foreign currencies  

The corporate treasurer is responsible for managing these risks. The treasurer will either employ traders or engage agency traders to take exchange and derivative positions to manage these risks. The following are strategies that treasurers and traders employ to contend with transactions exposure:  

1.  Do nothing—accept the risk

 2.  Hedge in forward markets

 3.  Hedge in money markets: take offsetting position in local currency debt instruments

 4.  Hedge in option markets: incomplete hedge with puts or complete hedge with conversions  

We use illustrations to examine the first three of these strategies for dealing with transactions exposure. We will discuss the options strategies in the next chapter.  

# Illustration: Managing Transactions Exposure  

Consider an example regarding the management of transactions exposure. The Dayton Company of America invested in a British construction project and expects to receive a payoff of  d 1,000,000 in three months. The company seeks to realize its revenues in dollars. The problem is that management does not know the dollar amount of the payoff due to exchange rate uncertainty. Assume relevant data as follows:  

Spot exchange rate:   $\mathbb{S}1.7640/\mathfrak{E}$  Three-month forward exchange rate:   $\Updownarrow1.7540/\updownarrow$  UK borrowing interest rate:   $10.0\%$  
U.S. borrowing interest rate:  $8.0\%$  UK lending interest rate:   $8.0\%$  U.S. lending interest rate:   $6.0\%$  Forward contract settlement price:  $\S1.75$   per  d Transactions cost on  d 1,000,000 forward contract:  $\S500$  

The treasurer’s problem is to evaluate non-options  based methods of managing the transaction risk associated with this extension of credit and the implications of each. We will determine which hedging strategy is likely to be optimal and why. First, we consider the alternative of doing nothing.  

# Unhedged Alternative  

The unhedged alternative simply means to accept the risk. The strategy is simply to wait 3 months, then sell  d 1,000,000 for dollars at the then prevailing spot rate. The result of this strategy is that all  d 1,000,000 is at risk. The expected value of the transaction is  $\mathbb{S}1{,}754{,}000$   based on the forward rate of exchange used as a predictor for the future spot rate. However, all funds are at risk.  

# Forward Market Hedge  

The  forward market hedge  strategy is to sell  d 1,000,000 forward for dollars at once. The result is that, in the absence of default risk,  $\S1,754,000$   will certainly be received in three months. Transactions costs at time zero will total  $\S500$  . Forgone interest on this  $\S500$   over three months totals   $\S7.50=0.06\times0.25\times\S500$  . The total amount (net of forgone interest) to be received in three months is   $\S1,753,492.50$  . This amount is certain.  

# Money Market hedge  

The  money market hedge  strategy is to borrow  d 975,609.76 in UK for three months at an annual rate of   $10\%$  , exchange the  d 975,609.76 for   $\S1,720,975.60$   now at the spot exchange rate, and then invest  $\S1,720,975.60$   for three months at an annual rate of  $6\%$  . The result of this strategy is that the UK pound loan is repaid by receipts from sale in three months.  $\S1,746,790.{\bar{20}}$   is obtained from the U.S. investment. This amount is certain in the absence of default risk. Note that this strategy in this example is inferior to the forward market hedge.  

# Other Hedging Strategies  

The hedging strategies described in the above examples and in the next chapter are more effective when firms can easily enter into forward, money market and options contracts. This is normally quite easily accomplished in countries with major currencies. However, in many instances, firms will need to hedge exchange rate volatility in countries where such opportunities are not available. For example, it is often very difficult to employ the above strategies in smaller African, Asian, or Latin American countries. In many instances, firms might modify these strategies with cross-hedges. Typically, these crosshedging strategies involve the use of contracts denominated in currencies strongly correlated with the currency to be hedged. For example, rather than attempt to directly hedge exchange rate risk involving Philippine pesos, a firm might use contracts denominated in yen, which are fairly highly correlated with pesos. An alternative cross hedging strategy is to hedge currency risk with commodity contracts whose values are strongly correlated with that of the currency. For example, the price of oil is strongly correlated with the value of the Saudi Arabia riyal (SAR). The firm needing to hedge risk associated with the riyal can use futures contracts on oil as an imperfect substitute for the currency itself.  
# Additional Reading  

Elton, Gruber, Brown, and Goetzmann (2010) , Chapters 21 and 22, offer good coverage of yield curves, fixed income arbitrage, and hedging.  Knopf and Teall (2015)  offer a somewhat more detailed introduction to much of the fixed-income-related material in this chapter, as does Chapter 18 in  Neftci (2000) , which extends material in this chapter to continuous time. Chapters 1 through 6 in Neftci comprise good background reading for Chapter 18.  Shapiro (2006)  and  Grabbe (1996)  discuss parity conditions along with currency exposure and hedging. Chapter 9 in  Saunders and Cornett (2009)  provides a concise overview of FX markets, instruments and analysis.  

# References  

Cox, J., Ingersoll, J., & Ross, S. (1985). A theory of the term structure of interest rates.  Econometric a ,  53 , 385  408. Elton, E., Gruber, M., Brown, S., & Goetzmann, W. (2010).  Modern portfolio theory and investment analysis  (8th ed.). New York: Wiley. Grabbe, J. O. (1996).  International financial markets  (3rd ed). Englewood Cliffs, NJ: Prentice Hall. Knopf, P., & Teall, J. L. (2015).  Risk neutral pricing and financial mathematics: A primer . San Diego: Academic Press. Merton, R. C. (1973). Theory of rational option pricing.  Bell Journal of Economics and Management Science ,  4 (1), 141  183. Neftci, S. N. (2000).  An introduction to the mathematics of financial derivatives  (2nd ed). San Diego: Academic Press. Rendleman, R. J., Jr., & Bartter, B. J. (1980). The pricing of options on debt securities.  Journal of Financial and Quantitative Analysis ,  15 (1), 11  24. Saunders, A., & Cornett, M. M. (2009).  Financial markets and institutions: A modern perspective . Irwin, Boston: McGraw-Hill. Shapiro, A. C. (2006).  Multinational financial management  (8th ed). New York: Wiley. Uhlenbeck, G. E., & Ornstein, L. S. (1930). On the theory of Brownian motion.  Physics Review ,  36 , 823  841. Vasicek, O. (1977). An equilibrium characterization of the term structure.  Journal of Financial Economics ,  5 , 177  188.  

# 8.8 EXERCISES  

1.  There are two three-year bonds with face values equaling  $\mathbb{S}1000$  . The coupon rate of bond A is 0.05 and 0.08 for bond B. A third bond  $\mathsf C$   also exists, with a maturity of two years. Bond C also has a face value of   $\mathbb{S}1000$  ; it has a coupon rate of  $11\%$  . The prices of the three bonds are  $\S878.9172$  ,  $\S955.4787.$  , and  $\Updownarrow1055.419$  , respectively. Find a portfolio of bonds A, B, and C that would replicate the cash flow structure of bond D, which has a face value of   $\mathbb{S}1000,$  , a maturity of three years, and a coupon rate of   $3\%$  .

 2.  A  $\mathbb{S}1000$   face value bond is currently selling at a premium for   $\mathbb{S}1200$  . The coupon rate of this bond is  $12\%$   and it matures in three years. Calculate the following for this bond assuming that its interest payments are made annually: a.  Annual interest payments b.  Current yield c.  Yield to maturity  
3.  Work through each of the calculations in Problem 2 assuming that interest payments are made semi annually.  

4.  A life insurance company expects to make payments of  $\S30{,}000{,}000$   in one year,  $\mathbb{S}15{,}000{,}000$   in two years,   $\S25{,}000{,}000$   in three years, and  $\S35{,}000{,}000$   in four years to satisfy claims of policyholders. These anticipated cash flows are to be matched with a portfolio of the following  $\mathbb{S}1000$   face value bonds:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/785868a49438afb966256c769770fa2d0cf5063eaa1df31d821905f8e3b403b2.jpg)  

How many of each of the four bonds should the company purchase to exactly match its anticipated payments to policyholders?  

Find the duration of the following pure discount bonds: a.    $\mathbb{S}1000$   face value bond maturing in one year currently selling for  $\S900$  b.    $\mathbb{S}1000$   face value bond maturing in two years currently selling for   $\S800$  c.    $\S2000$   face value bond maturing in three years currently selling for  $\S1400$  d.  Portfolio consisting of one of each of the three bonds listed in parts a,  $^\mathrm{b,}$   and c of this problem  

6.  What is the relationship between the maturity of a pure discount bond and its duration?  

7.  Find the duration of each of the following  $\mathbb{S}1000$   face value coupon bonds assuming coupon payments are made annually:  

a.  Three-year  $10\%$   bond currently selling for   $\S900$  b.  Three-year  $12\%$   bond currently selling for   $\S900$  c.  Four-year   $10\%$   bond currently selling for  $\S900$  d.  Three-year  $10\%$   bond currently selling for   $\S800$  

8.  Based on duration computations, what would happen to the prices of each of the bonds in Question 7 if market interest rates   $(1+r)$   were to decrease by   $10\%:$  ?  

9.  What is the duration of a portfolio consisting of one of each of the bonds listed in problem 7?  

10.  Find durations and convex i ties for each of the following bonds:  

a.    $10\%$   five-year bond selling for  $\S1079.8542$   yielding  $8\%$  b.    $12\%$   five-year bond selling for  $\mathbb{S}1000$   yielding   $12\%$  

11. a.  Use the duration (first-order) approximation models to estimate bond value increases induced by changes in interest rates (yields) to  $10\%$   for each of the bonds in Problem 10 above. b.  Use the convexity (second-order) approximation models to estimate bond value increases induced by changes in interest rates (yields) to  $10\%$   for each of the bonds in Problem 10 above.  
c.  Find the present values of each of the bonds in Problem 10 above after yields (discount rates) change to  $10\%$  .  

12.  Consider an example where we can borrow money today for one year at  $5\%$  ;  $y_{0,1}=0.05$  . Suppose that we are able to obtain a commitment to obtain a one-year loan one year from now at an interest rate of  $8\%$  . Thus, the one-year forward rate on a loan originated in year equals  $8\%$  . According to the pure expectations theory, what is the two-year spot rate of interest  $y_{0,2}^{}\prime$  ?  

13.  Suppose that the one-year spot rate  $y_{0,1}$   of interest is  $5\%$  . Investors are expecting that the one-year spot rate one year from now will increase to  $6\%$  ; thus, the one-year forward rate  $y_{1,2}$   on a loan originated in one year is   $6\%$  . Furthermore, assume that investors are expecting that the one-year spot rate two years from now will increase to  $7\%$  ; thus, the one-year forward rate  $y_{2,3}$   on a loan originated in two years is   $7\%$  . Based on the pure expectations hypothesis, what is the three-year spot rate?  

14.  Suppose that the one-year spot rate  $y_{0,1}$   of interest is  $5\%$  . Investors are expecting that the one-year spot rate one year from now will increase to  $7\%$  ; thus, the one-year forward rate  $y_{1,2}$   on a loan originated in one year is   $7\%$  . Furthermore, assume that the three-year spot rate equals   $7\%$   as well. What is the anticipated one-year forward rate  $y_{2,3}$   on a loan originated in two years based on the pure expectations hypothesis?  

15.  Consider the following four bonds:  

 ![500](https://cdn-mineru.openxlab.org.cn/model-mineru/prod/cc37a49f2b0b35679f452e711fa857ab684331e0ddb3caa26000fa36de71af95.jpg)  

Based on the cash flows and prices associated with these bonds, determine the following:  

a.  Spot rates  $y_{0,n}$   for each of four years 1 through 4. These are interest rates on loans originating at time 0. b.  Forward rates  $y_{1,t}$   for each of three periods beginning with year 1. These are interest rates on loans originating at time 1. c.  Forward rates  $y_{2,t}$   for each of two periods beginning with year 2. These are interest rates on loans originating at time 2. d.  Forward rates  $y_{3,n}$   for the period beginning with year 3. This is the interest rates on loans originating at time 3.  

16.  Bond  $\mathrm{A},$  , a three-year  $7\%$   issue, currently sells for 964.3227. Bond B is a two-year   $8\%$  issue currently selling for 1010.031. Bond C is a three-year  $6\%$   issue currently selling for 938.4063. Based on this information, answer the following:  

a.  What are the one-, two-, and three-year spot rates of interest? b.  What are the one- and two-year forward rates on loans originating one year from now? c.  What is the one-year forward rate on a loan originated in two years?  
17.  Assume that there are two three-year bonds with face values equaling  $\mathbb{S}1000$  . The coupon rate of Bond A is 0.05 and 0.08 for Bond B. A third Bond C also exists, with a maturity of two years. Bond C also has a face value of  $\mathbb{S}1000,$  ; it has a coupon rate of  

$11\%$  . The prices of the three bonds are  $\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \$  ,  $\S955.4787.$  , and  $\mathbb{S}1055.419$  , respectively. a.  What are the spot rates implied by these bonds? b.  Find a portfolio of Bonds A, B, and C which would replicate the cash flow structure of Bond D, which has a face value of   $\S1000$  , a maturity of three years, and a coupon  $3\%$  rate of  .  

18.  Suppose we expected that PPP should hold between the United States and Canada. Assume that the exchange rate between U.S. dollars and Canadian dollars is CAD1/ USD0.64. That is, one Canadian dollar will purchase USD0.64. If USD2.30 purchases one Big Mac in the United States, how much should a Big Mac cost in Canada?  

19.  Consider a case involving three currencies concerning cross rates of exchange. Assume that 1.5 Swiss francs are required to purchase 1 U.S. dollar and that 0.64 U.S. dollars are required to purchase 1 Canadian dollar. a.  How many Canadian dollars are required to purchase 10 Swiss francs? b.  Assuming that PPP holds, how many Swiss francs are required to purchase one Big Mac?  

20.  Assume that  $\S1$   will purchase    $£0.60$   and  f 108; that is, 1 U.S. dollar will purchase 0.6 UK pounds and 108 Japanese yen. Assume that goods in the three countries are identically priced after adjusting for currency exchange rates. a.  What is the value of  d 1 in  f ? b.  What is the value of  f 1 in  d ? c.  If one ounce of gold costs   $\S300$   in the United States, what is its cost in the United Kingdom and in Japan?  

21.  Consider the following exercise concerned with management of transactions exposure. The Smedley Company has sold products to a Japanese client for  f 15,000,000. Payment is due six months later. Relevant data is as follows:  

Spot exchange rate:  $\Psi105/\Phi$  Six-month forward exchange rate:    $\mathfrak{F}104/\mathfrak{F}$  Japanese borrowing interest rate:  $9.0\%$  U.S. borrowing interest rate:  $7.0\%$  Japanese lending interest rate:  $7.0\%$  U.S. lending interest rate:  $5.0\%$  Size of futures contracts:  f 1,000,000 Term to settlement of contracts: six months Transactions cost on  f 15,000,000 forward contract:   $\S500$  Discuss the implications associated with each of the non-options  based methods for managing the transactions exposure risk associated with this extension of credit. Determine which hedging strategy is likely to be optimal and why.  
