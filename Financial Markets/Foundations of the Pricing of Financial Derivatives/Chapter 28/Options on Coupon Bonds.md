---
tags:
  - '#american_options'
  - '#binomial_tree'
  - '#coupon_bond_options'
  - '#coupon_payment'
  - '#european_options'
  - '#exercise_price'
  - '#option_pricing'
---
# 28.4 OPTIONS ON COUPON BONDS

Now, we shall look at options on the four-period coupon bond we analyzed in Section. 28.2. Recall that its pricing tree is Figure 28.3. Let us examine an option expiring at time. 3 with an exercise price of 1.0. We shall assume that at expiration, the exercise of the option would occur an instant before the coupon is paid. In other words, we would exercise in time to receive the coupon. Thus, the values in Figure 28.3 are the relevant values to compare with the exercise price. Let us illustrate the calculated values at time 3:.

$$
\begin{array}{r l}&{c C B(3,1.0,4,0.05)^{++}=\operatorname*{max}(0,0.9881-1)=0.0000}\ &{\begin{array}{r l}{p C B(3,1.0,4,0,0.5)^{++}=\operatorname*{max}(0,1.-0.9881)=0.0119}\ &{c C B(3,1.0,4,0.05)^{++}=\operatorname*{max}(0,1.0071-1)=0.0071}\end{array}}\ &{\begin{array}{r l}{p C B(3,1.0,4,0.05)^{+-}=\operatorname*{max}(0,1.-1.0071)=0.0000}\ &{c C B(3,1.0,4,0.05)^{+-}=\operatorname*{max}(0,1.0264-1)=0.0264}\end{array}}\ &{\begin{array}{r l}{p C B(3,1.0,4,0,0.5)^{+-}=\operatorname*{max}(0,1.-1.0264)=0.0000}\ &{c C B(3,1.0,4,0.05)^{--}=\operatorname*{max}(0,1.0461-1)=0.0461}\end{array}}\ &{\begin{array}{r l}{P C B(3,1.0,4,0.05)^{--}=\operatorname*{max}(0,1.0461-1)=0.0461}\ &{p C B(3,1.0,4,0.05)^{--}=\operatorname*{max}(0,1.-1.0461)=0.0000.}\end{array}}\end{array}
$$

![](images/c845fc58c35ab461dc3d85107d9b8a1e2bc4ce853dfcfe4233c7a9ac8026590f.jpg)
FIGURE 28.5 Binomial Tree of Options on Coupon Bond Prices

Now, let us go to the top node at time 2 and illustrate how the call and put values are calculated using the binomial formula:

$$
\begin{array}{r l}&{c C B(3,1.0,4,0.05)^{++}=\bigl[0.5(0.0000)+0.5(0.0071)\bigr]0.8954=0.0032}\ &{p C B(3,1.0,4,0.05)^{++}=\bigl[0.5(0.0119)+0.5(0.0000)\bigr]0.8954=0.0053.}\end{array}
$$

Continuing in that manner gives us Figure 28.5, the tree of European option prices for the underlying coupon bond.

If these were American options, we would compare the exercise values with the unexercised values and replace the latter with the former if early exercise were justified.
