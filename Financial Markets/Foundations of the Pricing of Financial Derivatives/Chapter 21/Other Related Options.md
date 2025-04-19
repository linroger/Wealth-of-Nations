---
tags:
  - dual_strike_option
  - exchange_option
  - multi_asset_options
  - option_pricing
  - spread_option
  - stulz_formula
aliases:
  - Alternative Option
  - Outperformance Option
  - Rainbow Options
key_concepts:
  - Dual-strike option payoff
  - Exchange option model
  - Options on multiple assets
  - Relative asset performance
  - Rubinstein option pricing
  - Stulz's formulas
  - Two-color rainbow options
---

# 21.3 OTHER RELATED OPTIONS

There have been numerous extensions of the basic formula. Johnson (1987) and Rich and. Chance (1993) develop the formula under the condition of more than two assets. Also,. several other useful results have been obtained by Rubinstein (1991b). He first establishes a formula for an option that pays off the better of two risky assets or a fixed amount. of cash. Letting $X$ be the fixed amount of cash, we write this payoff as $\operatorname*{max}\bigl(S_{1T},S_{2T},X\bigr)$ Rubinstein then derives the pricing formula for this option. Let us denote this price as $c_{12X}$ where the subscripts denote asset price 1, asset price 2, and some fixed amount X. Then. note the following relationship, $\mathrm{max}\big(S_{1T},S_{2T},X\big)-X=\mathrm{max}\big[0,\mathrm{max}\big(S_{1T},S_{2T}\big)-X\big]$ This equivalence implies that a long position in Rubinstein's option paying the best of two assets. or $X$ and a short position worth the present value of $X$ is equivalent to a call on the max struck at $X$ Thus,

$$
c_{12X}=X e^{-r_{c}\tau}+c_{\mathrm{max}}.
$$

One particular problem encountered in using options on the max or min of two or more assets is that the asset values may be far apart at the start of the option. It would hardly be interesting to own a call paying off based on the maximum of two assets if one asset were currently worth $\$100$ and the other were currently worth $\$20$ . We already pretty much know which of the two assets will be the more highly valued asset at expiration. To overcome this problem, it is customary to express the option in terms of the assets' relative performances. For example, a call on the max would have a payoff as follows:

$$
\operatorname*{max}\left[0,\operatorname*{max}\left(\frac{S_{1T}-S_{1}}{S_{1}},\frac{S_{2T}-S_{2}}{S_{2}}\right)-X_{R}\right].
$$

Here the rates of return of the two assets are compared and the payoff is determined by comparing the greater return to an exercise rate,. $X_{R}$ , expressed in terms of a return. To. price this option, we first express the payoff above by adding a 1 to the returns on each asset and also the exercise price:

$$
\operatorname*{max}\left[0,\operatorname*{max}\left({\frac{S_{1T}}{S_{1}}},{\frac{S_{2T}}{S_{2}}}\right)-\left(1+X_{R}\right)\right].
$$

This equation is the payoff of a call on the max in which the price of each asset has been.
normalized to a value of 1 at the start and the exercise price is expressed as 1 plus a return.
This option can be valued directly with Stulz's formulas, inserting 1 as the price of each.
asset and using $1+X_{R}$ as the exercise price. The volatilities and the correlation remain the.
Same.4

Options on more than one asset are used in the over-the-counter options market. One particularly popular application is to have the assets be the returns on indexes representing different sectors of the market. Then the investor receives a return based on the better or worse performing sector. In practice, options paying off based on more than one asset are sometimes called two-color rainbow options. One variation is the outperformance option, whose payoff would be as follows:

$$
\operatorname*{max}\left[0,\left({\frac{S_{1T}-S_{1}}{S_{1}}}\right)-\left({\frac{S_{2T}-S_{2}}{S_{2}}}\right)\right].
$$

Note that this option pays off the difference between the return on asset 1 and the return on asset 2, if that difference is positive, and zero if the difference is negative. Of course, the option could be structured with the assets reversed. This option is an exchange option, expressed in rate of return form and can be priced by the exchange option model of Margrabe (1978). The standard version that pays off the difference in the value of the asset with the better return and the strike is commonly called an alternative option. Another variation is the spread option discussed in Chapter 17, whose payoff is

$$
\mathrm{max}\big[0,\big(S_{1T}-S_{2T}\big)-X\big].
$$

Another variation is the dual-strike option, whose payoff is

$$
\begin{array}{r}{\operatorname*{max}\bigl(0,S_{1T}-X_{1},S_{2T}-X_{2}\bigr),}\end{array}
$$

which has no known closed-form solution.
