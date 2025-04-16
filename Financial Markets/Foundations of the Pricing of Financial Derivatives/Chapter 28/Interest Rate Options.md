---
tags:
  - '#american_options'
  - '#binomial_tree'
  - '#exercise_rate'
  - '#interest_rate_calls'
  - '#interest_rate_options'
  - '#interest_rate_puts'
  - '#one_period_add_on_rates'
---
# 28.8 INTEREST RATE OPTIONS

With the tree of one-period add-on rates that we showed in Figure 28.8, we can easily value interest rate options. Remember that when interest rate options expire, the payoff is determined but not actually made until the next period.4

To illustrate, let us value three-period interest rate calls and puts with an exercise rate. of 0.09. Following the conversion method we described previously, Figure 28.10 shows the tree of one-period add-on rates through time 3..

The values of the interest rate calls and puts at time 3 are, therefore,

$V I R C(3,0.09)^{+++}=\operatorname*{max}(0,0.119240-0.09)0.8935=0.0261$ $V I R P(3,0.09)^{+++}=\operatorname*{max}(0,0.09-0.119249)\:0.8935=0.0000$ $V I R C(3,0.09)^{++-}=\operatorname*{max}(0,0.097078-0.09)0.9115=0.0065$ $V I R P(3,0.09)^{++-}=\operatorname*{max}(0,0.09-0.097078)0.9115=0.0000$ $V I R C(3,0.09)^{--+}=\operatorname*{max}(0,0.075354-0.09)0.9299=0.0000$ $V I R P(3,0.09)^{--+}=\operatorname*{max}(0,0.09-0.075354)0.9299=0.0136$ $V I R C(3,0.09)^{--}=\operatorname*{max}(0,0.054061-0.09)0.9487=0.0000$ $V I R P(3,0.09)^{--}=\operatorname*{max}(0,0.09-0.054061)0.9487=0.0341.$

![](images/b6dde49f1c0eaebdd2cb247c7fbf570aad7910b803a1efafc2e060c661f11336.jpg)
FIGURE 28.10 Binomial Tree of One-Period Add-on Spot Rates Through Time 3

<html><body><table><tr><td colspan="2"></td><td></td><td>VIRC(3,0.9)+++ = 0.0261 VIRP(3,0.9)+++ = 0.0000</td></tr><tr><td rowspan="3"></td><td>VIRC(3,0.9)+= 0.0080</td><td>VIRC(3,0.9)++=0.0146 VIRP(3,0.9)++=0.0000</td><td></td></tr><tr><td>VIRP(3,0.9)+=0.0029</td><td></td><td>VIRC(3,0.9)++- = 0.0065 VIRP(3,0.9)++-= 0.0000</td></tr><tr><td>VIRC(3,0.9)-= 0.0014</td><td>VIRC(3,0.9)+-=0.0030 VIRP(3,0.9)+-= 0.0063</td><td></td></tr><tr><td colspan="2">VIRP(3,0.9)-= 0.0137</td><td></td><td>VIRC(3,0.9)--+ = 0.0000 VIRP(3,0.9)--+ = 0.0136</td></tr><tr><td colspan="2"></td><td>VIRC(3,0.9)-- = 0.0000 VIRP(3,0.9)--= 0.0227</td><td>VIRC(3,0.9)---= 0.0000</td></tr></table></body></html>

Now, stepping back to time 2, we simply do the binomial weighted-average discounted value,

$$
V I R C(3,0.09)^{++}=\left[0.5(0.0261)+0.5(0.0065)\right]0.8954=0.0146
$$

$$
V I R P(3,0.09)^{++}=\left[0.5(0.0000)+0.5(0.0000)\right]0.8954=0.0000
$$

$$
V I R C(3,0.09)^{+-}=\left[0.5(0.0065)+0.5(0.0000)\right]0.9226=0.0030
$$

$$
V I R P(3,0.09)^{+-}=\left[0.5(0.0000)+0.5(0.0136)\right]0.9226=0.0063
$$

$$
V I R C(3,0.09)^{--}=\left[0.5(0.0000)+0.5(0.0000)\right]0.9507=0.0000
$$

$$
{V I R P}(3,0.09)^{--}=\left[0.5(0.0136)+0.5(0.0341)\right]0.9507=0.0227.
$$

We would then continue back to time 1 and time O in the same manner. The results are shown in Figure 28.11.

Again, if these options were American, at each node of the tree, the exercise values would be compared to each market value, and the greater value would be used.
