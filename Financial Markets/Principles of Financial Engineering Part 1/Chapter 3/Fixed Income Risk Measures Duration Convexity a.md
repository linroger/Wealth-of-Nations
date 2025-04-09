# 3.8 FIXED INCOME RISK MEASURES: DURATION, CONVEXITY AND VALUE-AT-RISK  

As we saw in the introductory chapter, volatility trading is made possible in the presence of two instruments, one whose value moves linearly as the underlying risk changes, while the other's value moves according to a convex curve. As we will see later in this section there are also convexity differences between interest rate forwards and interest rate futures. This is due to the fact that the pricing equation for Eurocurrency futures is linear whereas the market-traded FRAs have a pricing. equation that is nonlinear in the corresponding LIBOR rate..  

We will encounter several other convex instruments, including options, in later chapters but one. of the simplest convex instruments is a default-free bond. A bond's price is a nonlinear function of its yield. This is shown in Figure 3.15.24 The solid line represents the price-yield relationship for a.  

![](af2cd5fe1b2e6beb07fe4d5c18bb1b7ac1eb654f9ca33b489ac20d5d1e51f4b6.jpg)  

# FIGURE 3.15  

Price-yield curve and duration approximation.  

coupon bond with 3 years to maturity, semiannual coupons and a face value of $\$100$ .The pricing function for the bond is  

$$
B(0,T)=\frac{C}{\left(1+y/2\right)}+\frac{C}{\left(1+y/2\right)^{2}}+...+\frac{C+F}{\left(1+y/2\right)^{6}}.
$$  

In this example, the coupon rate is $1\%$ per year and the bond makes semiannual coupon payments of 50 cents. The above figure captures that an increase (decrease) in the bond yield decreases (increases) the price of the bond.  

Risky bonds are exposed to various risk factors including credit risk, but a default-free bond is. only exposed to interest rate risk. In this section, we review some of the most important measures used to calculate and hedge risk in fixed income markets. These are Dv01, duration and convexity.. As we will see duration is a linear approximation to the nonlinear bond price-yield relationship,. while convexity measures the curvature of the relationship. One of the underlying simplifying. assumptions here will be that only one risk factor is driving changes in the term structure of interest rates. More complex models exist but will not be discussed here..  

# 3.8.1 DVO1 AND PVO1  

The solid line in Figure 3.15 shows that the price of Bond A is $\$94.30$ when the yield to maturity is $3\%$ . If the yield was to increase from $3\%$ to $3.10\%$ , the bond price would fall from $\$94.30$ to $\$94.03$ . This implies a slope of the curve equal to $((93.03-94.30)/(3.10\%-3.00\%))=-274.687$ or $-2.74$ cents per basis point. The price sensitivity itself is not constant as yields change. For example, if yields were to fall from $2\%$ to $1.9\%$ , the bond price would rise from 97.10 to 97.38. This would imply a slope of $((97.38-97.10)/(1.9\%-2\%))=-285.286$ or 2.85 cents per basis point. We have thus calculated by how much the bond price changes when the yield changes by 1 basis point. It turns out that this sensitivity is the definition of the dollar duration or Dv01 measure.  

# 3.8.1.1 Dollar duration Dv01  

DV01 is short for "dollar value of $a O I^{\gamma}$ , that is 1 basis point. More formally, if we denote the change in the bond price by $\Delta B$ and the change in the yield by $\Delta y$ then DV01 is defined as follows  

$$
\mathrm{\bfDV}01=-\mathrm{\bf\Pi}\frac{\Delta B}{10,000\times\Delta y}
$$  

Note that dollar duration or DV01 is the change in price in dollars, not in percentage. The negative sign is there by convention to assume that DV01 is positive for most fixed income securities if which prices fall as yields rise. As we will see in later chapters, Dv01 is the equivalent of the delta, one of the Greeks in option pricing, which measures the sensitivity of an option to changes in the underlying, for example. One of the advantages of DV01 over other measures of interest rate risk (such as modified duration) is that it is useful for fixed income instruments with zero present) value at inception such as interest rate swaps.  

In the above example, we have chosen several points on the yield axis to calculate the sensitivity of bond prices to yields. We saw that the sensitivity changes with yields, but if we were to move the different points on the yield curve together we would obtain the tangent to the price-yield curve at the given yield level. The slope of the tangent line at a given yield level is called the derivative of the price yield function and is denoted by $\mathrm{d}B/d y$ . In the case of the simple coupon bond that we examined above the derivative of the price-yield curve is available in closed form, that is, as a simple mathematical formula:  

$$
\mathrm{\bfDV}01=-\mathrm{\bf\Phi}\frac{\mathrm{d}B}{10,000\times\mathrm{d}y}
$$  

For more complex instruments the derivative needs to be approximated numerically by means of simulations. Many market participants take Dv01 to refer to the yield-based Dv01, but there are other more general versions of Dv01 which measure how a specific risk factor changes by one basis point and how this affects different parts of the term structure of interest rates.  

# 3.8.1.2 PV01  

There are some standard bond market terms that are often used in swap markets. The present value of a basis point or Pv01 is the present value of an annuity of 0.oo01 paid periodically at times $t_{i},$ calculated using the proper LIBOR rates, or the corresponding forward rates:  

$$
\mathrm{PV}01=\sum_{i=1}^{n}\frac{(0.01)\delta}{\sum_{j=1}^{i}(1+L_{t_{j}}\delta)}
$$  

In order to get the sensitivity to one basis point, the number obtained from this formula needs to be divided by 100. The concepts, PV01 and DV01, are routinely used by market practitioners for the pricing of swap-related instruments and other fixed income products.2  

# 3.8.2 DURATION  

There are several measures of risk in fixed income markets. As we saw above, DV01 measures the dollar change in the value of an asset in response to a basis point change in the yield. A related. measure of interest rate sensitivity focuses on the percentage change in the value of an asset in. response to a unit change in yields. This measure is called modified duration or. $D$ and is defined as follows:  

$$
D=-\frac{1}{P}\frac{\Delta P}{\Delta y}
$$  

Since for a coupon bond $B(t,T)$ an explicit formula is available for the bond-yield relationship, we can calculate duration $D$ by differentiating with respect to. $y$ . For simplicity, consider a bond. with annual coupon payments $C$ .The price of such bond,. $B(O,T)$ , at time $t=0$ with a maturity. $T$ years and a face value of $F$ is given by.  

$$
B(0,T)=\frac{C}{(1+y)}+\frac{C}{(1+y)^{2}}+...+\frac{C+F}{(1+y)^{T}}
$$  

Modified duration $D_{\mathrm{modified}}$ can therefore be expressed as  

$$
{\cal D}_{\mathrm{Modified}}=-\frac{1}{P}\frac{\mathrm{d}B}{\mathrm{d}y}=\frac{1}{1+y}\times\frac{1}{P}\left[\frac{C}{\left(1+y\right)^{1}}\times1+\frac{C}{\left(1+y\right)^{2}}\times2+\ldots+\frac{C+F}{\left(1+y\right)^{T}}\times T\right]
$$  

This can be rewritten as  

$$
D_{\mathrm{Modified}}=\frac{1}{1+y}\times\frac{1}{\mathrm{Sum~of~PV~of~CF}}\sum_{t=1}^{T}t\times\mathrm{PV}(\mathrm{CF}_{t})=\frac{1}{1+y}\times\frac{1}{B}\sum_{t=1}^{T}t\times\mathrm{PV}(\mathrm{CF}_{t})
$$  

The above equation nicely illustrates that duration is linked to the average time to maturity ofJ the cash flows $\left(\mathrm{CF}_{t}\right)$ embedded in the bond. Specifically, it is related to the weighted average where. each time to maturity is weighted by the present value of a given cash flow relative to the bond price (which itself is the sum of the present value of all cash flows, of course). We can apply the. above duration formula to the 3-year bond example in Figure 3.15. What is the duration of the bond if the yield to maturity is $3\%2$ If we apply Eq. (3.52) to this bond, we obtain a modified duration of 2.9178. This means that a one basis point increase in the yield from. $3\%$ to $3.01\%$ is going to lead to an approximate decrease in the bond price of. $2.9178\times0.0001$ or $0.029178\%$ . Since the price of the bond at. $3\%$ is $\$94.30$ , this percentage change corresponds to a dollar change of $0.029178\%\times\$94.30$ or $\$2.74$ per basis point, which, not surprisingly, is the Dv01 that we calcu-. lated at the yield level of. $3\%$ . The dashed line in Figure 3.15 shows the linear duration approxima-. tion at the yield level of. $3\%$ . As we can see, for larger changes in yields, duration is a poor approximation to the convex bond-yield relationships..  

# EXAMPLE  

Figure 3.16 presents a real-world example of risk measures for a fixed income security. It shows a screenshot from Bloomberg on June 16, 2014 for the T $2{\frac{1}{2}}$ 05/15/24, that is the 10-year Treasury note with a $2.5\%$ fixed coupon, a $\$1\mathrm{m}$ face value and a maturity of May 5, 2024. The Dv01 at the current yield level of $2.59\%$ is 865 and the modified duration is 8.701.  

![](5834836f36f526228b354da57cfe9709be2da0db010e95ed07262b0375847e2a.jpg)  

Ten-year Treasury note with $2.5\%$ fixed coupon.  

# 3.8.3 CONVEXITY  

As we saw in the context of the Dv01 measure, the sensitivity of bond prices to yields is not constant but changes with the level of yields. This sensitivity is measured by convexity and captures. the curvature of the bond-yield relationship in Figure 3.15. Duration is based on the first deriva-. tive and convexity is based on the second derivative of the price-yield curve. Convexity is defined as  

$$
C o n\nu e x i t y=\frac{1}{B}\frac{\mathrm{d}^{2}B}{\mathrm{d}y^{2}}
$$  

In the case of a coupon bond whose price is given in Eq. (3.50) above, the formula for convexity is  

$$
C o n\nu e x i t y=\frac{1}{B\times(1+y)^{2}}\sum_{t=1}^{T}\left[\frac{\mathbf{C}\mathbf{F}_{t}}{(1+y)^{t}}(t^{2}+t)\right]
$$  

where $\mathrm{CF}_{t}$ is the cash flow paid to the bondholder at date. $t.$ Convexity is the rate of change of the. slope of the price-yield curve. The Treasury security in Figure 3.16 has a convexity of 0.859. Convexity is an attractive feature. This applies for buy-and-hold investors as well as volatility traders. Bonds with greater curvature gain more in price when yields fall than they lose when yields rise.  

For noncallable bonds, convexity is positive. In other words, the slope increases and becomes less negative as yields increase. Convexity is however not always positive for fixed income securities. As we will see in Chapter 17, for bonds with embedded options, such as callable bonds, for example, there is a range of yields for which convexity is negative and the curvature of the price-yield relationship increases as yields rise. $\mathrm{CF}_{t}$ with $T$ years to maturity and annual coupon bonds. One of the advantages of convexity is that it can be used to improve on the duration approximation when measuring the sensitivity of the bond-yield relationship. Another important use is that it can help to measure the potential for volatility trading and convexity gains when forming portfolios of bonds and hedging them. The exercises at the end of this chapter contain an exercise on the duration and convexity of a barbell strategy that illustrates one of the uses of convexity measures for bonds.  

# 3.8.4 IMMUNIZATION  

Hedging fixed income portfolios against interest rate risk fluctuations is called immunization. Immunization strategies can be based on duration. The duration of a portfolio is the weighted average of the duration of the portfolio constituents. Thus, a portfolio of two bonds A and B has a duration $D_{\mathrm{P}}$  

$$
D_{\mathrm{P}}=w\times D_{\mathrm{A}}+(1-w)D_{\mathrm{B}}
$$  

The above equation can also be used to calculate the optimal weights for an immunized portfolio. Asset A could be a bond and asset. $\mathbf{B}$ could be another bond or a bond futures. To immunize the portfolio we would want to calculate the weights $w$ and $(I-w)$ that set the portfolio duration. $D_{\mathrm{P}}$ to zero.This implies $w=(D_{\mathrm{B}}/(D_{\mathrm{B}}-D_{\mathrm{A}}))$ Another application is the context of.  

Asset-Liability Management, as we will see in the next chapter. Pension funds have liabilities whose present value is typically calculated by dividing by a bond market rate. The assets of a pension fund can include fixed income instruments as well as other assets. One typical risk manage-. ment objective of a pension fund is to immunize the balance sheet against interest rate risk. This can be achieved by making sure that the duration of the assets is equal to the duration of the liabilities. As interest rates go up, for example, the present value of pension liabilities tends to fall. If the asset side is dominated by fixed income securities, the value of the assets would also fall at the same time. As we will see in the next chapter, swaps can also be used to immunize a portfolio or balance sheet.  

# 3.8.5 VALUE-AT-RISK, EXPECTED SHORTFALL, BASEL CAPITAL REQUIREMENTS AND FUNDING COSTS  

One of the distinguishing features of our approach in this book is to assume the perspective of the market maker when considering financial engineering applications. All risk takers in banks including market makers need to fund their activities. Funding costs are driven by capital requirements that banks in different countries are subject to and these are guided by the Basel Committee on Banking Supervision. Funding costs for hedge funds are also affected by regulation, either directly or indirectly through the prime brokerage relationship. The ability of a prime brokerage desk to finance hedge fund trades is controlled by the bank's internal capital requirements. Banking regulation distinguishes banks' lending and trading activities by separating them into banking and trading books. One of the most widely used measures of risk for trading books since 1990s was value-atrisk (VaR).26VaR is a risk measure of the risk of loss on a given portfolio of financial assets. VaR). is defined as the maximum loss not exceeded with a given probability defined as the confidence level, over a given period of time. For example, if a portfolio of bonds has a 1-day $5\%$ VaR of $\$100$ million, then there is a 0.05 probability that the portfolio will fall in value by more than. $\$100$ million over a 1-day period. On October 2013, the Basel Committee on Banking Supervision, in its review of trading book rules proposed scrapping VaR as the basis for modeling market risk capital requirements. The committee recommended replacing VaR with expected shortfall, which measures the expected value of losses above a given confidence internal. The reputation of VaR was badly damaged during the GFC, since it became clear to regulators, banks and other market participants that stressed market conditions can lead to losses far in excess of the maximum amounts forecast by standard VaR applications. One of the theoretical advantages of expected shortfall is that, unlike VaR, expected shortfall is a coherent risk measure. This means that VaR might theoretically discourage diversification. Although one of the stated intentions of the Basel committee is to better capture tail risk, it is important to note that the failure of VaR during the crisis is not so much due to its mathematical properties, but rather the results of how it was applied in practice, which often relied on using short historical time periods and distributional assumptions that did not allow for.  

scenarios with extreme volatilities and asset correlations. Expected shortfall applications have their own practical challenges such as data requirements and backtesting issues. By its nature, expected shortfall requires orders of magnitude more data than VaR since it incorporates less likely scenarios. Regulation goes through waves and whichever risk measure dominates capital requirement calculations in the future, financial engineers will need to be familiar with them since these rules determine funding costs and, therefore, which trades and derivative products are profitable in practice and which are not.  
