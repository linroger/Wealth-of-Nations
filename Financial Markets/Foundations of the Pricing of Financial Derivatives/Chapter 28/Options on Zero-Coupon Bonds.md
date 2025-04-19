---
tags:
  - binomial_tree
  - european_option
  - exercise_price
  - option_pricing
  - zero_coupon_bond
aliases:
  - Options on Zero Coupon Bonds
  - Zero-Coupon Bond Options
key_concepts:
  - American style options
  - Binomial discounting method
  - European call/put options
  - Option expiration and exercise
  - Underlying zero-coupon bond
---

# 28.3 OPTIONS ON ZERO-COUPON BONDS

Now, let us use the tree to price our first options. Specifically, we are going to price European call and put options that expire at time 3 on a four-period zero-coupon bond.. Note that we do not care about four-period options on this bond, because the face value of the bond has no uncertainty at time 4: it is 1 for sure. Let us arbitrarily choose an exercise price of 0.9. The prices of the underlying zero-coupon bond are shown in Figure 28.2.. They are the prices $B(4)$ in the respective nodes. To introduce options, however, we are. going to have to add to the notation a bit, because with options we have two additional parameters to put in parentheses--the expiration of the option and the exercise price. In addition, we need to show information about the underlying..

Let us start at the top node of time 3, where we want the option prices, designated as $c Z C B(3,0.9,4)$ and $\hbar{Z C B}(3,0.9,4)$ for calls and puts, respectively. This notation stands for the price of a call or put expiring at time 3 with an exercise price of 0.9 on a zero-coupon bond maturing at time 4. Let us calculate the prices in this top node:

$$
\begin{array}{r l}&{c Z C B(3,0.9,4)^{+++}=\operatorname*{max}(0,0.8935-0.9)=0.0000}\ &{p Z C B(3,0.9,4)^{+++}=\operatorname*{max}(0,0.9-0.8935)=0.0065.}\end{array}
$$

Stepping down to the three lower nodes, we follow the same pattern. To illustrate the calculation at time 2, we shall need the values:

$$
\begin{array}{r l}&{c Z C B(3,0.9,4)^{++-}=\operatorname*{max}(0,0.9115-0.9)=0.0115}\ &{p Z C B(3,0.9,4)^{++-}=\operatorname*{max}(0,0.9-0.9115)=0.0000.}\end{array}
$$

Now, we shall price the option at time 2 using the binomial discounting method:

$$
\begin{array}{r l}&{c Z C B(3,0.9,4)^{++}=\left[0.5(0.0000)+0.5(0.0115)\right]0.8954=0.0052}\ &{p Z C B(3,0.9,4)^{++}=\left[0.5(0.0065)+0.5(0.0000)\right]0.8954=0.0029.}\end{array}
$$

We fill in the rest of the tree and obtain Figure 28.4.

FIGURE 28.4  Binomial Tree of Options on Zero-Coupon Bond Prices


<html><body><table><tr><td colspan="2"></td><td></td><td>cZCB(3,0.9,4)+++=0.0000 pZCB(3,0.9,4)+++=0.0065</td></tr><tr><td rowspan="3"></td><td></td><td>cZCB(3,0.9,4)++=0.0052 pZCB(3,0.9,4)++=0.0029</td><td></td></tr><tr><td>cZCB(3,0.9,4)+=0.0111 pZCB(3,0.9,4)+=0.0013</td><td></td><td>cZCB(3,0.9,4)++-=0.0115 pZCB(3,0.9,4)++-=0.0000</td></tr><tr><td></td><td>cZCB(3,0.9,4)+=0.0191 pZCB(3,0.9,4)+-=0.0000</td><td></td></tr><tr><td rowspan="3"></td><td>cZCB(3,0.9,4)=0.0268 pZCB(3,0.9,4)-=0.0000</td><td></td><td>cZCB(3,0.9,4)--+=0.0299 pZCB(3,0.9,4)--+=0.0000</td></tr><tr><td></td><td>cZCB(3,0.9,4)--=0.0374 pZCB(3,0.9,4)- = 0.0000</td><td></td></tr><tr><td></td><td></td><td>cZCB(3,0.9,4)---=0.0487 pZCB(3,0.9,4)---=0.0000</td></tr></table></body></html>

Notice that when interest rates go up, the price of the underlying goes down so puts are more highly valued in the up states, and calls are more highly valued in the down states.

If these options were American style, they could be exercised early. In each node, we would evaluate whether the exercise value would exceed the unexercised value in the node.
