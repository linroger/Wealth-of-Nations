# 28.1 ZERO-COUPON BONDS

At time 0, the price of a one-period zero-coupon bond with face value 1 is easily found as

$$
B(0,1)=B(1)=e^{-0.068}=0.9343.
$$

Note that we suppress the O here for notational simplicity. The argument in parentheses is the maturity of the bond. Again, we do not include an argument for the time point we are at, as we shall use the $+$ and - superscripts to indicate where we are. This will cut down on notational clutter.1 There are no superscripts in this case, so we know we are at time 0.

![](images/259ff24b50186e6b4dfa8101b58b57b15c6504bb497192c6159bb2350734dd05.jpg)
FGURE 28.1 Heath-Jarrow-Morton Arbitrage-Free Binomial Tree Using the Method of Grant-Vora

We also need the prices at time 0 of zero-coupon bonds with maturities of two, three, and. four periods. We can obtain these values by successively discounting at the forward rates as follows:

$$
\begin{array}{l}{{B(2)=e^{-0.068-0.072}=0.8694}}\ {{B(3)=e^{-0.068-0.072-0.08}=0.8025}}\ {{B(4)=e^{-0.068-0.072-0.08-0.082}=0.7393.}}\end{array}
$$

If we want to fill in the entire tree of all zero-coupon bond prices, we need only go up. through time 3, because the four-period bond will have a price of 1 at time 4. The prices of the four-period bond at time 3 are found by discounting the 1.0 payoff at time 4 at the. spot rates in the forward rate tree:.

$$
\begin{array}{l}{{B(4)^{+++}=e^{-0.1126S}=0.8935}}\ {{{}}}\ {{B(4)^{++--}=e^{-0.0926S}=0.9115}}\ {{{}}}\ {{B(4)^{--+}=e^{-0.0726S}=0.9299}}\ {{{}}}\ {{B(4)^{---}=e^{-0.0526S}=0.9487.}}\end{array}
$$

For example, we read these as the prices of the four-period bond when the rate has gone up three times, up twice and down once, down twice and up once, and down three times, respectively.

Stepping back to time 2, let us obtain the prices of the three-period bond:

$$
\begin{array}{l}{{B(3)^{++}=e^{-0.110525}=0.8954}}\ {{{}}}\ {{B(3)^{+-}=e^{-0.080525}=0.9226}}\ {{{}}}\ {{B(3)^{--}=e^{-0.050525}=0.9507.}}\end{array}
$$

Now, let us obtain the prices of the two-period bond as represented by the four-period bond at time 2. We can discount by the successive spot and forward rates. For example, for the prices of two-period bonds at time 2, we have

$$
\begin{array}{l}{{B(4)^{++}=e^{-0.110525-0.1026}=0.8081}}\ {{{}}}\ {{B(4)^{+-}=e^{-0.080525-0.0826}=0.8495}}\ {{{}}}\ {{B(4)^{--}=e^{-0.050525-0.0626}=0.8930.}}\end{array}
$$

Of course, this is a bond that matures at time 4, and there have been two time steps so far.

And there is yet another and most important way to get the price of any such bond: We use the binomial valuation formula that weights the next two outcomes and then discounts at the one-period rate. Let us note that discounting at the one-period rate is the same as multiplying by the one-period bond price. So, again, to get the prices of two-period bonds at time 2, we do the following, using the price $B(2)$ in the appropriate state to discount:

$$
\begin{array}{r l}&{B(4)^{++}=\left[0.5(0.8935)+0.5(0.9115)\right]0.8954=0.8081}\ &{B(4)^{+-}=\left[0.5(0.9115)+0.5(0.9299)\right]0.9226=0.8495}\ &{B(4)^{--}=\left[0.5(0.9299)+0.5(0.9487)\right]0.9507=0.8930.}\end{array}
$$

If we continue and fill in the tree, we obtain Figure 28.2.

![](images/f55e75eee39cb4a5be3273a83da89da135f6e113274abde0a0d4864ff4741fc2.jpg)
FIGURE 28.2 Binomial Tree of Zero-Coupon Bond Prices

The litmus test to determine if the tree is properly fit is to price each bond by rolling through the tree backwards using the binomial formula, but we already know the prices at time 1. So, let us see if we can obtain them from the prices at time 2:

$$
\begin{array}{r l}&{B(2)=\left[0.5(0.9119)+0.5(0.9491)\right]0.9343=0.8694}\ &{B(3)=\left[0.5(0.8289)+0.5(0.8890)\right]0.9343=0.8025}\ &{B(4)=\left[0.5(0.7558)+0.5(0.8269)\right]0.9343=0.7393.}\end{array}
$$

Because these prices match the ones we had already obtained, we know the tree is done correctly.
