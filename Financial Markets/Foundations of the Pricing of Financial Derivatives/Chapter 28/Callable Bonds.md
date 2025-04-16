---
tags:
  - '#binomial_framework'
  - '#bond_issuer'
  - '#bond_pricing'
  - '#bond_valuation'
  - '#bondholder_risk'
  - '#call_period'
  - '#call_price'
  - '#callable_bond'
  - '#interest_rates'
---
# 28.5 CALLABLE BONDS

A callable bond is a bond in which the issuer can choose to retire the bond early. This is sometimes done because interest rates have fallen, and a new bond can be issued at a lower rate. There are naturally some costs associated with retiring one bond and issuing another, but these costs can often be far less than the savings from issuing a bond at a lower interest rate. Firms might also retire bonds when they have unexpected available cash that can be used to pay off the remaining amount owed. A callable bond has a call price embedded in it, which is represented by the amount that is paid off to retire it. This price will often be the face value plus some additional interest, which compensates the bond holders for the inconvenience of having their investment prematurely terminated. In addition, the bondholder has to find another investment in an environment in which rates are lower. A callable bond will also have a call period, which means that it cannot be called before one date, nor after another, though the latter might simply be the maturity.

Evaluating the pricing of a callable bond is relatively simple in a binomial framework.. Let us price a callable bond using the coupon bond we have previously priced, a four-year bond with a coupon of 0.05. Recall that the tree of its prices is Figure 28.3. We shall now assume the bond is callable as of time 1 at a price of 1.025. Starting off at maturity, time 4, the bond is not callable, and the issuer would not call it anyway, because it has to pay some additional interest, and there are no savings in the future. It would simply pay off the bond. by paying the principal, 1.00, and the last period's interest of 0.05. So all outcomes for the callable and noncallable bond at time 4 are 1.05. Stepping back to time 3, we see that the noncallable bond values are 0.9881, 1.0071, 1.0264, and 1.0461 in the four possible. outcomes. Recall that these values include the interest payment at time 3..

Now let us determine the callable bond values in each of these four states. First, for the top state, we can see that the bond is worth 0.9881, so there is no reason to call it and. pay 1.025:

$$
B(1,1.025,4,0.05)^{+++}=\operatorname*{min}\left[C B(4,0.05)^{+++},1.025\right]=\operatorname*{min}(0.9881,1.025)=0.9881.
$$

Of course, you may wonder whether the value of the bond means anything to the issuer. It certainly means something to the holder. Remember that to the issuer it is the present value of the remaining payments. Thus, in this case, if not called, the firm is obligated to make remaining payments with a value in that state of 0.9881. If it calls the bond, it must pay 1.025 immediately. So clearly, it is not optimal to call the bond. It will also not be optimal to call it in the state in which the bond value is 1.0071. It will, however, be optimal to call it in the bottom two outcomes at time 3, as 1.025 is below 1.0264 and 1.0461:

$$
5B(1,1.025,4,0.05)^{++-}=\operatorname*{min}\left[C B(4,0.05)^{++-},1.025\right]=\operatorname*{min}(1.0071,1.025)=1.0071
$$

$$
\Sigma B(1,1.025,4,0.05)^{--+}=\operatorname*{min}\left[C B(4,0.05)^{--+},1.025\right]=\operatorname*{min}(1.0264,1.025)=1.0250
$$

$$
\ B(1,1.025,4,0.05)^{--}=\operatorname*{min}\left[{\cal C}B(4,0.05)^{--},1.025\right]=\operatorname*{min}(1.0461,1.025)=1.0250.
$$

Now, let us step back to time 2. At the very top state, where the bond value is 0.9432,. it is clearly not optimal to call the bond and pay 1.025. Thus,. $c C B(1,1.025,4,0.05)^{++}=$ 0.9432. Now, in the middle state, the price of the bond is 0.9881, and it is not optimal to call it and pay 1.025, but 0.9881 is not the value of the callable bond. At this point, the next two outcomes are 1.0071 and 1.0250, the latter a result of the call at time 3. Thus, we have to take a weighted average of the next two outcomes and discount by the appropriate one-period factor, $B(3)^{+-}=0.9226$ In addition, we have to add the interest payment at. time 3 of 0.05, and we have to again check and see if all of this exceeds 1.025, in which case it would be called. The remaining results for time 2 are.

$$
{\begin{array}{l l}{{\mathord{\it{c C B}}}(1,1.25,4,0.05)^{+-}=\operatorname*{min}\left\{\left[0.5(1.0071)+0.5(1.025)\right]0.9226+0.05,1.025\right\}=0.98}\ {{\mathord{\it{c C B}}}(1,1.25,4,0.05)^{--}=\operatorname*{min}\left\{\left[0.5(1.0250)+0.5(1.025)\right]0.9507+0.05,1.025\right\}=1.02}\end{array}}
$$

![](images/44941448d2a3ddb15ab8368767434c856310c7851b96b46b52737bf71e8fa34f.jpg)
FIGURE 28.6 Binomial Tree of Noncallable and Callable Bond Prices

So clearly it would not be called at time 2. We would then step back to time 1 and apply the same procedure, and we would obtain callable bond prices of 0.9303 and 1.0048, and of course, the bond would not be called at time 1. At time 0, the bond is not callable at all and the callable bond price would be 0.9039, which is lower than the price of the bond if it were not callable, 0.9066. The lower price compensates the buyer for the risk of having it called. That risk is realized when the bond is called, the bondholder is paid back the principal, and then has to invest it elsewhere in a lower interest rate environment. The full tree is presented in Figure 28.6.
