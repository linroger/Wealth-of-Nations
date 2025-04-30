---
tags:
  - duration
  - dv01
  - interest_rate_risk
  - modified_duration
  - yield_curve
aliases:
  - Basis Point Value
  - Dollar Duration
  - PV01
key_concepts:
  - Key rate durations
  - Modified duration
  - Partial DV01s
  - Price sensitivity measurement
  - Yield curve risk
---

# A Guide to Duration, DV01, and Yield Curve Risk Transformations  

Originally titled "Yield Curve Partial Dv01s and Risk Transformations"  

Thomas S. Coleman Close Mountain Advisors LLC  

15 January 2011  

Duration and Dv01 (dollar duration) measure price sensitivity and provide the basic risk measure for bonds, swaps, and other fixed income instruments. When valuing. instruments off a yield curve, duration and Dv01 naturally extend to a vector of partial. DV01s or durations (key rate durations) and these are widely used in the finance. industry. But partial Dv01s or durations can be measured with respect to different. rates: forwards, par rates, zero yields, or others. This paper reviews the concepts of partial Dv01 and duration and then discusses a simple method for transforming partial DVO1s between different rate bases and provides examples. The benefit of this transformation method is that it only requires calculating the risk of a small set of. alternate instrument and does not require re-calculating the original portfolio risk.. (This paper is also available in an interactive version with enhanced digital content - see. references.)  

Keywords: Dvo1, Duration, Key Rate Duration, Interest Rate Risk, Yield Curve Risk,   
Dollar Duration, Modified Duration, Partial DV01   
JEL Classifications: G10, G12, E43  

# Paper  

# Introduction  

Duration and Dv01 provide the basic measures for evaluating the risk or sensitivity of fixed income instruments and are both used throughout the financial industry. The Dv01 (dollar value of an 01) is just the derivative of price with respect to yield:.  

$$
P r i c e=P V(\mathrm{y})D V O I=-\frac{d P V}{d\mathrm{y}}
$$  

Modified or adjusted duration, the derivative in percentage instead of dollar terms, is just the Dv01 expressed in different units:  

$$
{\mathrm{Modified~or~}}{\mathrm{Adjusted~Duration}}=-{\frac{1}{P V}}{\frac{d{\cal P}V}{d~y}}=100\cdot{\frac{D V O I}{{\cal P}V}} 
$$  

One can use either Dv01 or modified duration and the choice between them is largely a matter of convenience, taste, and custom. Dv01, also called dollar duration, PV01 (present value of an O1), or BPV (basis point value), measures the derivative in price terms: the dollar price change per change in yield. Modified duration measures the derivative in percent terms: the. percent price change per change in yield. I will work mostly with Dv01 throughout this paper but the ideas can be applied. equally well to modified duration.  

In many practical applications a bond or other fixed-income security will be valued off a yield curve, and we can then extend the Dv01 or duration to partial Dv01s or durations - the partial derivatives with respect to yields for different parts of the cur ve:  

$$
\mathrm{{Partial~}}D V O I\mathrm{{s}}=\left(\begin{array}{c c c}{{\frac{\partial P V}{\partial y_{1}}}}&{{\dots}}&{{\frac{\partial P V}{\partial y_{k}}}}\end{array}\right)
$$  

Calculating and using partial Dv01s based on a curve is a natural extension of the basic yield Dv01, just as partial derivatives are a natural extension of the univariate derivative. Partial Dv01s of one form or another are used throughout the financial industry (see Ho 1992 and Reitano 1991 for early discussions). Unlike for the basic Dv01, however, when working with a full. yield curve there is no single unique yield. Partial Dv01s can be calculated with respect to any of a large set of possible yields. The values for the partial Dv01s will depend on the set of rates used. Partial Dv01s w.r.t. alternate yields all measure the same. thing - risk to parts of the curve - but do so from different perspectives. As a result, we often need to transform between partial Dv01s w.r.t. alternate yields.  

Let us turn to an example. Say we have a 10 year zero bond trading at $\$70.26$ or $3.561\%$ semi-bond yield. The DV01 will be.  

$$
D V O I_{s a b}=-{\frac{d P V}{d y_{\mathrm{sab}}}}=6.903
$$  

(measured here as the price change for a $\$100$ notional bond per 100bp or 1 percentage point change in yield). The modifie. duration will be  

$$
M o d D=100\cdot{\frac{6.903}{70.26}}=9.83
$$  

(measured as the percent change per 1 percentage point change in yield). For the bond there is a single yield-to-maturity, so little choice in defining the Dv01 or duration..  

When we turn to valuation using a curve, however, there are many choices for the yields in defining the partial Dv01s. Say that we restrict ourselves to a curve built with instruments of maturity 1, 2, 5, and 10 years. The exact meaning of "parts of the curve" is discussed more below, but for this curve we would use instruments with maturity 1, 2, 5, and 10 years. A natural choice, but by no means unique, would be to work with zero-coupon yields of maturity 1, 2, 5, and 10 years. For our 10 year zero the partial Dv01s w.r.t. zero rates would be:  

<html><body><table><tr><td></td><td>10-year</td><td>Zero</td><td>Bond</td><td>Zero</td><td>Yield</td><td>Partial</td><td>DV01</td></tr><tr><td>lyr</td><td>Zero</td><td>2yr</td><td>Zero</td><td>5yr</td><td>Zero</td><td>10yr Zero</td><td>Total</td></tr><tr><td>0.</td><td></td><td>0.</td><td></td><td>0.</td><td></td><td>6.904</td><td>6.904</td></tr></table></body></html>  

The partial Dv01 w.r.t. the 10 year yield is the same as the original Dvo1, and all the other partials are zero. This should not be a surprise.  

Zero yields are a common choice for partial Dv01 yields but might not be suitable for all circumstances and are by no means the only choice. We could instead calculate partial Dv01s w.r.t. forwards - using our curve this would be forward rates between 0, 1, 2, 5, and 10 years. For our zero bond the forward rate partial Dv01s would be:  

<html><body><table><tr><td>10-year</td><td>Zero</td><td>Bond</td><td>Forward</td><td>Rate</td><td>Partial</td><td>DV01</td></tr><tr><td>1 yr Zero</td><td>2yr</td><td>Zero</td><td>5yr Zero</td><td>10yr</td><td>Zero</td><td>Total</td></tr><tr><td>0.702</td><td></td><td>0.702</td><td>2.109</td><td></td><td>3.513</td><td>7.027</td></tr></table></body></html>  

This is the same risk as we originally calculated, just measured using alternative instruments - forward rates instead of zero rates. If we were trading options then we would be particularly interested in forward rates and risk expressed in this way might be more useful than the risk w.r.t. zero rates.  

We are not limited to zeros or forwards. We could equally well calculate the risk w.r.t. yields on par bonds:  

<html><body><table><tr><td>10-year</td><td>Zero</td><td>Bond</td><td>Par</td><td>Yield</td><td>Partial</td><td>DV01</td></tr><tr><td>1 yr Zero</td><td>2yr</td><td>Zero</td><td>5yr</td><td>Zero</td><td>10yr Zero</td><td>Total</td></tr><tr><td>-0.026</td><td></td><td>-0.105</td><td>-0.54</td><td></td><td>7.597</td><td>6.926</td></tr></table></body></html>  

The exact numbers, both the distribution across the curve and the total (a "parallel' shift of. $100\mathrm{bp}$ in all yields) are different in all cases. Nonetheless the risk is the same in all three cases, simply expressed in different units or different co-ordinates - essentially transformed from one set of rates or instrument to another.  

Usually we start with risk in one representation or in one basis, dependent on the particular risk system we are using, but often we want to examine the partial Dv01s w.r.t. another set of yields. We might be given the partials w.r.t. forwards but wish to see the partial Dv01s w.r.t. par yields. We would need to transform from the forward basis to the par basis. This. paper describes a simple methodology for transforming between alternate sets of rates or instruments. The essence of the approach is:  

Start with partial Dvo1s for the original security or portfolio calculated in one representation, usually based on the risk system used and particular functional form used to build the curve.   
Pick a set of instruments that represent the alternate yields or rates desired for the partial Dv01s. For example if we wish to transform to zero-coupon yields, choose a set of zero-coupon bonds.   
Perform an auxiliary risk calculation for this set of alternate instruments to obtain partial derivatives, reported on the same basis as the original risk.   
Use this matrix of partial derivatives to create a transformation matrix, and transform from the original partial Dv01s to the new partial DV01s by a simple matrix multiplication.  

The matrix provides a quick, computationally efficient way to transform from the original risk to the new risk, essentially a basis or coordinate transformation. The benefit of this transformation approach is that it does not require re-calculating the original portfolio risk. The auxiliary risk calculation for the set of alternate instruments will generally be quick, involving valuation of a handful of plain-vanilla instruments.  

We can even take the idea one step further. The process above assumes the same number of new rates as old, but we may wish to view the partial Dv01s with respect to a reduced set of rates. In our example we might wish to remove the 2 year swap and measure risk w.r.t. the 1, 5, and 10 year par swap yields:.  

<html><body><table><tr><td>10-year</td><td>Zero</td><td>Bond</td><td>Zero</td><td>Yield</td><td>Partial DV01</td></tr><tr><td>1 yr Swap</td><td>5yr</td><td>Swap</td><td>10yr</td><td>Swap</td><td>Total</td></tr><tr><td>-0.065</td><td></td><td>-0.606</td><td></td><td>7.597</td><td>6.926</td></tr></table></body></html>  

To do this requires building a new curve with a reduced set of market instruments, and then two auxiliary risk calculations - a set of instruments using the old curve and the same set of instruments using the new curve. Once again, this is computationally inexpensive since the original portfolio does not need to be revalued using the new curve.  

# Review of Duration and DV01  

Duration and Dv01 are the foundation for virtually all fixed income risk analysis. The ideas are well-known but it will prove useful to review the basic concepts. The duration we are concerned with is modified duration, the semi-elasticity, percentage price sensitivity or logarithmic derivative of price with respect to yield:  

$$
{\mathrm{Modified~or~Adjusted~Duration}}=-{\frac{1}{V}}{\frac{d V}{d y}}=-{\frac{d{l n}V}{d y}}
$$  

he name duration originated with Frederick Macaulay (1938) and his definition of duration as the weighted average maturity f cash flows, using the present value of cash flows as weights:  

$$
\mathrm{{Macaulay~Duration}}=\sum_{i=1}^{n}t_{i}{\frac{P V_{i}}{V}}
$$  

Macaulay duration applies to instruments with fixed cash flows (. $t_{i}$ is the maturity of cash flow i,. $P V_{i}$ is the present value of. cash flow $i$ , and $V$ is the sum of all. $P V\mathrm{s}$ ). Macaulay duration is a measure of time or maturity (hence the name "duration"),. and is measured in years. This is in contrast to modified duration, which is a rate of change of price w.r.t. yield and is measured as percent per unit change in yield.  

The shared use of the term "duration" for both a maturity measure and a price sensitivity measure causes endless confusion. but is deeply embedded in the finance profession. The shared use of the term arises because Macaulay duration and modi-. fied duration have the same numerical value when yield-to-maturity is expressed continuously-compounded. For a flat yieldto-maturity and continuously-compounded rates the sum of present values is:.  

$$
{\cal V}=\sum_{i\mathop{=}1}^{n}{\cal P}{\cal V}_{i}=\sum_{i\mathop{=}1}^{n}C{\cal F}_{i}\cdot e^{-t i\cdot y}
$$  

Taking the logarithmic derivative w.r.t. $y$ gives:  

$$
M o d D=-{\frac{1}{V}}{\frac{d V}{d y}}=\sum_{i=1}^{n}t_{i}{\frac{C F_{i}\cdot e^{-t i\cdot y}}{V}}
$$  

But note that the term $\frac{C F_{i}\cdot e^{\mathrm{~-~}t i\cdot y}}{\l_{V}}$ is just - $\frac{P V_{i}}{\mathrm{~}_{V}}$ so that this is also the formula for Macaulay duration, and so modified duration and Macaulay duration have the same numerical value.  

1 the more common situation where rates are quoted periodically-compounded, then the sum of present values will be:  

$$
V=\sum_{i=1}^{n}P V_{i}=\sum_{i=1}^{n}{\cfrac{C F_{i}}{(\ 1+y/k)^{k\cdot t i}}}
$$  

where $k$ is the compounding frequency (e.g. 1 for annual, 2 for semi-annual). Taking the logarithmic derivative in this case gives:  

$$
M o d D=-\frac{1}{V}\frac{d V}{d y}=\sum_{i=1}^{n}t_{i}\frac{1}{V}\frac{C F_{i}}{\left(1+y/k\right)^{k\cdot t i}}\frac{1}{\left(1+y/k\right)}
$$  

This can be written as  

$$
M o d D=\sum_{i=1}^{n}t_{i}\frac{P V_{i}}{\mathrm{~\large~V~}}\frac{1}{\mathrm{~\large~\left(~1~+~y~/~k~\right)~}}
$$  

which gives the oft-quoted relation:  

$$
M o d D=\frac{M a c D}{(1+y/k)}
$$  

It is vitally important to remember, however, that this expresses a relationship between the values of modified and Macaulay. duration (for fixed cash flow instruments such as bonds) but that the two measures are conceptually distinct in spite of. sharing the name. Macaulay duration is a measure of time, denoted in years. Modified duration is a rate of change, percentage change in price per unit change in yield. Macaulay duration is limited in application to instruments with fixed cash flows (such as standard bonds) while modified duration can be applied to more general fixed-income instruments such as options..  

When we turn to Dv01 we calculate the dollar (rather than percentage) change in price with respect to yield:  

$$
D V O I~=~-{\frac{d~V}{d~y}}~
$$  

DV01 is also called dollar duration, BPV (basis point value), or PV01 (present value of an 01, although PV01 more accurately refers to the value of a one dollar or one basis point annuity). The relation between Dv01 and modified duration is:  

$$
M o d D=100\cdot\frac{D V O I}{\textsl{V}}\quad\qquadD V O I=\frac{M o d D\cdot V}{100}
$$  

The concepts of duration and Dv01 become more concrete if we focus on specific examples. Consider a two year and a ten year bond, together with two and ten year annuities and zero bonds. Table 1 shows these bonds, together with assumed prices and yields.  

Table 1 - Dv01 and Durations For Selected Swaps, Annuities, and Zero-Coupon Bonds 'V01 is the dollar change for a $\$100$ notional instrument per 100bp change in yield. Modified duration is the percent change per 100bp hange in yield. Macaulay duration is the weighted average time to maturity, in years.  

<html><body><table><tr><td>Instrument</td><td>Coupon (%)</td><td>Price</td><td>Yield （%)</td><td>DV01</td><td>Mod Dur</td><td>Mac Dur</td></tr><tr><td>2yr Bond</td><td>2.5</td><td>100.</td><td>2.5</td><td>1.94</td><td>1.94</td><td>1.96</td></tr><tr><td>10yr Bond</td><td>3.5</td><td>100.</td><td>3.5</td><td>8.38</td><td>8.38</td><td>8.52</td></tr><tr><td>2yr Ann</td><td>2.5</td><td>4.86</td><td>2.3</td><td>0.06</td><td>1.23</td><td>1.24</td></tr><tr><td>10yr Ann</td><td>3.5</td><td>29.72</td><td>3.22</td><td>1.46</td><td>4.91</td><td>4.98</td></tr><tr><td>2yr Zero</td><td>0.</td><td>95.14</td><td>2.51</td><td>1.88</td><td>1.97</td><td>2.</td></tr><tr><td>10yr Zero</td><td>0.</td><td>70.28</td><td>3.56</td><td>6.9</td><td>9.82</td><td>10.</td></tr></table></body></html>  

The Dv01 is the change in price per change in yield. It can be calculated (to a good approximation) by bumping yield up and down and taking the difference; i.e. calculating a numerical derivative. For example the ten year bond has a yield-to-maturity of $3.50\%$ and is priced at 100. At 10bp higher and lower the yields are. $3.6\%$ and $3.4\%$ and the prices are 99.1664 and 100.8417. The DV01 is approxim ately:  

$$
D V O I_{10\mathrm{yr{bond}}}=\frac{100.8417-99.1664}{3.6-3.4}=8.38
$$  

The modified duration can be calculated from the Dv01 using the relation in (5). The Macaulay duration can then be calculated using the relation (3) or the original definition (2). For the table above, and in most practical applications, it proves. easier to calculate a numerical derivative approximations to either Dv01 or modified duration (1 or 4) and then use the. relations (3) and (5) to derive the other measures..  

Table 1 shows the Macaulay duration of the zero bonds are equal to maturity, as should be. The modified durations are slightly lower (dividing by one plus yield as per above), and the Dvo1s lower still (multiplying by the zero prices, which are below 100). For the coupon bonds the Macaulay duration is less than maturity, reflecting the coupons that are paid prior to. m aturity.  

A good way to visualize the Macaulay duration is to imagine PVs of cash flows as weights placed on a balance-beam. Figure 1 shows the Macaulay duration for the two year annuity. The cash flows are. $\$1.25$ each half- year, and the circles represent the PVs, which gradually decline further out. The fulcrum of the balance beam is just slightly less than the mid-point (1.24 years). If we drew the diagram for the two year bond there would be a much large cash flow (the. $\$100$ principal) at year 2 and this is what pushes the Macaulay duration (the fulcrum on the balance beam) out to 1.96 years for the two year coupon bond..  

![](1814cb9a3ff36af6d901ced72027f0cf0be48f37951e9abd3da6a9e13985d0dd.jpg)  
Figure 1 - Macaulay Duration for Two Year Annuity   
This shows the Macaulay duration as the fulcrum or balance point on a balance beam, with weights representing the present value ofcash flows. "PV' is the present value ofthe cash flow. Time" is the maturity ofthe cash flow. The Macaulay Duration is shown at the fulcrum.  

The equality (or near-equality) in the values of modified and Macaulay duration can be a valuable aid to intuition. Macaulay duration will always be less than the maximum maturity (equal only for a single cash flow, i.e. a zero-coupon bond, as seen in table 1 and the definition in equation 2). This means we can often make a rough guess at the Macaulay duration and from that infer a rough value for the modified duration. For example a ten year bond will have Macaulay duration somewhat but not dramatically less than 10 years, and so the modified duration will be somewhat less than $10\%$ . In table 1 we can see that the ten year bond has a Macaulay duration of 8.5 years and a modified duration of $8.4\%$  

Macaulay duration is useful as an aide for intuition but in measuring price sensitivity we must use either modified duration or DV01. In many cases one can use either, converting between them using equation (5) depending on the needs of the problem. Generally, managers of real-money long-only portfolios use modified duration while managers of trading and derivatives portfolios tend to use Dvo1. Modified duration is well-suited for long-only portfolios, where risk and return can be. measured as a percent of portfolio value, while Dv01 is more suited to portfolios where the present value of the portfolio may be zero and measuring risk in dollar or absolute terms is more convenient..  

In using duration we must be careful with a few points. First, we must keep straight the distinction between Macaulay duration (a measure of maturity) and modified duration (a measure of price sensitivity). Second, we must remember that (modified) duration tells us the price sensitivity to a change in rates, but does not tell us what rates we are sensitive to, in spite of the term "duration"'. Consider the ten year annuity, which has a Macaulay and modified duration of roughly 5. The duration of 5 does not mean the annuity reacts in the same way as a five year bond. Think back to the fulcrum view from figure 1 - for the annuity the fulcrum is in the middle but the cash flows at the far end depend on longer-dated rates. For the ten year annuity the fulcrum sits at roughly 5 years but there are cash flows extending out to ten years.  

As a personal matter I usually use Dv01 rather than duration. I prefer to sidestep the confusion between the different. meanings of the term "duration" and find the concept of Dv01 cleaner and simpler. Having stated my preference, however,. it is a personal preference and Dv01 or modified duration can usually be used interchangeably. Throughout the rest of this paper, however, I will use Dv01 rather than duration..  

# Yield and Forward Curves  

The discussion above treated Dv01 as a function of yield-to-maturity, essentially treating each bond or instrument on its own, having its own yield. In many situations we will in contrast consider a set of bonds or instruments together, all valued off a common market-based yield curve. For example a collection of swaps will be valued off a yield curve derived for a. small set of on-the-run or active instruments (swaps, futures, libor deposits). The value of the swaps is the discounted value. of future cash flows, discounting off the yield curve. Discounting cash flows off a yield curve or forward curve forms the. foundation for all trading of fixed income instruments.  

When a collection of bonds or other fixed-income instruments is valued off a common yield curve, the idea of Dv01 or. duration extends naturally to partial Dv01s or key rate durations. Such partial Dv01s are widely used on trading desks and. risk management groups. Before turning to partial Dv01s, however, it is useful to briefly review the idea of yield or forward curves. (Coleman 1998 discusses forward curves in more detail.)  

# Forw ard, Zero, and Discount Curves  

The most constructive way to think of a yield curve is as a function that provides the discount factor for any day - for our the bonds discussed above we would want the discount factor for any date from today out to 10 years in the future. It is particularly convenient to work with the forward curve $f(t)$ , where $t$ is the maturity measured in years from today and $f(.)$ is the instantaneous forward rate. Alternatively we could work the zero-coupon yield curve $z(t)$ , or discount curve $d(t)$ , but the three are related and so the choice becomes one of convenience. When we express rates continuously-compounded, the relations between the forward, zero, and discount curve are:  

$$
z\left(t\right)=\frac{\int_{0}^{t}f\left(u\right)d u}{t}
$$  

$$
d(t)=\exp[-z\left(t\right)\cdot t]=\exp\left[-{\int_{0}^{t}}f\left(u\right)d u\right].
$$  

n what follows I will often use the terms forward curve, yield curve, and zero curve interchangeably; since we can always ranslate between the forward, zero, and discount functions this casual terminology should be acceptable..  

In general we want to be able to get the discount factor for any date; i.e. we want $f(t)$ for any and all $t$ Market data (such as in table 2 below) never provide enough data to directly determine the discount factor for every day. Instead we generally. assume some parametric (but flexible) functional form, depending on parameters or variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ , for the forward curve. We then choose the parameters so that the curve prices the market data correctly. This means the forward / zero curve will be a function of the variables:. $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$  

# Example of Forward Curve  

An example helps to explain and clarify how a yield curve is constructed and used. Say that the following swaps are PV zero in the market, and we decide to use these as our market data:  

Table 2 - Hypothetical Market (Zero-PV) Swaps  

USD Swaps   


<html><body><table><tr><td>Maturity (yrs)</td><td>Fixed Rate （%)</td></tr><tr><td>1</td><td>2</td></tr><tr><td>2</td><td>2.5</td></tr><tr><td>5</td><td>3</td></tr><tr><td>10</td><td>3.5</td></tr></table></body></html>  

In other words these are the current-market par swap rates. We can now build a forward or yield curve that is consistent with these par swap rates.  

As an example of a functional form we can assume that instantaneous forward rates are constant between instrument maturity points (break points or knot points) and that the forward rates jump at maturity points. In this case the variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ are the forward rates between knot points. (This is, in fact, a practical and useful forward curve often used by market practitioners, but it is only one among many.) Functionally, this is a piece-wise constant function:  

$$
\left\{\begin{array}{l l}{£1}&{0\leq\mathtt{t}\&\mathtt{k}\in\mathtt{\iota}<1}\ {£2}&{1\leq\mathtt{t}\&\mathtt{k}\in\mathtt{\iota}<2}\ {£3}&{2\leq\mathtt{t}\&\mathtt{k}\in\mathtt{t}<5}\ {£4}&{5\leq\mathtt{t}\&\mathtt{k}\in\mathtt{\iota}<10}\ {0}&{\mathrm{True}}\end{array}\right.
$$  

If we choose the forward rates to match the market data given in table 2, we get:  

$$
\left\{\begin{array}{l l}{0.0199}&{0\leq\mathtt{t}\&\mathtt{t}\cot<1}\ {0.0299}&{1\leq\mathtt{t}\&\mathtt{t}<2}\ {0.0333}&{2\leq\mathtt{t}\&\mathtt{t}<5}\ {0.0406}&{5\leq\mathtt{t}\&\mathtt{t}<10}\ {0}&{\mathrm{True}}\end{array}\right.
$$  

and graphically the forward function is a step function:  

![](dc7607394395fdb5c56e4da644694260f5904b126ea0ed9107d4303c89d13d63.jpg)  
Figure 2 - Piece-Wise Constant Forward Curve   
Solid are Zero Rates, Dashed are Forward Rates  

These instantaneous forward rates are chosen so that the market instruments are priced correctly. We can now use this forward curve to price arbitrary cash flows to obtain market-based prices of other instruments, prices that are consistent with the instruments shown in table 2.  

In practice swap curves are usually built with a variety of different instruments, including libor deposits, libor futures, and par swaps. For expository purposes it will be useful to consider a curve built with both spot and forward instruments, and. thus we will build our curve with the following instruments:.  

Table 3 - Market Instrument Used for Building Sample Curve  

<html><body><table><tr><td>Instrument</td><td>Forward Start</td><td>Underlier (yrs)</td><td>Coupon Rate (%)</td><td>Fwd Rate (cc)</td></tr><tr><td>1yr Swap</td><td>0</td><td>1</td><td>2.</td><td>0.0199</td></tr><tr><td>1 y2y Fwd</td><td>1</td><td>1</td><td>3.014</td><td>0.0299</td></tr><tr><td>5yr Swap</td><td></td><td>5</td><td>3.</td><td>0.0333</td></tr><tr><td>10yr Swap</td><td>0</td><td>10</td><td>3.5</td><td>0.0406</td></tr></table></body></html>  

These instruments produce the values for the forward curve variables (the instantaneous forward rates) shown above in figure 2.  

# PV of Instruments Off Curve  

With this forward curve we can now price the original market instruments (which by construction will have PV zero) plus other swaps or bonds. Table 4 shows the original PV-zero market swaps, plus a selection of additional swaps, annuities and zero-coupon instruments (all notional 100).  

Table 4 - PV For Selected Swaps, Annuities, Zero-Coupon Bonds, and Forward Swaps  

<html><body><table><tr><td>Instrument</td><td>ForwardStart</td><td>Underlier (yrs)</td><td>Coupon Rate (%)</td><td>PV</td></tr><tr><td>1yr Swap</td><td>0</td><td>1</td><td>2.</td><td>0.</td></tr><tr><td>1y2y Fwd</td><td>1</td><td>1</td><td>3.014</td><td>0.</td></tr><tr><td>5yr Swap</td><td>0</td><td>5</td><td>3.</td><td>0.</td></tr><tr><td>10yr Swap</td><td>0</td><td>10</td><td>3.5</td><td>0.</td></tr><tr><td>2yr Swap</td><td>0</td><td>2</td><td>2.5</td><td>0.</td></tr><tr><td>3yr S Swap</td><td>0</td><td>3</td><td>2.8</td><td>0.06</td></tr><tr><td>2yr Ann</td><td>0</td><td>2</td><td>2.5</td><td>4.86</td></tr><tr><td>10yr Ann</td><td>0</td><td>10</td><td>3.5</td><td>29.72</td></tr><tr><td>2yr Zero</td><td>0</td><td>2</td><td>0.</td><td>95.14</td></tr><tr><td>10yr Zero</td><td>0</td><td>10</td><td>0.</td><td>70.28</td></tr></table></body></html>  

DV01s are reported as dollar change for a. $\$100$ notional instrument per 100bp change in yields orrates. Instruments used in fitting the curve are highlighted.  

# PartialDV01s  

Partial Dv01s, partial durations, or key rate durations are used throughout the finance industry and have a long history. Ho. (1992) introduced the term key rate duration. Reitano covered multifactor yield curve models as early as 1991 (Reitano 1991) and has revisited the topic in a recent review (Reitano 2008)..  

When we use a yield curve to value a set of fixed income instruments rather than a single yield-to-maturity for each bond, it is natural to extend the concept of Dv01 from a univariate derivative to a set of partial derivatives. We now turn to these partial DV01s.  

# Risk w.r.t. Curve Variables  

Once we have a forward curve as a function of the variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ it is straight-forward to calculate the partial derivatives (delta risk or Dvo1) with respect to these curve variables or parameters. As a practical matter we might do this by simply bumping the variables up and down and taking a numerical derivative, as we did above for the Dv01 with a single yield-to-maturity. Say we have a portfolio consisting of $n$ instruments or positions. The prices or PVs of these instruments will be functions of the curve variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ represented by the vector  

$$
{\mathrm{Prices}}={\left(\begin{array}{l}{P_{1}}\ {\vdots}\ {P_{n}}\end{array}\right)}={\left(\begin{array}{l l l}{P_{1}(\nu_{1}\cdots\nu_{k})}\ &{\vdots}\ {P_{n}(\nu_{1}\cdots\nu_{k})}\end{array}\right)}
$$  

and the matrix of partial derivatives will be:  

$$
=\left(\begin{array}{c c c}{\frac{\partial P_{1}}{\partial\nu_{1}}}&{\dots}&{\frac{\partial P_{1}}{\partial\nu_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial P_{n}}{\partial\nu_{1}}}&{\dots}&{\frac{\partial P_{n}}{\partial\nu_{k}}}\end{array}\right)
$$  

For the piece-wise forward curve we are using, the curve variables are forward rates and the partial Dv01s will be with respect to forward rates. For the sample market yield curve shown in table 3 the forward rate partial Dv01s for selected instruments will be:  

Table 5 - Dv01 w.r.t. Curve Variables (Forward Rates) for Selected Instruments   


<html><body><table><tr><td></td><td>foyly</td><td>fly2y</td><td>f2y5y</td><td>f5y10y</td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.99</td><td>0.</td><td>0.</td><td>0.</td><td>0.99</td></tr><tr><td>1y2y Fwd</td><td>0.</td><td>0.97</td><td>0.</td><td>0.</td><td>0.97</td></tr><tr><td>5yr Swap</td><td>0.99</td><td>0.96</td><td>2.72</td><td>0.</td><td>4.68</td></tr><tr><td>10yr Swap</td><td>0.99</td><td>0.96</td><td>2.68</td><td>3.87</td><td>8.5</td></tr><tr><td>2yr Swap</td><td>0.99</td><td>0.97</td><td>0.</td><td>0.</td><td>1.96</td></tr><tr><td>3yr Swap</td><td>0.99</td><td>0.97</td><td>0.94</td><td>0.</td><td>2.9</td></tr><tr><td>2yr Ann</td><td>0.04</td><td>0.02</td><td>0.</td><td>0.</td><td>0.06</td></tr><tr><td>10yr Ann</td><td>0.29</td><td>0.25</td><td>0.57</td><td>0.36</td><td>1.47</td></tr><tr><td>2yr Zero</td><td>0.95</td><td>0.95</td><td>0.</td><td>0.</td><td>1.9</td></tr><tr><td>10yr Zero</td><td>0.7</td><td>0.7</td><td>2.11</td><td>3.51</td><td>7.03</td></tr></table></body></html>  

DV01s are reported as dollar change for a $\$100$ notional instrument per 100bp change in yields or rates. Curve variables are continuously compounded forward rates. Instruments used in fitting the curve are highlighted.  

# Risk w.r.t. Curve Inputs  

Calculating the risk in table 5, partial Dv01s w.r.t. the curve variables, is straight-forward but often we will want risk. expressed in a different form. An alternative and conceptually straight-froward method for calculating Dv01s is to bump the input instruments used in building the curve. In our case the curve is built using 1, 5, and 10 year swaps and the 1-2 year. forward swap. We could bump the inputs, in this case the par swap rates or fixed rates for the swaps. We would bump inputs one-at-a-time, rebuild the curve each time, revalue the portfolio with each new curve, and thereby calculate numerical partial derivatives with respect to each input.  

There are a variety of reasons we may be interested in risk calculated w.r.t. alternate variables. One important reason may be that the variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ that appear in the forward $f(t)$ or zero curve $z(t)$ may not be financially meaningful. For. example cubic splines are a common choice for functional form, and the variables will not have as simple an interpretation. as the forward rates in the curve used here. Another reason may be that, even if the parameters have some financial interpretation, the units may not be those desired - for our example here the forward rates are quoted as continuously-compounded. whereas in the U.S. market yields are usually quoted semi-annually compounded. In the end the reason may be something as simple as our boss preferring to see risk quoted in some other manner..  

urning to the bumping of curve input, if the $k$ curve input rates are. $(\mathrm{~}r_{1}\mathrm{~~}\cdots\mathrm{~~}r_{k}\mathrm{~~})$ then the matrix of partial derivatives is:.  

$$
\mathrm{DpDr}=\mathrm{Derivative~of~prices~}{\boldsymbol{w}}\cdot{\boldsymbol{r}}\cdot{\boldsymbol{t}}\cdot\mathrm{~curve~input~rates}={\left(\begin{array}{l l l}{{\frac{\partial P_{1}}{\partial r_{1}}}}&{\dots}&{{\frac{\partial P_{1}}{\partial r_{k}}}}\ {\vdots}&{\ddots}&{\vdots}\ {{\frac{\partial P_{n}}{\partial r_{1}}}}&{\dots}&{{\frac{\partial P_{n}}{\partial r_{k}}}}\end{array}\right)}
$$  

For our hypothetical market yield curve and the instruments shown in table 3, the risk will be w.r.t. the 1 year par rate, the 1-2 year forward par rate, the 5 year and 10 year par rates. This is shown in table 4.  

Table 6 - Dv01 w.r.t. Curve Input Rates for Selected Instruments, Calculated by Direct Bumping of Inputs  

<html><body><table><tr><td></td><td>lyr Swap</td><td>1y2y Fwd</td><td>5yr Swap</td><td>10yr Swap</td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td><td>0.</td><td>0.98</td></tr><tr><td>1y2y Fwd</td><td>0.</td><td>0.96</td><td>0.</td><td>0.</td><td>0.96</td></tr><tr><td>5yr Swap</td><td>0.</td><td>0.</td><td>4.64</td><td>0.</td><td>4.64</td></tr><tr><td>10yr Swap</td><td>0.</td><td>0.</td><td>0.</td><td>8.49</td><td>8.49</td></tr><tr><td>2yr Swap</td><td>0.98</td><td>0.95</td><td>0.</td><td>0.</td><td>1.94</td></tr><tr><td>3yr Swap</td><td>0.64</td><td>0.62</td><td>1.6</td><td>0.</td><td>2.87</td></tr><tr><td>2yr Ann</td><td>0.04</td><td>0.02</td><td>0.</td><td>0.</td><td>0.06</td></tr><tr><td>10yr Ann</td><td>0.08</td><td>0.05</td><td>0.54</td><td>0.79</td><td>1.46</td></tr><tr><td>2yr Zero</td><td>0.94</td><td>0.94</td><td>0.</td><td>0.</td><td>1.88</td></tr><tr><td>10yr Zero</td><td>-0.08</td><td>-0.05</td><td>-0.54</td><td>7.7</td><td>7.03</td></tr></table></body></html>  

Dv01s are reported as dollar change for a $\$100$ notional instrument per 100bp change in yields orrates. Instruments used in fitting the curve are highlighted.  

The partial Dv01s w.r.t. curve inputs shown in table 6 is simply a transformation of the original risk w.r.t. curve variables shown in table 5. The underlying forward curve changes in exactly the same manner, we just measure the Dv01s w.r.t. the curve inputs rather than the curve parameters. Nor are we restricted to the curve inputs we originally used. We could use alternate instruments that would be appropriate for building the curve. For example we could substitute the 2 year swap for the 1-2 year forward and then we would have the risk w.r.t. the par swap instead of the forward swap..  

# PartialDv01 Transformations  

Bumping curve inputs is very useful but requires re-building the yield curve multiple times and re-calculating the risk for the. whole portfolio. In many risk systems it is easy to calculate the derivatives w.r.t. curve parameters but difficult (requiring re-. programming) to calculate derivatives w.r.t. curve inputs. We now turn to an approach that accomplishes the same - risk as if we re-built and bumped curve inputs - but without the burden of actually re-building the curve and re-valuing the whole. portfolio. The trick is that we can choose a set of alternate curve inputs and use the multivariate inverse function theorem to. calculate the inverse Jacobian to obtain the transformation that converts the original partial Dvo1s into partials w.r.t. the alternate curve inputs.  

# Partial Dv01s w.r.t Alternate Variables  

We now describe a straight-forward method to calculate derivatives w.r.t. alternate variables (subject to certain technical restrictions). The result will be to calculate the risk as if we went through the process of re-building the curve and bumping. w.r.t. inputs as in the previous section, but without the burden of actually re-building the curve multiple times..  

Jonsider $k$ alternate variables $\left(\begin{array}{l l l}{x_{1}}&{\cdots}&{x_{k}}\end{array}\right)$ . Assume for now that these alternate variables are themselves the yields or :ates we want to use for calculating partial Dv01s and that we can calculate these as a function of the forward curve:  

$$
{\mathrm{Alternate~variables}}={\left(\begin{array}{l}{x_{1}}\ {\vdots}\ {x_{k}}\end{array}\right)}={\left(\begin{array}{l l l}{x_{1}(\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)}\ {\vdots}&{\vdots}\ {x_{k}(\nu_{1}}&{\cdots}&{\nu_{k})}\end{array}\right)}
$$  

If we have the same number of variables $(\mathrm{~\boldmath~{~\pi~}~}_{1}\mathrm{~\boldmath~{~\cdot~}~}\mathrm{~\boldmath~{~\pi~}~}_{\stackrel{{\scriptstyle}{{x_{k}}}}{\cal{~)}}}$ as curve variables $(\mathrm{~\boldmath~\nu~}_{1}\mathrm{~\boldmath~\cdots~}\mathrm{~\boldmath~\nu~}_{k})$ then we can calculate the derivatives of these alternate variables w.r.t. the curve variables and this will be the Jacobian matrix for the function (8):  

$$
\mathrm{DxDv}=\mathrm{Jacobian~for~Curve}\to\mathrm{~Alternate~Variables}=\left(\begin{array}{r r r}{\frac{\partial x_{1}}{\partial\nu_{1}}}&{\cdots}&{\frac{\partial x_{1}}{\partial\nu_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial x_{k}}{\partial\nu_{1}}}&{\cdots}&{\frac{\partial x_{k}}{\partial\nu_{k}}}\end{array}\right)
$$  

If this Jacobian is non-singular, then the inverse function theorem tells us that there is an inverse function  

$$
{\left(\begin{array}{l}{\nu_{1}}\ {\vdots}\ {\nu_{k}}\end{array}\right)}={\left(\begin{array}{l l l}{\nu_{1}(\nu_{1}\cdots x_{k})}\ &{\vdots}\ {\nu_{k}(x_{1}\cdots x_{k})}\end{array}\right)}
$$  

and the Jacobian of this function is  

$$
{\mathrm{Inverse~Jacobian~}}={\mathrm{DvDX}}={\left(\begin{array}{l l l}{{\frac{\partial\nu_{1}}{\partial x_{1}}}}&{\cdots}&{{\frac{\partial\nu_{1}}{\partial x_{k}}}}\ {\vdots}&{\ddots}&{\vdots}\ {{\frac{\partial\nu_{k}}{\partial x_{1}}}}&{\cdots}&{{\frac{\partial\nu_{k}}{\partial x_{k}}}}\end{array}\right)}={\left(\begin{array}{l l l}{{\frac{\partial x_{1}}{\partial\nu_{1}}}}&{\cdots}&{{\frac{\partial x_{1}}{\partial\nu_{k}}}}\ {\vdots}&{\ddots}&{\vdots}\ {{\frac{\partial x_{k}}{\partial\nu_{1}}}}&{\cdots}&{{\frac{\partial x_{k}}{\partial\nu_{k}}}}\end{array}\right)}^{-1}
$$  

Jsing the Jacobian of the inverse function we can transform the derivatives w.r.t. curve variables to derivatives w.r.t. the new ariables. Consider the first row of equation 6:  

Derivative for $P_{1}\mathrm{~}w\mathrm{~}.r\mathrm{~}.t$ . Alternate Variables $=$  

$$
\begin{array}{r}{\left(\begin{array}{l l l}{\frac{\partial P_{1}}{\partial x_{1}}}&{\cdots}&{\frac{\partial P_{1}}{\partial x_{k}}}\end{array}\right)=\left(\begin{array}{l l l}{\frac{\partial P_{1}}{\partial v_{1}}}&{\cdots}&{\frac{\partial P_{1}}{\partial v_{k}}}\end{array}\right)\cdot\left(\begin{array}{l l l}{\frac{\partial v_{1}}{\partial x_{1}}}&{\cdots}&{\frac{\partial v_{1}}{\partial x_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial v_{k}}{\partial x_{1}}}&{\cdots}&{\frac{\partial v_{k}}{\partial x_{k}}}\end{array}\right)=\left(\begin{array}{l l l}{\frac{\partial P_{1}}{\partial v_{1}}}&{\cdots}&{\frac{\partial P_{1}}{\partial v_{k}}}\end{array}\right)\cdot\left(\begin{array}{l l l}{\frac{\partial x_{1}}{\partial v_{1}}}&{\cdots}&{\frac{\partial x_{1}}{\partial v_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial x_{k}}{\partial v_{1}}}&{\cdots}&{\frac{\partial x_{k}}{\partial v_{k}}}\end{array}\right)^{-1}}\end{array}
$$  

so that the full matrix is:  

$$
\mathrm{DpDx}=\mathrm{Partial~DV01}w\ldots t\mathrm{~Alternate~Variables}=\left(\begin{array}{c c c}{\frac{\partial P_{1}}{\partial x_{1}}}&{\ldots}&{\frac{\partial P_{1}}{\partial x_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial P_{n}}{\partial x_{1}}}&{\ldots}&{\frac{\partial P_{n}}{\partial x_{k}}}\end{array}\right)=\mathrm{DpDv}\mathrm{~.~DvDx}
$$  

$=$ Derivative w .r.t . Curve Variables $^*$ Inverse Jacobian $\mathbf{\Sigma}=\left(\begin{array}{c c c}{\frac{\partial P_{1}}{\partial\nu_{1}}}&{\dots}&{\frac{\partial P_{1}}{\partial\nu_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial P_{n}}{\partial\nu_{1}}}&{\dots}&{\frac{\partial P_{n}}{\partial\nu_{k}}}\end{array}\right)\cdot\left(\begin{array}{c c c}{\frac{\partial x_{1}}{\partial\nu_{1}}}&{\dots}&{\frac{\partial x_{1}}{\partial\nu_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial x_{k}}{\partial\nu_{1}}}&{\dots}&{\frac{\partial x_{k}}{\partial\nu_{k}}}\end{array}\right)^{-1}$  

# Partial Dv01 w.r.t. Yield  

If the variables $(\mathrm{~\boldmath~{~\boldsymbol~{~x~}~}~}_{1}\mathrm{~\boldmath~{~\cdot~}~}\mathrm{~\boldmath~{~\boldsymbol~{~\cdot~}~}~}\mathrm{~\boldmath~{~\boldsymbol~{~\it~{~\varepsilon~}~}~}~})$ are the yields or rates we want, and our risk system can easily produce the matrix (9), then equation (11) is the transformation matrix we need. Most risk systems, however, will not produce the matrix of partials for yields directly. More often the variables $\left(\begin{array}{l l l}{x_{1}}&{\cdots}&{x_{k}}\end{array}\right)$ will be price or PV functions for traded instruments. Risk systems are usually set up to easily calculate risk for traded instruments, so that it is easy to calculate the Jacobian (9) for price functions.. But we usually want to calculate risk w.r.t. yields or rates, $\left(\begin{array}{l l}{{y_{1}}}&{{\cdots}}\ {{}}&{{}{\:y_{k}}}\end{array}\right)$ , rather than prices of traded instruments.  

The solution to this is simple. For each instrument we have a function that gives the yield as a function of the price, and equation (8) is replaced by:  

$$
\left(\begin{array}{c}{y_{1}}\ {\vdots}\ {y_{k}}\end{array}\right)=\left(\begin{array}{c c c}{y_{1}(\nu_{1}}&{\cdots}&{\nu_{k})}\ &{\vdots}\ {y_{k}(\nu_{1}}&{\cdots}&{\nu_{k})}\end{array}\right)=\left(\begin{array}{c}{f_{1}(x_{1})}\ {\vdots}\ {f_{k}(x_{k})}\end{array}\right)=\left(\begin{array}{c}{f_{1}[x_{1}(\nu_{1}\cdots\nu_{k})]}\ {\vdots}\ {f_{k}[x_{k}(\nu_{1}\cdots\nu_{k})]}\end{array}\right)
$$  

Using the uni-variate inverse function theorem we can calculate $f_{i}^{'}$ as one over the derivative of price w.r.t. yield (the basic. DV01):  

$$
\boldsymbol{f}_{i}^{\phantom{\dagger}}=\left(\frac{d\boldsymbol{x}_{1}}{d\boldsymbol{y}_{1}}\right)^{-1}
$$  

and by application of the uni-variate inverse function theorem and the chain rule, we can get the inverse Jacobian for these yield variables:  

$$
{\mathrm{Inverse~Jacobian}}={\mathrm{DvDy}}={\left(\begin{array}{l l l}{{\frac{\partial{\nu}_{1}}{\partial{y}_{1}}}}&{\cdots}&{{\frac{\partial{\nu}_{1}}{\partial{y}_{k}}}}\ {\vdots}&{\ddots}&{\vdots}\ {{\frac{\partial{\nu}_{k}}{\partial{y}_{1}}}}&{\cdots}&{{\frac{\partial{\nu}_{k}}{\partial{y}_{k}}}}\end{array}\right)}={\left(\begin{array}{l l l}{\left({\frac{d{x}_{1}}{d{y}_{1}}}\right)^{-1}{\frac{\partial{x}_{1}}{\partial{v}_{1}}}}&{\cdots}&{\left({\frac{d{x}_{1}}{d{y}_{1}}}\right)^{-1}{\frac{\partial{x}_{1}}{\partial{v}_{k}}}}\ {\vdots}&{\ddots}&{\vdots}\ {\left({\frac{d{x}_{k}}{d{y}_{k}}}\right)^{-1}{\frac{\partial{x}_{k}}{\partial{v}_{1}}}}&{\cdots}&{\left({\frac{d{x}_{k}}{d{y}_{k}}}\right)^{-1}{\frac{\partial{x}_{k}}{\partial{v}_{k}}}}\end{array}\right)}^{-1}
$$  

The transformation (11) now becomes  

DpDy $=$ Partial Dvo1 w .r .t . Alternate Variables (via yield function) $=$  

$$
\begin{array}{r}{\mathrm{DpDv}\cdot\mathrm{DvDy}=\left(\begin{array}{c c c}{\frac{\partial P_{1}}{\partial y_{1}}}&{\cdots}&{\frac{\partial P_{1}}{\partial y_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial P_{n}}{\partial y_{1}}}&{\cdots}&{\frac{\partial P_{n}}{\partial y_{k}}}\end{array}\right)=\left(\begin{array}{c c c}{\frac{\partial P_{1}}{\partial v_{1}}}&{\cdots}&{\frac{\partial P_{1}}{\partial v_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial P_{n}}{\partial v_{1}}}&{\cdots}&{\frac{\partial P_{n}}{\partial v_{k}}}\end{array}\right)\cdot\left(\begin{array}{c c c c}{\frac{d x_{1}}{d y_{1}}}\ {\vdots}&{\frac{\partial x_{1}}{\partial v_{1}}}&{\cdots}&{\left(\frac{d x_{1}}{d y_{1}}\right)^{-1}\frac{\partial x_{1}}{\partial v_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{d x_{k}}{d y_{k}}}&{\cdots}&{\left(\frac{d x_{k}}{d y_{k}}\right)^{-1}\frac{\partial x_{k}}{\partial v_{k}}}\end{array}\right)^{-1}}\end{array}
$$  

The whole idea here is that it is generally easy to calculate the Jacobian (9) for price functions. As long as the alternate variables we wish to use are yields for traded instruments we have a simple multi-step process  

1. Choose a set of traded instruments $\left(\begin{array}{l l l}{x_{1}}&{\cdots}&{x_{k}}\end{array}\right)$ that match the curve variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ in terms of maturity or   
other characteristics so that the Jacobian will be well-behaved   
2. Calculate the risk of these instruments w.r.t. curve variables. $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ , giving the price Jacobian (9)   
3. Using the uni-variate yield functions (12) calculate the inverse Jacobian (13)   
4. Transform the risk of an arbitrary set of instruments or portfolios using the inverse Jacobian according to (14)  

The calculation in step (2) requires evaluating the risk of a small set of traded instruments, and this (and the additional calculations) will usually be quick and cheap relative to evaluating the risk of the whole portfolio. The transformation matrix (13) (or 11) can then be applied to the original portfolio risk, transforming the partial Dv01s from curve variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ to alternate yields $\left(\begin{array}{l l l}{{y_{1}}}&{{\cdots}}&{{y_{k}}}\end{array}\right)$ . Naturally, the same process applies if the original risk is reported w.r.t. curve input rates $(\mathrm{~}r_{1}\mathrm{~~}\cdots\mathrm{~~}r_{k}\mathrm{~~})$  

# Example of Transformation to Input Variables  

As an example let us take the variables. $(\mathrm{~\boldmath~{~\boldsymbol~{~x~}~}~}_{1}\mathrm{~\boldmath~{~\cdot~}~}\mathrm{~\boldmath~{~\boldsymbol~{~\cdot~}~}~}\mathrm{~\boldmath~{~\boldsymbol~{~\it~{~\varepsilon~}~}~}~})$ in equation (8) to be the par rates on the curve input instruments. In. other words the alternate variables. $(\mathrm{~\boldmath~{~\boldsymbol~{~x~}~}~}_{1}\mathrm{~\boldmath~{~\cdot~}~}\mathrm{~\boldmath~{~\boldsymbol~{~\cdot~}~}~}\mathrm{~\boldmath~{~\boldsymbol~{~\it~{~\varepsilon~}~}~}~})$ will be the vector of rates on the swaps shown in table 2, reproduced here:  

<html><body><table><tr><td>Instrument</td><td>Forward Start</td><td>Underlier (yrs)</td><td>Coupon Rate (%)</td></tr><tr><td>1 yr Swap</td><td>0</td><td>1</td><td>2.</td></tr><tr><td>1 y2y Fwd</td><td>1</td><td>1</td><td>3.014</td></tr><tr><td>5yr Swap</td><td>0</td><td>5</td><td>3.</td></tr><tr><td>10yr Swap</td><td>0</td><td>10</td><td>3.5</td></tr></table></body></html>  

Further, let us say that our risk system can easily calculate the derivatives of these rates w.r.t. the curve variables. In this case we can apply equation (11) directly. This is an exercise only, since we should end up with the same risk as bumping the curve inputs, shown in table 6. In this case the Jacobian for the alternate variables $(\mathrm{~\boldmath~{~\boldsymbol~{~x~}~}~}_{1}\mathrm{~\boldmath~{~\cdot~}~}\mathrm{~\boldmath~{~\boldsymbol~{~\cdot~}~}~}\mathrm{~\boldmath~{~\boldsymbol~{~\it~{~~\varepsilon~}~}~}~})$ is  

Table 7 - Jacobian for Curve Input Rates (Equation 9)  

1.01 0. 0. 0.   
0. 1.015 0. 0.   
0.214 0.208 0.587 0.   
0.117 0.113 0.315 0.456  

Applying the transformation shown in equation (11) to the derivatives (Dv01s) w.r.t. curve variables shown in table 5 gives.   
the risk shown in table 8, which is the same answer as we obtain by bumping the curve itself, shown in table 6.  

Table 8 - Dv01 w.r.t. Curve Input Rates for Selected Instruments, Transformed via Equation 11  

<html><body><table><tr><td></td><td>lyr Swap</td><td>1y2y Fwd</td><td>5yr Swap</td><td>10yr Swap</td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td><td>0.</td><td>0.98</td></tr><tr><td>1y2y Fwd</td><td>0.</td><td>0.96</td><td>0.</td><td>0.</td><td>0.96</td></tr><tr><td>5yr Swap</td><td>0.</td><td>0.</td><td>4.64</td><td>0.</td><td>4.64</td></tr><tr><td>10yr Swap</td><td>0.</td><td>0.</td><td>0.</td><td>8.49</td><td>8.49</td></tr><tr><td>2yr Swap</td><td>0.98</td><td>0.95</td><td>0.</td><td>0.</td><td>1.94</td></tr><tr><td>3yr Swap</td><td>0.64</td><td>0.62</td><td>1.6</td><td>0.</td><td>2.87</td></tr><tr><td>2yr Ann</td><td>0.04</td><td>0.02</td><td>0.</td><td>0.</td><td>0.06</td></tr><tr><td>10yr Ann</td><td>0.08</td><td>0.05</td><td>0.54</td><td>0.79</td><td>1.46</td></tr><tr><td>2yr Zero</td><td>0.94</td><td>0.94</td><td>0.</td><td>0.</td><td>1.88</td></tr><tr><td>10yr Zero</td><td>-0.08</td><td>-0.05</td><td>-0.54</td><td>7.7</td><td>7.03</td></tr></table></body></html>  

DV01s are reported as dollar change for a $\$100$ notional instrument per l00bp change in yields orrates. Instruments used in fitting the curve are highlighted. Transformed via equation (11)  

# Example of Transformation to Par Rate Partial Dv01  

Now let us turn to a more substantive example, where we wish to measure Dv01s w.r.t. par swap rates instead of the mix of spot and forward swaps shown in tables 5 and 6. In other words we take the variables (. $\left(\begin{array}{l l l}{x_{1}}&{\cdots}&{x_{k}}\end{array}\right)$ in equation (8) to be the par swap rates on 1, 2, 5, and 10 year swaps:  

<html><body><table><tr><td>Maturity (yrs)</td><td>Fixed Rate (%)</td></tr><tr><td>1</td><td>2</td></tr><tr><td>2</td><td>2.5</td></tr><tr><td>5</td><td>3</td></tr><tr><td>10</td><td>3.5</td></tr></table></body></html>  

Again, let use assume that our risk system can easily calculate the derivatives of the rates themselves w.r.t. the curve variable: so that we can apply equation (11) directly. The Jacobian for these rates is:.  

Table 9 - Jacobian for Par Swap Rates (Equation 9)  

1.01 0. 0. 0.   
0.511 0.499 0. 0.   
0.214 0.208 0.587 0.   
0.117 0.113 0.315 0.456  

Applying the transformation shown in equation (11) to the derivatives (Dv01s) w.r.t. curve variables shown in table 5 gives the risk shown in table 9. Risk expressed in this form may be more intuitive than that shown in table 6. Here a 2 year swap is sensitive to only the 2 year swap, while a 3 year swap is sensitive to both the 2 year swap rate and the 5 year swap rate..  

Table 10 - Dv01 w.r.t. Par Swap Rates for Selected Instruments, Transformed via Equation 11  

<html><body><table><tr><td></td><td>lyr Swap</td><td>2yr Swap</td><td>5yr Swap</td><td>10yr Swap</td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td><td>0.</td><td>0.98</td></tr><tr><td>1 y2y Fwd</td><td>-0.99</td><td>1.95</td><td>0.</td><td>0.</td><td>0.96</td></tr><tr><td>5yr Swap</td><td>0.</td><td>0.</td><td>4.64</td><td>0.</td><td>4.64</td></tr><tr><td>10yr Swap</td><td>0.</td><td>0.</td><td>0.</td><td>8.49</td><td>8.49</td></tr><tr><td>2yr Swap</td><td>0.</td><td>1.94</td><td>0.</td><td>0.</td><td>1.94</td></tr><tr><td>3yr Swap</td><td>0.</td><td>1.27</td><td>1.6</td><td>0.</td><td>2.87</td></tr><tr><td>2yr Ann</td><td>0.02</td><td>0.04</td><td>0.</td><td>0.</td><td>0.06</td></tr><tr><td>10yr Ann</td><td>0.03</td><td>0.11</td><td>0.54</td><td>0.79</td><td>1.46</td></tr><tr><td>2yr Zero</td><td>-0.02</td><td>1.91</td><td>0.</td><td>0.</td><td>1.88</td></tr><tr><td>10yr Zero</td><td>-0.03</td><td>-0.11</td><td>-0.54</td><td>7.7</td><td>7.03</td></tr></table></body></html>  

DV01s are reported as dollar change for a $\$100$ notional instrument per 100bp change in yields orrates. Instruments used in fitting the curve are highlighted. Transformed via equation (11)  

# Transformation w.r.t. Yields vs. Par Rates  

There is a subtle issue concerning Dv01 w.r.t. yields versus Dv01 w.r.t. par rates as shown in tables 8 and 10. For a bond the price is  

$$
P r i c e~=~c o u p o n~*~\mathrm{PV}(\mathcal{S}I~a n n u i t y~)~+~100~*~\mathrm{PV}(\mathcal{\S}I~a t~m a t u r i t y)
$$  

with the PVs calculated from the forward curve. The par coupon or par rate is the coupon that makes the price equal to pa1 (100):  

$$
p a r c o u p o n=r={\frac{100-\mathrm{PV}(\S I O O a t m a t u r i t y)}{\mathrm{PV}(\S I a n n u i t y)}}
$$  

The yield-to-maturity is the solution to:  

$$
P r i c e=\sum_{i=1}^{n}\frac{c o u p o n}{\left(1~+~y\right)^{i}}~+\frac{100}{\left(1~+~y\right)^{n}}
$$  

(ignoring for now complications related to partial periods, compounding frequency, etc.). The yield on a par bond (Price=100) will equal the par coupon.  

In building a swap curve we will use par swaps and we will often measure risk w.r.t. the par swap rates. That is what we did in tables 7 and 9 above. But we can also think of the "yield" of a swap - more precisely the yield of a bond with the same fixed coupons and a final repayment of principal. The par yield will be the same as the par coupon (by definition) but the risk w.r.t. the par yield will not be quite the same as the risk w.r.t. the par coupon. The reason is that the derivative of the coupon and yield w.r.t. curve variables are different:  

$$
\frac{\partial p a r~c o u p o n}{\partial\nu_{i}}~\ne\frac{\partial p a r~y i e l d}{\partial\nu_{i}}
$$  

except for a flat yield curve. The difference arises because the yield calculation assumes a flat yield curve, while the par coupon calculation in equation (15) uses the forward curve.  

We can see the differences for our sample curve by comparing the Jacobians (9) for the par rates and par yields. Table 9,. repeated here, shows the derivatives of par swap rates w.r.t. curve parameters. Table 11 shows the derivatives of yields. For the 1 year swap the derivative of the par rate and the par yield are the same since the curve is flat between O and 1 years. The derivatives differ for the lon ger m aturity swaps.  

Table 9 (repeated) - Jacobian for Par Swap Rates (Equation 9)  

Table 11 - Jacobian for Par Swap Yields   


<html><body><table><tr><td colspan="4">f0yly fly2y</td></tr><tr><td>1 yr</td><td>Swap</td><td>1.01 0.</td><td>f2y5y 0.</td><td>f5y10y 0.</td></tr><tr><td>2yr</td><td>Swap</td><td>0.511 0.499</td><td>0.</td><td>0.</td></tr><tr><td></td><td></td><td>0.214 0.208</td><td>0.587</td><td>0.</td></tr><tr><td>5yr 10yr</td><td>Swap Swap</td><td>0.117 0.113</td><td>0.315</td><td>0.456</td></tr></table></body></html>  

<html><body><table><tr><td colspan="4">f0yly fly2y</td></tr><tr><td>1yr</td><td>Swap 1.01</td><td>0.</td><td>f2y5y 0.</td><td>f5y10y 0.</td></tr><tr><td>2yr</td><td>Swap</td><td>0.513 0.5</td><td>0.</td><td>0.</td></tr><tr><td></td><td></td><td>0.215 0.209</td><td>0.591</td><td>0.</td></tr><tr><td>5yr 10yr</td><td>Swap Swap</td><td>0.118 0.114</td><td>0.32</td><td>0.462</td></tr></table></body></html>  

This difference in derivatives gives a slight difference in transformed risk. The following table shows the original risk transformed to risk w.r.t. yields, and we can see that there are slight differences from the risk reported in table 10.  

Table 12 - Dv01 w.r.t. Par Swap Yields for Selected Instruments, Transformed via Equation 14  

<html><body><table><tr><td></td><td>lyr Swap</td><td>2yr Swap</td><td>5yr Swap</td><td>10yr Swap</td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td><td>0.</td><td>0.98</td></tr><tr><td>1 y2y Fwd</td><td>-0.99</td><td>1.95</td><td>0.</td><td>0.</td><td>0.96</td></tr><tr><td>5yr Swap</td><td>0.</td><td>0.</td><td>4.61</td><td>0.</td><td>4.61</td></tr><tr><td>10yr Swap</td><td>0.</td><td>0.</td><td>0.</td><td>8.38</td><td>8.38</td></tr><tr><td>2yr Swap</td><td>0.</td><td>1.94</td><td>0.</td><td>0.</td><td>1.94</td></tr><tr><td>3yr Swap</td><td>0.</td><td>1.27</td><td>1.59</td><td>0.</td><td>2.86</td></tr><tr><td>2yr Ann</td><td>0.02</td><td>0.04</td><td>0.</td><td>0.</td><td>0.06</td></tr><tr><td>10yr Ann</td><td>0.03</td><td>0.11</td><td>0.54</td><td>0.78</td><td>1.45</td></tr><tr><td>2yr Zero</td><td>-0.02</td><td>1.9</td><td>0.</td><td>0.</td><td>1.88</td></tr><tr><td>10yr Zero</td><td>-0.03</td><td>-0.11</td><td>-0.54</td><td>7.6</td><td>6.93</td></tr></table></body></html>  

DV01s are reported as dollar change for a $\$100$ notional instrument per 100bp change in yields or rates. Instruments used in fitting the surve are highlighted. The risk hereis w.r.t. yields on par bonds instead ofpar coupons. Transformed via equation (14)  

If we wish to calculate the risk w.r.t. par rates rather than yields we can employ equation (15) to get the derivative of the par coupon from price derivatives of instruments:.  

$$
\frac{\partial p a r~c o u p o n}{\partial\nu_{i}}=-\bigg[\frac{\partial\mathrm{PV}(\mathcal{S}l o O~a t~m a t u r i t y)}{\partial\nu_{i}}~+r\cdot\frac{\partial\mathrm{PV}(\mathcal{S}l~a n n u i t y)}{\partial\nu_{i}}\bigg]\bigg/\mathrm{PV}(\mathcal{S}l~a n n u i t y)
$$  

# Example of Partial Dv01 w.r.t. Zero Yields  

Now consider an example where our risk system cannot directly calculate the derivative of the rate or yield. Say that we wan! to calculate the risk w.r.t. yields for the following zero-coupon bonds:  

<html><body><table><tr><td>Maturity (yrs)</td><td>PV</td><td>Yield （%)</td><td>Yld DV01</td></tr><tr><td>1</td><td>98.03</td><td>2.</td><td>0.97</td></tr><tr><td>2</td><td>95.14</td><td>2.51</td><td>1.88</td></tr><tr><td>5</td><td>86.09</td><td>3.02</td><td>4.24</td></tr><tr><td>10</td><td>70.28</td><td>3.56</td><td>6.9</td></tr></table></body></html>  

Our risk system, however, can only calculate the derivatives of bond prices w.r.t. curve variables. The following table shows the derivative of prices w.r.t. curve variables (continuously-compounded forward rates):.  

Table 13 - Derivative of price w.r.t. Curve Variables (Forward Rates)  

0.98 0. 0. 0.  
0.951 0.951 0. 0.  
0.86 0.86 2.583 0.  
0.702 0.702 2.109 3.513  

We can use the yield $\begin{array}{r}{\mathrm{DV01}\left(\frac{d P}{d y}\right)}\end{array}$ shown above to get the inverse Jacobian of the zero yield, equation (13), shown in the following table:  

Table 14 - Jacobian for Zero Coupon Yields  

1.01 0. 0. 0.   
0.506 0.506 0. 0.   
0.203 0.203 0.609 0.   
0.102 0.102 0.305 0.509  

We can then use this to transform the original partial Dv01s w.r.t. forward rates shown in table 4 to Dv01s w.r.t. zero. coupon yields according to equation (14):  

Table 15 - Dv01 w.r.t. Zero-Coupon Yields for Selected Instruments, Transformed via Equation 14 )v01s are reported as dollar change for a $\$100$ notional instrument per 100bp change in yields orrates. Instruments used in fitting the :urve are highlighted. Transformed via equation (14).  

<html><body><table><tr><td></td><td>lyr Zero</td><td>2yr Zero</td><td>5yr Zero</td><td>10yr Zero</td><td></td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td><td></td><td>0.</td><td>0.98</td></tr><tr><td>1y2y Fwd</td><td>-0.96</td><td>1.92</td><td>0.</td><td>0.</td><td></td><td>0.96</td></tr><tr><td>5yr Swap</td><td>0.03</td><td>0.11</td><td>4.47</td><td>0.</td><td></td><td>4.61</td></tr><tr><td>10yr Swap</td><td>0.03</td><td>0.13</td><td>0.58</td><td>7.61</td><td></td><td>8.35</td></tr><tr><td>2yr Swap</td><td>0.02</td><td>1.91</td><td>0.</td><td>0.</td><td></td><td>1.94</td></tr><tr><td>3yr Swap</td><td>0.03</td><td>1.29</td><td>1.54</td><td>0.</td><td></td><td>2.86</td></tr><tr><td>2yr Ann</td><td>0.02</td><td>0.04</td><td>0.</td><td>0.</td><td></td><td>0.06</td></tr><tr><td>10yr Ann</td><td>0.03</td><td>0.13</td><td>0.58</td><td>0.71</td><td></td><td>1.45</td></tr><tr><td>2yr Zero</td><td>0.</td><td>1.88</td><td>0.</td><td>0.</td><td></td><td>1.88</td></tr><tr><td>10yr Zero</td><td>0.</td><td>0.</td><td>0.</td><td>6.9</td><td></td><td>6.9</td></tr></table></body></html>  

# Total Dv01 w .r.t. Different Rates  

The partial Dv01s can be summed to give a total Dv01, and this is displayed in the tables above. This total Dv01 is the sensitivity to a "parallel shift' in all the underlying rates. Examination of the tables shows, however, that the total Dv01 differs for different sets of rates. For example, the total Dv01 for the 10 year zero bond in table 15 (shift in all zero yields) is 6.91 while in table 12 (shift in all par yields) it is 6.93. For example, the total Dv01 for the 10 year par swap in table 5 (shift in cc forwards) is 8.49 while in table 12 (shift in all par yields) it is 8.38.  

The fact is that a parallel shift in one set of rates is not always parallel in another set of rates. It will be the same when the yield curve is flat and all rates use the same compounding, or if we work with zero and forward rates in the same compounding basis. When we work with a sloped curve and par rates or yields (i.e. instruments with intermediate coupons) a parallel shift in one set of rates will not be parallel in another. This is easiest to see using a simple example with forward rates and. yields on par bonds. Say the 0-5 year forward rate is flat at. $10.00\%\mathrm{sab}$ or $9.7580\%\mathrm{cc}$ . If rates are not in the same basis then a 1bp change in the continuously-compounded forward transats into a 1.05bp change in the sab par rate (sice d =e e/ 2), not a 1bp change in the par rate. When the forward rate is quoted semi-annual bond (rate of. $2\%$ ) then a 1bp sab change in. the forward does translate into a 1bp sab change in the par. But this will not carry out to longer maturities unless the curve is flat. If the 5- 10 year forward is $20\%$ sab (the 10 year par $13.2819\%\mathrm{sab}$ ) then a 1bp sab change in the forwards ( $10\%$ and $20\%$ to $10.01\%$ and $20.01\%$ translate into a 0.95bp change in the 10 year par yield (from $13.2819\%$ to $13.2914\%$ . In other words, a 1bp "parallel" shift in sab forwards translates into a non-parallel shift in sab pars:  

$$
\Delta{\left(\begin{array}{l}{0-5\mathrm{yr~fwd}}\ {5-10\mathrm{yr~fwd}}\end{array}\right)}=\left({\begin{array}{l}{1\mathrm{bp}}\ {1\mathrm{bp}}\end{array}}\right){\longleftrightarrow}\Delta{\left(\begin{array}{l}{5\mathrm{yr~par}}\ {10\mathrm{yr~par}}\end{array}\right)}=\left({\begin{array}{l}{1\mathrm{bp}}\ {0.95\mathrm{bp}}\end{array}}\right)
$$  

Fortunately the Jacobian and inverse Jacobian contain the information on how yields shift and the translation from one "parallel shift' to another. Say we are transforming from the original cc forward rates, $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ , to par yields, $\left(\begin{array}{l l l}{{y_{1}}}&{{\cdots}}&{{y_{k}}}\end{array}\right)$ . Taking the Jacobian and post-multiplying by a column vector of ones gives the change in $\left\{y_{i}\right\}$ corresponding to a parallel shift (one unit) in all the $\{\nu_{i}\}\mathrm{:~}$  

Change in $\left\{\begin{array}{l}{y_{i}}\end{array}\right\}$ due to parallel shift in $\{\nu_{i}\}=\left(\begin{array}{c c c}{{\frac{\partial y_{1}}{\partial\nu_{1}}}}&{{\cdots}}&{{\frac{\partial y_{1}}{\partial\nu_{k}}}}\ {{}}&{{}}&{{}}\ {{\vdots}}&{{\ddots}}&{{\vdots}}\ {{}}&{{}}&{{}}\ {{\frac{\partial y_{k}}{\partial\nu_{1}}}}&{{\cdots}}&{{\frac{\partial y_{k}}{\partial\nu_{k}}}}\end{array}\right)\cdot\left(\begin{array}{c}{{1}}\ {{\vdots}}\ {{1}}\end{array}\right)$  

while starting with the inverse Jacobian and post-multiplying gives the change in $\left\{\nu_{i}\right\}$ corresponding to a parallel shift (one. unit) in all the $\{y_{i}\}.$  

Change in $\left\{\nu_{i}\right\}$ due to parallel shift in $\{\mathbf{\phi}_{y_{i}}\}\mathbf{\Phi}=\left(\begin{array}{c c c}{\frac{\partial\nu_{1}}{\partial y_{1}}}&{\cdots}&{\frac{\partial\nu_{1}}{\partial y_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial\nu_{k}}{\partial y_{1}}}&{\cdots}&{\frac{\partial\nu_{k}}{\partial y_{k}}}\end{array}\right)\cdot\left(\begin{array}{c}{1}\ {\vdots}\ {1}\end{array}\right)$  

Consider again table 12. The original variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ are forward rates continuously-compounded while the alter-. nate yields $(\mathrm{~\boldmath~y~}_{1}\mathrm{~\boldmath~\beta~}\cdots\mathrm{~\boldmath~y~}_{k}\mathrm{~\boldmath~\beta~})$ are par yield semi-annually compounded. The change in the par yields due to a parallel shift in forwards and vice-versa are:.  

<html><body><table><tr><td colspan="4">Change in sab par yields CC fwds</td><td colspan="4">1 yr Par 2yr 1.01 1.0124</td><td colspan="4">Par 10yr Par 1.0145</td></tr><tr><td colspan="4">from parallel shift in</td><td colspan="4"></td><td colspan="4">1.0145</td></tr><tr><td></td><td></td><td></td><td>from</td><td></td><td>Oyly</td><td>fwd 1y2y</td><td>fwd</td><td>2y5y</td><td>fwd</td><td>5y10y</td><td>fwd</td></tr><tr><td</table></body></html>  

The top panel shows that a "paralll shift"' of 1bp in all forwards (continuously-compounded) implies a greater-than-1bp shift in par yields, with larger shifts at the longer end. These data also show that, because a "parallel shift' in one set of rates is not parallel in another, unless we restrict ourselves to zeros and forwards in the same compounding basis, there is no simple way to transform the "total Dv01' from one set of rates to another - we must use the transformation of equation (11) 0r (14).  

# Choice of AppropriateAlternate Variables  

The transformation technique is quite powerful, but we have to careful in choosing the alternate instruments and rates used in the transformation. There are some obvious restrictions on choosing alternative instruments, restrictions required to ensure the transformation works mathematically. Even when these conditions are satisfied, however, choosing rates that do not match the original curve can give odd results. We have to remember that the transformation approach tells us what the risk would be if we re-built and bumped our original curve with our alternate instruments. If we choose instruments that are not appropriate to our original curve we will get what appear to be odd results for the risk. The transformation approach. does not involve building a new curve - it is only a transformation of the original partial derivatives w.r.t. the original variables.  

First the obvious conditions. The transformation is effectively a coordinate transformation. The relation (13) or (12) must be invertible. There must be the same number of original variables. $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ and new yields $\left(\begin{array}{l l}{{y_{1}}}&{{\cdots}}\end{array}\begin{array}{l}{{y_{k}}}\end{array}\right)$ . In addition the Jacobian must be invertible, in other words the matrix in equation 9 must have non-zero determinant. These conditions. ensure that the transformation works mathematically..  

Even when the transformation works mathematically, however, it may not be well-behaved or make intuitive sense. The new.   
variables should match the original forward curve in the sense that they would be appropriate for building the original curve..   
For the examples discussed so far the set of alternate instruments have had the same maturities as the original input instru-.   
ments (1, 2, 5, and 10 years) ensuring that they match the original curve. In these cases the transformation has worked well and the old and new partial Dv01s measure the same risk from a different perspective. We will next turn to an example.   
where the new variables do not match the original curve, and the transformed risk looks peculiar..  

# Example of Transformation using Unsuitable Alternate Variables  

The forward curve used in the examples is shown in figure 2 above and is built with breaks at 1, 2, 5, and 10 years and forward rates from 0-1, 1-2, 2-5, and 5-10 years. This curve is consistent with instrument maturities at 1, 2, 5, and 10 years. Let us consider what would happen if, instead of using a 2 year swap we substituted a 3 year swap. We could build our original curve using the 3 year swap, but it is not really appropriate for a curve with a break at 2 and 5 years (and not at 3 years).  

The original curve produces risk that is reasonable, reasonable in the sense that instruments are not sensitive to long-. maturity rates when short-maturity rates are unchanged. Let us focus for now on 2 and 5 years. It is obvious that none of the 1 year swap, 1-2 year forward swap, 2 year swap, 2 year annuity, or 2 year zero should have sensitivity to the 2-5 year forward. rate, and looking back at table 5 verifies this. More importantly, transformations using instruments with maturity at 2 and 5 years have the same property. Looking at tables 7, 9, and 14 we see that these short-dated instruments have no sensitivity to 5. year rates, as long as the 1 and 2 year rates are held constant. The 3 year swap, of course, does have sensitivity to 5 year rates,  

holding the 2 year rate fixed.  

Consider now what would happen if we built our original curve (or transformed) using 3 and 5 year rates instead of 2 and 5 year rates. The curve is still built with 1-2 and 2-5 year forwards - our transformation approach does not involve building a new curve. Shifting the 5 year rate shifts the 2-5 year forward. When we transformed using a 2 year instrument the 1-2 year forward did not change since the 2 year instrument did not change. Using a 3 year instead of a 2 year rate, however, requires. shifting the 1-2 year forward to keep the 3 year rate unchanged. As a result a 2 year instrument will now have risk w.r.t. 5 year rates even when the 3 year rate is kept fixed.  

Table 16 shows the result of transforming a 1, 2, 5, 10 year curve using 1, 3, 5, and 10 year rates. Instruments with 2 year maturity now have risk w.r.t. 5 year rates, even when the 3 year rate is fixed. This is peculiar but it is correct - it is the result of trying to transform 2 year risk into 3 year risk rather than building a new curve with a 3 year instrument..  

Table 16 - Dv01 w.r.t. 1, 3, 5, 10 year Swap Rates for Selected Instruments, Transformed via Equation 11  

<html><body><table><tr><td></td><td>lyr Swap</td><td>3yr: Swap</td><td>5yr Swap</td><td>10yr Swap</td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td><td>0.</td><td>0.98</td></tr><tr><td>1 y2y Fwd</td><td>-0.99</td><td>4.41</td><td>-2.45</td><td>0.</td><td>0.96</td></tr><tr><td>5yr Swap</td><td>0.</td><td>0.</td><td>4.64</td><td>0.</td><td>4.64</td></tr><tr><td>10yr Swap</td><td>0.</td><td>0.</td><td>0.</td><td>8.49</td><td>8.49</td></tr><tr><td>2yr Swap</td><td>0.</td><td>4.39</td><td>-2.45</td><td>0.</td><td>1.94</td></tr><tr><td>3yr Swap</td><td>0.</td><td>2.87</td><td>0.</td><td>0.</td><td>2.87</td></tr><tr><td>2yr Ann</td><td>0.02</td><td>0.08</td><td>-0.05</td><td>0.</td><td>0.06</td></tr><tr><td>10yr Ann</td><td>0.03</td><td>0.24</td><td>0.41</td><td>0.79</td><td>1.46</td></tr><tr><td>2yr Zero</td><td>-0.03</td><td>4.31</td><td>-2.4</td><td>0.</td><td>1.88</td></tr><tr><td>10yr Zero</td><td>-0.03</td><td>-0.24</td><td>-0.41</td><td>7.7</td><td>7.03</td></tr></table></body></html>  

DV01s are reported as dollar change for a $\$100$ notional instrument per l00bp change in yields or rates. Instruments used in fitting the. curve are highlighted. Transformed via equation (11) to represent risk w.r.t. 1, 3, 5, and 10 year swaps, but based on a piece-wise constan! curve built with 1, 2, 5, and 10 year swaps.  

The transformation tells us what the risk of the original curve would be if we built the original curve with a 3 year swap, but it cannot tell us what the risk would be for a different curve - to do that we need to build a new curve. Our original curve was built using market instruments with maturities of 1, 2, 5, and 10 years. As a result, transforming using combinations of forwards, pars, zeros will work fine as long as they have maturities of 1, 2, 5, and 10 years. But trying to transform with a 3 year rate causes problems because the original curve is not set up for a 3 year instrument.  

Table 17 shows the risk we would get building a curve with 1, 3, 5, and 10 year instruments. Here the partial Dv01 for the 2 year is reasonable. Two year instruments have no sensitivity to the 5 year..  

Table 17 - Dv01 w.r.t. 1, 3, 5, 10 year Swap Rates for Selected Instruments, Calculated from Alternate Curve  

<html><body><table><tr><td></td><td>lyr Swap</td><td>3yr s Swap</td><td>5yr Swap</td><td>10yr Swap</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td><td>0.</td></tr><tr><td>1 y2y Fwd</td><td>-0.5</td><td>1.46</td><td>0.</td><td>0.</td></tr><tr><td>5yr Swap</td><td>0.</td><td>0.</td><td>4.63</td><td>0.</td></tr><tr><td>10yr Swap</td><td>0.</td><td>0.</td><td>0.</td><td>8.49</td></tr><tr><td>2yr Swap</td><td>0.48</td><td>1.46</td><td>0.</td><td>0.</td></tr><tr><td>3yr Swap</td><td>0.</td><td>2.87</td><td>0.</td><td>0.</td></tr><tr><td>2yr Ann</td><td>0.03</td><td>0.03</td><td>0.</td><td>0.</td></tr><tr><td>10yr Ann</td><td>0.04</td><td>0.16</td><td>0.48</td><td>0.79</td></tr><tr><td>2yr Zero</td><td>0.45</td><td>1.43</td><td>0.</td><td>0.</td></tr><tr><td>10yr Zero</td><td>-0.04</td><td>-0.16</td><td>-0.48</td><td>7.7</td></tr></table></body></html>  

DVo1s are reported as dollar change for a $\$100$ notional instrument per 1o0bp change in yields or rates. Instruments used in fitting the. curve are highlighted. Calculated by direct bumping ofthe curve inputs for a piece-wise constant curve built with 1, 3, 5, and 10 year swaps  

# DV01s w.r.t. Reduced Set of Variables- CompressingPartialDv01s  

So far we have been discussing transforming Dvo1s w.r.t. the original curve variables. $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ to DV01s w.r.t. the same number of alternate variables $\left(\begin{array}{l l l}{x_{1}}&{\cdots}&{x_{k}}\end{array}\right)$ . Another issue that often arises is the need to reduce the dimensionality or  

compress the Dv01s: transform to risk w.r.t. curve variables $\left(\begin{array}{l l l}{\nu_{1}^{*}}&{\cdots}&{\nu_{j}^{*}}\end{array}\right)$ or alternate variables $\left(\begin{array}{l l l}{x_{1}^{*}}&{\cdots}&{x_{j}^{*}}\end{array}\right)$ , where $j{<}k$ In our example we might want to express Dv01s w.r.t. a reduced set of $\{1$ year, 5 year, 10 year} swaps instead of the original {1 year, 2 year, 5 year, 10 year } swaps.  

# Details  

Rather than re-build a new curve and revalue the complete portfolio using this new curve, there are some simplifying. transformations we can apply. The transformations (6) or (9) will not work because the Jacobian (9) will not be full rank - it will not be square since $j<k$  

What we need is a matrix to transform from old variables to new variables:  

$$
\mathrm{DvDv^{*}~=M a t r i x~f o r~R e d u c e d~\rightarrow~C u r v e~V a r i a b l e s}=\left(\begin{array}{r r r}{{\frac{\partial\nu_{1}}{\partial\nu_{1}^{*}}}}&{{\cdots}}&{{\frac{\partial\nu_{k}}{\partial\nu_{j}^{*}}}}\ {{\vdots}}&{{\ddots}}&{{\vdots}}\ {{\frac{\partial\nu_{k}}{\partial\nu_{1}^{*}}}}&{{\cdots}}&{{\frac{\partial\nu_{k}}{\partial\nu_{j}^{*}}}}\end{array}\right)
$$  

If we had this matrix, we could simply write  

$\begin{array}{r}{\mathrm{DpDv}^{*}=\mathrm{Partial~DV0l~}w\mathrm{~.~}r\mathrm{~.~}t\mathrm{~.~Reduced~Variables}=\left(\begin{array}{c c c}{\frac{\partial P_{1}}{\partial\nu_{1}^{*}}}&{\cdots}&{\frac{\partial P_{1}}{\partial\nu_{j}^{*}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial P_{n}}{\partial\nu_{1}^{*}}}&{\cdots}&{\frac{\partial P_{n}}{\partial\nu_{j}^{*}}}\end{array}\right)=\mathrm{DpDv}\mathrm{~.~DvDv}^{*}=\mathrm{~Part~}\cdot\frac{\partial P_{1}}{\partial\nu_{1}^{*}}}\end{array}$ $\begin{array}{r}{\mathrm{Derivative}{\emph{w}},r,t\cdot\mathrm{Curve}\mathrm{Variables}*\mathrm{ReducedMatrix}=\left(\begin{array}{c c c}{\frac{\partial P_{1}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial P_{1}}{\partial\nu_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial P_{r}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial P_{n}}{\partial\nu_{k}}}\end{array}\right)+\left(\begin{array}{c c c}{\frac{\partial\nu_{1}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial\nu_{1}}{\partial\nu_{j}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial\nu_{k}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial\nu_{k}}{\partial\nu_{j}}}\end{array}\right)}\end{array}$  

The transformation matrix (16) cannot be obtained from the original curve. Instead we need to build a new curve, using a. reduced set of curve variables. We do not, however, need to revalue the whole portfolio using this new curve. All we need is the matrix of derivatives in equation (16), relating the old and new curve variables. Generally, however, we cannot conveniently calculate (16) directly so we will use a set of "intermediate instruments" that we can value using both the old and new cur ve.  

We start with the set of intermediate instruments $\left(\begin{array}{l l l}{x_{1}}&{\cdots}&{x_{k}}\end{array}\right)$ for the original curve. First we get the inverse Jacobial (equation 10) by calculating the derivative w.r.t. the original curve variables:  

$$
\mathrm{DvDx}=\left(\begin{array}{c c c}{\frac{\partial\nu_{1}}{\partial x_{1}}}&{\cdots}&{\frac{\partial\nu_{1}}{\partial x_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial\nu_{k}}{\partial x_{1}}}&{\cdots}&{\frac{\partial\nu_{k}}{\partial x_{k}}}\end{array}\right)=\left(\begin{array}{c c c}{\frac{\partial x_{1}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial x_{1}}{\partial\nu_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial x_{k}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial x_{k}}{\partial\nu_{k}}}\end{array}\right)^{-1}
$$  

Next we use the new curve and calculate the derivative of these intermediate instruments w.r.t. the new curve variables:  

$$
\begin{array}{r}{\mathrm{DxDv}^{*}=\left(\begin{array}{c c c}{\frac{\partial x_{1}}{\partial\nu_{1}}}&{\hdots}&{\frac{\partial x_{1}}{\partial\nu_{j}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial x_{k}}{\partial\nu_{1}^{*}}}&{\hdots}&{\frac{\partial x_{k}}{\partial\nu_{j}^{*}}}\end{array}\right)}\end{array}
$$  

Finally, for the new curve variables. $\left(\begin{array}{l l l}{\nu_{1}^{*}}&{\cdots}&{\nu_{j}^{*}}\end{array}\right)$ and the new alternate instruments $\left(\begin{array}{l l l}{x_{1}^{*}}&{\cdots}&{x_{j}^{*}}\end{array}\right)$ or their yields $\left(\begin{array}{l l l}{{y_{1}^{*}}}&{{\cdots}}&{{y_{j}^{*}}}\end{array}\right)$ we calculate the inverse Jacobian as in (10) or (13):  

$$
\scriptstyle\mathrm{{Dv^{*}~D x^{*}}}=\left({\begin{array}{c c c}{{\frac{\partial{\nu_{1}^{*}}}{\partial{x_{1}^{*}}}}}&{{\dots}}&{{\frac{\partial{\nu_{1}^{*}}}{\partial{x_{j}^{*}}}}}\ {{\vdots}}&{{\ddots}}&{{\vdots}}\ {{\frac{\partial{\nu_{j}^{*}}}{\partial{x_{1}^{*}}}}}&{{\dots}}&{{\frac{\partial{\nu_{j}^{*}}}{\partial{x_{j}^{*}}}}}\end{array}}\right)=\left({\begin{array}{c c c}{{\frac{\partial{x_{1}^{*}}}{\partial{\nu_{1}^{*}}}}}&{{\dots}}&{{\frac{\partial{x_{1}^{*}}}{\partial{\nu_{j}^{*}}}}}\ {{\vdots}}&{{\ddots}}&{{\vdots}}\ {{\frac{\partial{x_{j}^{*}}}{\partial{\nu_{1}^{*}}}}}&{{\dots}}&{{\frac{\partial{x_{j}^{*}}}{\partial{\nu_{j}^{*}}}}}\end{array}}\right)^{-1}
$$  

$$
\begin{array}{r}{\mathrm{Dv^{*}~D y^{*}}=\left(\begin{array}{c c c}{\left(\frac{d x_{1}^{*}}{d y_{1}^{*}}\right)^{-1}\frac{\partial x_{1}^{*}}{\partial\nu_{1}^{*}}}&{\cdots}&{\left(\frac{d x_{1}^{*}}{d y_{1}^{*}}\right)^{-1}\frac{\partial x_{1}^{*}}{\partial\nu_{j}^{*}}}\ {\vdots}&{\ddots}&{\vdots}\ {\left(\frac{d x_{j}^{*}}{d y_{j}^{*}}\right)^{-1}\frac{\partial x_{j}^{*}}{\partial\nu_{1}^{*}}}&{\cdots}&{\left(\frac{d x_{j}^{*}}{d y_{j}^{*}}\right)^{-1}\frac{\partial x_{j}^{*}}{\partial\nu_{j}^{*}}}\end{array}\right)^{-1}}\end{array}
$$  

Ve can now combine these all to transform the partial Dv01s w.r.t. the original curve variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ into DV01s v.r.t. yields of the new instruments and the new curve $\left(\begin{array}{l l l}{\boldsymbol{y}_{1}^{*}}&{\cdots}&{\boldsymbol{y}_{j}^{*}}\end{array}\right)$  

Partial DV01s $w\mathrm{~.~}r\mathrm{~.~}t$ . Reduced Variables (via yield function) $=$  

$$
\begin{array}{r}{\mathrm{DpDy^{*}}=\left(\begin{array}{c c c}{\frac{\partial P_{1}}{\partial y_{1}^{*}}}&{\cdots}&{\frac{\partial P_{1}}{\partial y_{j}^{*}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial P_{n}}{\partial y_{1}^{*}}}&{\cdots}&{\frac{\partial P_{n}}{\partial y_{j}}}\end{array}\right)=\mathrm{DpDv}\mathrm{~.~DvDx~.~DxDv~^*~}\cdot\mathrm{Dv^{*}~D y^{*}~}=\frac{1}{\frac{\partial P_{1}}{\partial P_{2}}}\mathrm{~.~}}\end{array}
$$  

$$
\left(\begin{array}{c c c}{\frac{\partial P_{1}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial P_{1}}{\partial\nu_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial P_{n}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial P_{n}}{\partial\nu_{k}}}\end{array}\right)\left(\begin{array}{l l l}{\frac{\partial x_{1}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial x_{1}}{\partial\nu_{k}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial x_{k}}{\partial\nu_{1}}}&{\ldots}&{\frac{\partial x_{k}}{\partial\nu_{k}}}\end{array}\right)^{-1}\left(\begin{array}{l l l}{\frac{\partial x_{1}}{\partial\nu_{1}^{*}}}&{\ldots}&{\frac{\partial x_{1}}{\partial\nu_{j}^{*}}}\ {\vdots}&{\ddots}&{\vdots}\ {\frac{\partial x_{k}}{\partial\nu_{1}^{*}}}&{\ldots}&{\frac{\partial x_{k}}{\partial\nu_{j}^{*}}}\end{array}\right)\left(\left(\begin{array}{l l l}{\frac{d x_{1}^{*}}{d y_{1}^{*}}}\ {\vdots}&{\frac{\partial x_{1}^{*}}{\partial\nu_{1}^{*}}}&{\cdots}&{\left(\frac{d x_{1}^{*}}{d y_{1}^{*}}\right)^{-1}\frac{x_{1}^{*}}{\partial\nu_{j}^{*}}}\ {\vdots}&{\vdots}&{\ddots}&{\vdots}\ {\frac{d x_{j}^{*}}{d y_{1}^{*}}}&{\ldots}&{\frac{\partial x_{j}}{\partial\nu_{j}^{*}}}\end{array}\right)\left(\begin{array}{l l l}{\frac{d x_{1}^{*}}{\partial\nu_{1}^{*}}}&{\ldots}&{\frac{\partial x_{1}^{*}}{\partial\nu_{j}^{*}}}\ {\vdots}&{\vdots}&{\ddots}&{\vdots}\ {\frac{d x_{j}^{*}}{d y_{j}^{*}}}&{\ldots}&{\frac{\left(d x_{j}^{*}}{d y_{j}^{*}}\right)^{-1}\frac{\partial x_{j}^{*}}{\partial\nu_{j}^{*}} 
$$  

This looks very complicated, but in fact it is not. Each of the intermediate steps is a relatively straightforward risk calculation for a small number of instruments:  

The matrix DpDv is the original risk w.r.t. the original curve variables. This is what we are trying to transform and is give. a priori.   
The matrix DvDx is (the inverse of) the price Jacobian (14) for the "intermediate instruments' from the original curve and will be the risk of a small portfolio of traded instruments.   
The matrix DxDv \* is the derivative of the intermediate instruments using the new curve   
The matrix Dv $^{*}\mathrm{D}\mathrm{y}^{*}$ is the inverse Jacobian in yield terms, equation (13), for the new yields using the new curve  

# Example using 1, 5, 10 Year Sw aps  

Our original curve is based on swaps or futures with breaks at 1, 2, 5, and 10 years. Our original partial Dv01s are shown in table 5, and in table 9 we transformed it to risk w.r.t. par swaps. Say that we want to express the risk w.r.t. fewer swaps, effectively to compress the risk. Say we want to dispense with the 2 year swap and express the risk w.r.t. 1, 5, and 10 year swaps. We cannot simply combine the risk of adjacent categories, we need to have a transformation rule such as in equation (18).  

Our original curve has breaks at 1, 2, 5, and 10 years and is built with instruments that have maturities at these dates. Let us build a reduced curve with fewer parameters, in this case piece-wise constant with breaks at 1, 5, and 10 years. Let us build the curve so that it re-prices the 1, 5, and 10 year swaps:  

<html><body><table><tr><td>Maturity (yrs)</td><td>Fixed Rate (%)</td><td>Fitted Fwd</td></tr><tr><td>1</td><td>2</td><td>0.0199</td></tr><tr><td>5</td><td>3</td><td>0.0324</td></tr><tr><td>10</td><td>3.5</td><td>0.0406</td></tr></table></body></html>  

Figure 3 shows the original curve and the reduced or compressed curve.  

![](7432f8badc792e2554303b3d5c085b314b50814bc8fac4a798299b2ae4fe8cf3.jpg)  
Figure 3 - Piece-Wise Constant Forward Curve, Original and Reduced   
Solid is Original Curve. Dashed is Without 2yr Swap  

For our "intermediate instruments" we will use the set of 1, 2, 5, and 10 year swaps. Using the original curve we can calculate the inverse Jacobian DvDx for these intermediate instruments:  

<html><body><table><tr><td></td><td>1 yr Swap</td><td>2yr Swap</td><td>5yr Swap</td><td>10yr</td><td>Swap</td></tr><tr><td>f0yly</td><td>1.006</td><td>0.</td><td>0.</td><td>0.</td><td></td></tr><tr><td>fly2y</td><td>-1.031</td><td>1.032</td><td>0.</td><td></td><td>0.</td></tr><tr><td>f2y5y</td><td>-0.002</td><td>-0.365</td><td>0.367</td><td></td><td>0.</td></tr><tr><td>f5y10y</td><td>-0.001</td><td>-0.003</td><td>-0.254</td><td></td><td>0.258</td></tr></table></body></html>  

Using the new curve we can calculate derivative of these intermediate instruments using the new curve, DxDv \*:  

<html><body><table><tr><td colspan="2"></td><td>f0yly</td><td>fly5y f5y10y</td></tr><tr><td>1yr</td><td>Swap</td><td>0.994 0.</td><td>0.</td></tr><tr><td>2yr</td><td>Swap</td><td>0.991 0.966</td><td>0.</td></tr><tr><td>5yr</td><td>Swap 0.992</td><td>3.686</td><td>0.</td></tr><tr><td>10yr</td><td>Swap 0.991</td><td>3.633</td><td>3.874</td></tr></table></body></html>  

We then calculate the derivative of our new set of swaps (1, 5, 10 years) from the new curve, the matrix $\mathrm{Dx}^{\ast}\mathrm{Dv}^{\ast}$ , and the vector of yield DV01s:  

f0yly f1y5y f5y10y   
1yr Swap 0.994 0. 0.   
5yr Swap 0.992 3.686 0.   
10yr Swap 0.991 3.633 3.874   
1yr Swap 5yr Swap 10yr Swap   
0.984527 4.6105 8.3755  

and from these we can calculate the inverse yield Jacobian for the new yields and new curve Dv $^{\ast}\mathrm{D}\mathrm{y}^{\ast}$ (equation 17):  

<html><body><table><tr><td>1 yr</td><td>Swap 5yr</td><td>Swap</td><td>10yr Swap</td></tr><tr><td>f0yly</td><td>0.99</td><td>0.</td><td>0.</td></tr><tr><td>fly5y</td><td>-0.266</td><td>1.251</td><td>0.</td></tr><tr><td>f5y10y</td><td>-0.003</td><td>-1.173</td><td>2.162</td></tr></table></body></html>  

Combining these gives the transformation matrix DvDx . DxDv \* . Dv \*Dy \* he following table shows the result of applying this transformation (per equation 18) to the original risk from table 5:  

<html><body><table><tr><td>1 yr</td><td>Swap 5yr</td><td>Swap</td><td>10yr Swap</td></tr><tr><td>f0yly</td><td>0.99</td><td>0.</td><td>0.</td></tr><tr><td>fly2y</td><td>-0.268</td><td>1.248</td><td>0.</td></tr><tr><td>f2y5y</td><td>-0.266</td><td>1.252</td><td>0.</td></tr><tr><td>f5y10y</td><td>-0.003</td><td>-1.173</td><td>2.162</td></tr></table></body></html>  

Table 18 - Compressed Dv01 w.r.t. Par Swap Yields for Selected Instruments  

<html><body><table><tr><td></td><td>lyrs Swap</td><td>5yr: Swap</td><td>10yr Swap</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td></tr><tr><td>1 y2y Fwd</td><td>-0.26</td><td>1.21</td><td>0.</td></tr><tr><td>5yr Swap</td><td>0.</td><td>4.61</td><td>0.</td></tr><tr><td>10yr Swap</td><td>0.</td><td>0.</td><td>8.38</td></tr><tr><td>2yr Swap</td><td>0.72</td><td>1.21</td><td>0.</td></tr><tr><td>3yr Swap</td><td>0.47</td><td>2.38</td><td>0.</td></tr><tr><td>2yr Ann</td><td>0.04</td><td>0.02</td><td>0.</td></tr><tr><td>10yr Ann</td><td>0.07</td><td>0.61</td><td>0.78</td></tr><tr><td>2yr Zero</td><td>0.69</td><td>1.19</td><td>0.</td></tr><tr><td>10yr Zero</td><td>-0.07</td><td>-0.61</td><td>7.6</td></tr></table></body></html>  

DV01s are reported as dollar change for a $\$100$ notional instrument per l00bp change in yields orrates. The risk is compressed from tha shown in table 4 using equation (18)  

Comparing this with table 12 we see that the risk for the 5 year and 10 year swaps is unchanged - as we should expect. The risk of the 2 year swap, however, is now distributed between the 1 year and 5 year swaps. The distribution depends on the particular functional form chosen for the forward curve. The matrices. $\mathrm{DxDv}^{*}$ and DvDx together tell us how the original. cur ve variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ change when the compressed curve variables $\left(\begin{array}{l l l}{\nu_{1}^{*}}&{\cdots}&{\nu_{j}^{*}}\end{array}\right)$ change. This depends on the functional form of both curves, and requires the information embedded in these two matrices. Choosing a different functional form for the curve will lead to a different distribution of risk between the 1 year and 5 year swaps.  

# Alternate Forward Curves  

All examples so far have used a piece-wise constant forward curve but none of the results are limited to this functional form. Although a piece-wise constant forward curve is a robust, simple, useful functional form to use in market applications it is by no means the only possible curve. One popular alternative is piece-wise linear zero, where continuously-compounded zero rates are linearly-interpolated between break points. The curve variables $\left(\begin{array}{l l l}{\nu_{1}}&{\cdots}&{\nu_{k}}\end{array}\right)$ are zero rates at the break points: in this case (zero 1yr, zero 2yr, zero 5yr, zero 10yr). Figure 4 shows the fitted zero rates and forward rates..  

![](d51a8770f7b0b089a54602a23aa61e5ebe0798f9f180532a4e0f8a47d2c0081a.jpg)  
Figure 4 - Piece-Wise Linear Zero Curve  

e can calculate the derivatives of instruments w.r.t. the curve parameters, just as we did in table 5 above. In this case the risk is w.r.t. continuously-compounded zero rates. The following table shows the risk w.r.t. the curve variables, on other words w.r.t. zero rates.  

Table 19 - Dv01 w.r.t. Zero Yields (cc) for Selected Instruments   


<html><body><table><tr><td></td><td>zly</td><td>z2y</td><td>z5y</td><td>z10y</td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.99</td><td>0.</td><td>0.</td><td>0.</td><td>0.99</td></tr><tr><td>1y2y Fwd</td><td>-0.97</td><td>1.94</td><td>0.</td><td>0.</td><td>0.97</td></tr><tr><td>5yr Swap</td><td>0.03</td><td>0.15</td><td>4.5</td><td>0.</td><td>4.68</td></tr><tr><td>10yr Swap</td><td>0.04</td><td>0.17</td><td>0.65</td><td>7.63</td><td>8.49</td></tr><tr><td>2yr Swap</td><td>0.03</td><td>1.93</td><td>0.</td><td>0.</td><td>1.96</td></tr><tr><td>3yr Swap</td><td>0.03</td><td>1.94</td><td>0.94</td><td>0.</td><td>2.91</td></tr><tr><td>2yr Ann</td><td>0.03</td><td>0.03</td><td>0.</td><td>0.</td><td>0.06</td></tr><tr><td>10yr Ann</td><td>0.04</td><td>0.17</td><td>0.65</td><td>0.61</td><td>1.47</td></tr><tr><td>2yr Zero</td><td>0.</td><td>1.9</td><td>0.</td><td>0.</td><td>1.9</td></tr><tr><td>10yr Zero</td><td>0.</td><td>0.</td><td>0.</td><td>7.02</td><td>7.02</td></tr></table></body></html>  

DV01s are reported as dollar change for a $\$100$ notional instrument per l00bp change in yields or rates. Risk is w.r.t. continuouslycompounded zero rates. Instruments used in fitting the curve are highlighted.  

Next, we can transform to risk w.r.t. par swap yields by calculating the Jacobian and inverse Jacobians (equation 13). The following table shows the Jacobian, the derivatives of par swap yields w.r.t. zero curve variables. This should be compared with table 11 which shows the Jacobian for the same par swap yields but w.r.t. forward curve variables. Applying the transfor-. mation gives the data in the table below..  

Table 20 - Jacobian for Par Swap Yields (Equation 9) for Transformation from Zero Curve Risk  

Table 21 - Dv01 w.r.t. Par Swap Yields for Selected Instruments   


<html><body><table><tr><td></td><td>zly</td><td>z2y</td><td>z5y</td><td>z10y</td></tr><tr><td>l yr</td><td>Swap</td><td>1.01 0.</td><td>0.</td><td>0.</td></tr><tr><td>2yr</td><td>Swap</td><td>0.014 0.998</td><td>0.</td><td>0.</td></tr><tr><td>5yr</td><td>Swap</td><td>0.007 0.032</td><td>0.975</td><td>0.</td></tr><tr><td>10yr</td><td>Swap</td><td>0.005 0.021</td><td>0.078</td><td>0.911</td></tr></table></body></html>  

<html><body><table><tr><td></td><td>lyr Swap</td><td>2yr Swap</td><td>5yr Swap</td><td>10yr Swap</td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td><td>0.</td><td>0.98</td></tr><tr><td>1 y2y Fwd</td><td>-0.99</td><td>1.94</td><td>0.</td><td>0.</td><td>0.96</td></tr><tr><td>5yr Swap</td><td>0.</td><td>0.</td><td>4.61</td><td>0.</td><td>4.61</td></tr><tr><td>10yr Swap</td><td>0.</td><td>0.</td><td>0.</td><td>8.38</td><td>8.38</td></tr><tr><td>2yr Swap</td><td>0.</td><td>1.94</td><td>0.</td><td>0.</td><td>1.94</td></tr><tr><td>3yr Swap</td><td>0.</td><td>1.91</td><td>0.96</td><td>0.</td><td>2.87</td></tr><tr><td>2yr Ann</td><td>0.03</td><td>0.03</td><td>0.</td><td>0.</td><td>0.06</td></tr><tr><td>10yr Ann</td><td>0.03</td><td>0.14</td><td>0.62</td><td>0.67</td><td>1.45</td></tr><tr><td>2yr Zero</td><td>-0.03</td><td>1.9</td><td>0.</td><td>0.</td><td>1.88</td></tr><tr><td>10yr Zero</td><td>-0.03</td><td>-0.14</td><td>-0.62</td><td>7.71</td><td>6.92</td></tr></table></body></html>  

DV01s are reported as dollar change for a $\$100$ notional instrument per lo0bp change in yields orrates. Risk is w.r.t. par bond. $/$ swap yields, transformed from zero curve risk. Instruments used in fitting the curve are highlighted.  

Ne can also compare the zero and par risk calculated here with the zero and par risk shown in tables 15 and 12 above. Close xamination shows that there are some differences. These differences arise from two sources:  

First, for the zero risk the rates are compounded on a different basis. The curve variables in table 21 are continuouslycompounded while the yields for the instruments used in table 15 are semi-annually compounded. The conversion between risk expressed in different compounding bases depends on (1+rate):.  

$$
1+y_{\mathrm{sab}}/2=\exp(y_{\mathrm{cc}}/2)\Rightarrow\frac{d y_{\mathrm{sab}}}{d y_{\mathrm{cc}}}=\exp(y_{\mathrm{cc}}/2)=1+y_{\mathrm{sab}}/2
$$  

The 10 year zero rate $y_{\mathrm{sab}}$ is $3.56\%$ so the conversion factor for 10 year rates is 1.0178. If we take the risk for the 10 year zero bond from table 21 and divide by 1.0178 we get the value shown in table 15 - in other words the difference for the 10 year zero bond is totally due to differences in compounding between tables 15 and 21..  

The par risk in tables 23 and 12 are quoted on the same basis (both semi-bond) so there are no compounding. differences. Comparing the tables shows that the risk for swaps used in building the curve (1, 2, 5, 10 year) are the same. But risk for instruments not used in building the curve are different. For example the total risk for the 3 year swap is roughly the same, but the distribution, across the 2 year versus 5 year, is different. The reason is that the curves are fundamentally different and they imply different movements in forward rates between knot points. The 5 year swap, for example, has most of its cash flows and sensitivity concentrated at the 5 year point, and both curves, having the 5 year swap as an input, are constrained to have roughly the same 5 year zero and par rates. The risk for the 5 year swap will be virtually the same. The curves are not constrained to be the same at 3 years however, and changes in the 2 year or 5 year. input swaps will change the 3 year zero and 3 year par rates quite differently between the curves. How the 3 year swap. responds to changes in the 2 year and 5 year rates will be different between the curves..  

# Conclusion  

This paper has laid out a simple method to transform curve risk or sensitivity from one set of rates or yields to another. The method is quite general and allows transformations between arbitrary instruments, subject to certain constraints. The method can also be used to compress risk from a larger to a smaller number of variables.  

# APPENDIX - Dynamic Interactivity  

# Introduction  

his paper was written in Wolfram's Mathematica and all the tables generated dynamically. This appendix provides interacive exploration of the transformation methodology by making some of the tables dynamically interactive.  

If you are reading the pdf version of this paper the tables are clearly not interactive - they are simply static graphics. For interactivity you must use the .cdf/ nbp version, which is available at www.closemountain.com/publications.htm1#RiskManagement  

Wolfram has developed a platform for enhanced digital publication - documents saved in Computable Document Format (.cdf) or player format (.nbp) can then be "read" using the Wolfram Player (free download available at. http:/ / www.wolfram.com/ products/ player/). This is analogous to Adobe's .pdf format with the Acrobat Reader but extends the idea to dynamic interactivity. A.cdf document can be computable and can produce dynamic content, responding to readers' input.  

In the .cdf/ .nbp version the reader can choose the instruments for reporting the partial Dv01s in the table below and then the transformed risk (together with the Jacobian and inverse Jacobian) will be re-calculated and displayed. There is a "portfolio" of twenty securities, including swaps, annuities, zeros bonds, and forwards:  

Table A1 - Securities Available for Interactive Examination  

<html><body><table><tr><td>Instrument</td><td>Forward Start</td><td>Underlier (yrs)</td><td>Coupon Rate （%)</td><td>PV</td></tr><tr><td>1yr Swap</td><td>0</td><td>1</td><td>2.</td><td>0.</td></tr><tr><td>2yr Swap</td><td>0</td><td>2</td><td>2.5</td><td>0.</td></tr><tr><td>3yr Swap</td><td>0</td><td>3</td><td>2.8</td><td>0.063</td></tr><tr><td>5yr Swap</td><td>0</td><td>5</td><td>3.</td><td>0.</td></tr><tr><td>10yr Swap</td><td>0</td><td>10</td><td>3.5</td><td>0.</td></tr><tr><td>1yr Ann</td><td>0</td><td>1</td><td>2.</td><td>1.969</td></tr><tr><td>2yr Ann</td><td>0</td><td>2</td><td>2.5</td><td>4.856</td></tr><tr><td>3yr Ann</td><td>0</td><td>3</td><td>3.</td><td>8.61</td></tr><tr><td>5yr  Ann</td><td>0</td><td>5</td><td>3.</td><td>13.91</td></tr><tr><td>10yr Ann</td><td>0</td><td>10</td><td>3.5</td><td>29.724</td></tr><tr><td>lyr Zero</td><td>0</td><td>1</td><td>0.</td><td>98.031</td></tr><tr><td>2yr Zero</td><td>0</td><td>2</td><td>0.</td><td>95.144</td></tr><tr><td>3yr Zero</td><td>0</td><td>3</td><td>0.</td><td>92.027</td></tr><tr><td>5yr Zero</td><td>0</td><td>5</td><td>0.</td><td>86.09</td></tr><tr><td>10yr Zero</td><td>0</td><td>10</td><td>0.</td><td>70.276</td></tr><tr><td>1y2y Fwd</td><td>1</td><td>1</td><td>3.014</td><td>0.</td></tr><tr><td>2y5y Fwd</td><td>2</td><td>3</td><td>3.36</td><td>0.</td></tr><tr><td>3y5y Fwd</td><td>3</td><td>2</td><td>3.</td><td>-0.637</td></tr><tr><td>5y10y Fwd</td><td>5</td><td>5</td><td>4.101</td><td>0.</td></tr><tr><td>7y10y Fwd</td><td>7</td><td>3</td><td>3.5</td><td>-1.335</td></tr></table></body></html>  

Instruments used in fitting the curve are highlighted.  

Apiece-wise constant forward curve is used for valuation, fitted using the following four instruments:  

Table A2 - Market Instrument Used for Building Sample Curve  

<html><body><table><tr><td>Instrument</td><td>Maturity (yrs)</td><td>Coupon Rate (%)</td><td>Fwd Rate</td></tr><tr><td>1yr Swap</td><td>1</td><td>2.</td><td>0.0199</td></tr><tr><td>1 y2y Fwd</td><td>1</td><td>3.014</td><td>0.0299</td></tr><tr><td>5yr Swap</td><td>5</td><td>3.</td><td>0.0333</td></tr><tr><td>10yr Swap</td><td>10</td><td>3.5</td><td>0.0406</td></tr></table></body></html>  

![](fd99e311622bff439f9a55882220291f39342f674f31ad50428e23c6a6cf0167.jpg)  
Figure A1 - Piece-Wise Constant Forward Curve  

The partial Dv01s for all the instruments, calculated from the piece-wise constant forward curve, is shown in the following :able. The Dv01s are derivatives w.r.t. continuously-compounded forward rates (the parameters of the curve above).  

Table A3 - Dv01 w.r.t. Curve Variables (Forward Rates) for Selected Instruments  

<html><body><table><tr><td></td><td>f0yly</td><td>fly2y</td><td>f2y5y</td><td>f5y10y</td><td>Total</td></tr><tr><td>1 yr Swap</td><td>0.99</td><td>0.</td><td>0.</td><td>0.</td><td>0.99</td></tr><tr><td>2yr Swap</td><td>0.99</td><td>0.97</td><td>0.</td><td>0.</td><td>1.96</td></tr><tr><td>3yr Swap</td><td>0.99</td><td>0.97</td><td>0.94</td><td>0.</td><td>2.9</td></tr><tr><td>5yr Swap</td><td>0.99</td><td>0.96</td><td>2.72</td><td>0.</td><td>4.68</td></tr><tr><td>10yr Swap</td><td>0.99</td><td>0.96</td><td>2.68</td><td>3.87</td><td>8.5</td></tr><tr><td>1yr Ann</td><td>0.01</td><td>0.</td><td>0.</td><td>0.</td><td>0.01</td></tr><tr><td>2yr Ann</td><td>0.04</td><td>0.02</td><td>0.</td><td>0.</td><td>0.06</td></tr><tr><td>3yr Ann</td><td>0.08</td><td>0.05</td><td>0.02</td><td>0.</td><td>0.15</td></tr><tr><td>5yr  Ann</td><td>0.13</td><td>0.1</td><td>0.14</td><td>0.</td><td>0.37</td></tr><tr><td>10yr Ann</td><td>0.29</td><td>0.25</td><td>0.57</td><td>0.36</td><td>1.47</td></tr><tr><td>lyr Zero</td><td>0.98</td><td>0.</td><td>0.</td><td>0.</td><td>0.98</td></tr><tr><td>2yr Zero</td><td>0.95</td><td>0.95</td><td>0.</td><td>0.</td><td>1.9</td></tr><tr><td>3yr Zero</td><td>0.92</td><td>0.92</td><td>0.92</td><td>0.</td><td>2.76</td></tr><tr><td>5yr Zero</td><td>0.86</td><td>0.86</td><td>2.58</td><td>0.</td><td>4.3</td></tr><tr><td>10yr Zero</td><td>0.7</td><td>0.7</td><td>2.11</td><td>3.51</td><td>7.03</td></tr><tr><td>1y2y Fwd</td><td>0.</td><td>0.97</td><td>0.</td><td>0.</td><td>0.97</td></tr><tr><td>2y5y Fwd</td><td>0.</td><td>0.</td><td>2.74</td><td>0.</td><td>2.74</td></tr><tr><td>3y5y Fwd</td><td>-0.01</td><td>-0.01</td><td>1.78</td><td>0.</td><td>1.77</td></tr><tr><td>5y10y Fwd</td><td>0.</td><td>0.</td><td>0.</td><td>3.93</td><td>3.93</td></tr><tr><td>7y10y Fwd</td><td>-0.01</td><td>-0.01</td><td>-0.04</td><td>2.22</td><td>2.15</td></tr></table></body></html>  

DV0ls are reported as dollar change for a. $\$100$ notional instrument per lo0bp change in yields orrates. Curve variables are continuously compounded forward rates. Instruments used in fitting the curve are highlighted..  

# DynamicInteractivity  

If you are reading the .pdf version of this paper the tables are clearly not interactive - they are simply static graphics. For interactivity you must use the .cdf/ .nbp version, which is available at www.closemountain.com/publications.htm1#RiskManagement  

# Duration and Dv01 for Yield-to-Maturity  

Table A4 shows the Dvo1, modified duration, and Macaulay duration for a sub-set of the securities above. These are calculated based on each security's yield-to-maturity separately, rather than based on the yield curve presented above. Below the table is a figure illustrating the Macaulay duration for the first security in the table. The reader can use the menus to select which securities are displayed in the table.  

Table A4 - Dv01 w.r.t. Curve Variables (Forward Rates) for Selected Instruments  

![](c48003a33b382edda1397480d7903a23dcf7cb23c36180d27f2f540f29f112ec.jpg)  

<html><body><table><tr><td>Instrument</td><td>Coupon （%)</td><td>Price</td><td>Yield （%)</td><td>DV01</td><td>Mod Dur</td><td>Mac Dur</td></tr><tr><td>2yr Bond</td><td>2.5</td><td>100.</td><td>2.5</td><td>1.94</td><td>1.94</td><td>1.96</td></tr><tr><td>10yr Bond</td><td>3.5</td><td>100.</td><td>3.5</td><td>8.38</td><td>8.38</td><td>8.52</td></tr><tr><td>2yr Ann</td><td>2.5</td><td>4.86</td><td>2.3</td><td>0.06</td><td>1.23</td><td>1.24</td></tr><tr><td>10yr Ann</td><td>3.5</td><td>29.72</td><td>3.22</td><td>1.46</td><td>4.91</td><td>4.98</td></tr><tr><td>2yr Zero</td><td>0.</td><td>95.14</td><td>2.51</td><td>1.88</td><td>1.97</td><td>2.</td></tr><tr><td>2y5y Fwd</td><td>3.36</td><td>0.</td><td>3.36</td><td>2.69</td><td>-100.</td><td>-100.</td></tr></table></body></html>  

Macaulay Duration for first security in table above  

![](1f0dc4994f6c4a4602f97b72885010b369ada3b16f466779636c02cd4ff9c74f.jpg)  
DV01 is the dollar change for a $\$100$ notional instrument per 100bp change in yield. Modified duration is the percent change per 100bp change in yield. Macaulay duration is the weighted average time to maturity, in years. Duration for forward swaps are not calculated (anc are reported as -100).  

# Transformed Partial Dv01s  

The table below is initialized to report risk w.r.t. 1, 2, 5, and 10 year par swap yields. If you are reading the .cdf version you may choose alternate instruments from the four drop-down lists and the risk will re-calculate. You can choose sets of instruments that are not appropriate (for example using the 3 year swap instead of the 2 year swap) but the transformation will still be calculated. If you choose a set of instruments for which the Jacobian is singular, the risk will not display.  

Table A5 - Transformed Dv01 w.r.t. Alternate Variables  

Partial Dvols  

![](ac09003a2a197fc7cf7faf95670824d7857ee868953654989801119f729a6c37.jpg)  
DV01s are reported as dollar change for a $\$100$ notional instrument per l00bp change in yields orrates. Instruments used in fitting the curve are highlighted. Transformed via methodology discussed in the text.  

<html><body><table><tr><td></td><td>lyr : Swap</td><td>2yr Swap</td><td>5yr Swap</td><td>10yr Swap</td><td>Total</td></tr><tr><td>1yr Swap</td><td>0.98</td><td>0.</td><td>0.</td><td>0.</td><td>0.98</td></tr><tr><td>2yr Swap</td><td>0.</td><td>1.94</td><td>0.</td><td>0.</td><td>1.94</td></tr><tr><td>3yr Swap</td><td>0.</td><td>1.27</td><td>1.59</td><td>0.</td><td>2.86</td></tr><tr><td>5yr Swap</td><td>0.</td><td>0.</td><td>4.61</td><td>0.</td><td>4.61</td></tr><tr><td>10yr Swap</td><td>0.</td><td>0.</td><td>0.</td><td>8.38</td><td>8.38</td></tr><tr><td>1yr Ann</td><td>0.01</td><td>0.</td><td>0.</td><td>0.</td><td>0.01</td></tr><tr><td>2yr Ann</td><td>0.02</td><td>0.04</td><td>0.</td><td>0.</td><td>0.06</td></tr><tr><td>3yr   Ann</td><td>0.03</td><td>0.08</td><td>0.04</td><td>0.</td><td>0.15</td></tr><tr><td>5yr Ann</td><td>0.03</td><td>0.11</td><td>0.24</td><td>0.</td><td>0.37</td></tr><tr><td>10yr Ann</td><td>0.03</td><td>0.11</td><td>0.54</td><td>0.78</td><td>1.45</td></tr><tr><td>lyr Zero</td><td>0.97</td><td>0.</td><td>0.</td><td>0.</td><td>0.97</td></tr><tr><td>2yr Zero</td><td>-0.02</td><td>1.9</td><td>0.</td><td>0.</td><td>1.88</td></tr><tr><td>3yr Zero</td><td>-0.02</td><td>1.19</td><td>1.56</td><td>0.</td><td>2.72</td></tr><tr><td>5yr Zero</td><td>-0.03</td><td>-0.11</td><td>4.37</td><td>0.</td><td>4.24</td></tr><tr><td>10yr Zero</td><td>-0.03</td><td>-0.11</td><td>-0.54</td><td>7.6</td><td>6.93</td></tr><tr><td>1y2y Fwd</td><td>-0.99</td><td>1.95</td><td>0.</td><td>0.</td><td>0.96</td></tr><tr><td>2y5yFwd</td><td>-0.01</td><td>-1.94</td><td>4.64</td><td>0.</td><td>2.7</td></tr><tr><td>3y5y Fwd</td><td>0.</td><td>-1.27</td><td>3.02</td><td>0.</td><td>1.74</td></tr><tr><td>5y10y Fwd</td><td>-0.01</td><td>-0.02</td><td>- 4.6</td><td>8.51</td><td>3.88</td></tr><tr><td>7y10y Fwd</td><td>0.</td><td>-0.01</td><td>-2.66</td><td>4.79</td><td>2.12</td></tr></table></body></html>  

# References  

Coleman, Thomas S. (1998), "Fitting Forward Rates to Market Data, available from Social Science Research Network, http:/ / ssrn.com/ abstract=994870   
Ho, Thomas S.Y. (1992), "Key Rate Durations: Measures of Interest Rate Risks," The Journal of Fixed Income, September 1992 Vol. 2, No. 2, pp. 29-44   
Macaulay, Frederick (1938), Some Theoretical Problem s Suggested by the Movements of Interest Rates, Bond Yields, and Stock Prices in the United States since 1856. New York: Columbia University Press.   
Reitano, Robert R., (2008), "Yield Curve Risk Management,' in Handbook of Finance, Frank J. Fabozzi, ed., vol. 3, p. 215 Hoboken, NJ: John Wiley and Sons..   
Reitano, Robert R., (1991), "Multivariate Duration Analysis," Transactions of the Society of Actuaries XLIlI: 335-391, availabl on-line at http:/ / www.soa.org/ library/ research/ transactions-of-society-ofactuaries/ 1990-95/ 1991/ january/ tsa91v4311.pdf   
This paper, (Coleman 2011, "A Guide to Duration, Dv01, and Yield Curve Risk Transformations") is also available in .cdf/ .nbp format (Wolfram computable document format or notebook player) with dynamic interactivity enabled - see www.closemountain.com/publications.htm1  