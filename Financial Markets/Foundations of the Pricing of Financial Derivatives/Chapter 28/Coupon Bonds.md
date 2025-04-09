# 28.2 COUPON BONDS

Coupon bonds make a series of payments of interest and a final payment of principal.
As such, they can be viewed as combinations of zero-coupon bonds. That is, each payment.
is a zero-coupon bond in and of itself..

Consider, for example, a four-period coupon bond with a $5\%$ coupon per period. Its price at time O can be found by discounting the individual coupons and the principal at the appropriate zero-coupon bond rate. Thus, it can be viewed as zero-coupon bonds with face value 0.05, maturing at times 1, 2, and 3, and a zero-coupon bond maturing at time 4 with face value 1.05. The discounting can be done by multiplying by the time 0 zero-coupon bond prices for the various maturities in the following manner:

$$
\ B(4,0.05)=0.05(0.9343)+0.05(0.8694)+0.05(0.8025)+1.05(0.7393)=0.9066,
$$

where we use the notation $C B(4,0.05)$ to be the price at time 0 of a coupon bond that.
matures at time 4 and has a coupon of 0.05. We take as the standard case a 1.0 principal.

Now, let us fill in the entire tree for this bond. We shall omit time 4 because we know the bond pays off 1.05 in each state. At time 3, we can discount the payment of 1.05 that comes up in time 4 at the respective one-period rate for the appropriate state.2 Note, however, that we also have to add the coupon paid at time 3. As such,

$$
\begin{array}{l}{{C B(4,0.05)^{++}=1.05e^{-0.11265}+0.05=0.9881}}\ {{C B(4,0.05)^{++-}=1.05e^{-0.09265}+0.05=1.0071}}\ {{C B(4,0.05)^{+-+}=1.05e^{-0.07265}+0.05=1.0264}}\ {{C B(4,0.05)^{--}=1.05e^{-0.05265}+0.05=1.0461.}}\end{array}
$$

We can continue to step back and obtain the prices at times 2 and 1. And we know that at time 1, the price should equal the 0.9066, the value we previously obtained. Indeed, it will. The tree of coupon bond prices is shown in Figure 28.3.

![](0de506b2a8f1dbf2bf12c2c92c42dbfeabfb1612c7011d8436c75ff822eb0ef8.jpg)
FIGURE 28.3 Binomial Tree of Coupon Bond Prices
