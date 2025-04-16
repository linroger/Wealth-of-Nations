---
tags:
  - '#arbitrage'
  - '#call_options'
  - '#european_options'
  - '#min_max_options'
  - '#option_payoffs'
  - '#option_pricing'
  - '#put_call_parity'
  - '#put_options'
  - '#risk_free_bonds'
  - '#stulz_model'
---
# 21.1 CHARACTERISTICS OF STULZ'S MIN-MAX OPTION

Suppose there are two assets whose current values at an arbitrary time are $S_{1}$ and $S_{2}$ and whose values at expiration $T$ are $S_{1T}$ and $S_{2T}$ . Each asset may pay a cash flow yield or. require a payment, such as storage costs. We generically denote these continuous cash flows as $\delta_{1}$ and $\delta_{2}$ , consistent with dividend yields in the case where the underlying instruments. are stocks. Consider a call option with exercise price of. $X$ expiring at time $T$ that pays off based on which of the two assets has the lesser value. So what happens at expiration is. two-step. We first determine which is the lesser valued of the two assets. Then we insert the value of that asset into the standard payoff formula for a call. Thus, the call payoff is.

$$
c_{\mathrm{min},T}=\operatorname*{max}\bigl[0,\operatorname*{min}\bigl(S_{1T},S_{2T}\bigr)-X\bigr].
$$

Let us denote the current price of this option as $c_{m i n}$ , where it will be understood that the call is on the minimum value of asset 1 and asset 2 and is being evaluated at time $t.$

Likewise, a call on the maximum has a current price of. $c_{m a x}$ . At expiration, we first determine the greater valued of the two assets and insert the value of that asset into the formula for the payoff of a call. The call payoff in this case is.

$$
c_{\mathrm{max},T}=\mathrm{max}\bigl[0,\mathrm{max}\bigl(S_{1T},S_{2T}\bigr)-X\bigr].
$$

To establish some bounds on the prices of these options, much in the same way that we. developed bounds on the prices of standard European options, let us compare the payoffs of a portfolio of long the call on the max priced at $c_{\mathrm{max}}$ and long the call on the min priced at $c_{\mathrm{min}}$ with a portfolio consisting of long the standard call on asset 1 priced at. $c_{1}$ and long the standard call on asset 2 priced at $c_{2}$ . We must consider two general cases, $S_{1T}<S_{2T}$ and $S_{1T}\ge S_{2T}$ and three outcomes in each case, as displayed in Table 21.1 Panels A and B..

TABLE 21.1 Min and Max Calls in Comparison to Standard Calls


<html><body><table><tr><td colspan="4">Panel A.S1r < S2T</td></tr><tr><td rowspan="2"></td><td colspan="3">Payoff</td></tr><tr><td>S1r < S2r < X</td><td>ST ≤X≤S2T</td><td>S>S>X</td></tr><tr><td>Currentvalueofinstrument +Cmax</td><td>0</td><td>S2T - X</td><td>S2T - X</td></tr><tr><td>+Cmin</td><td>0</td><td>0</td><td>S1T -X</td></tr><tr><td>Total</td><td>0</td><td>S2T - X</td><td>S2T + S1T - 2X</td></tr><tr><td>+C1</td><td>0</td><td>0</td><td>S1T -X</td></tr><tr><td>+C2</td><td>0</td><td>S2T - X</td><td>S2T - X</td></tr><tr><td>Total</td><td>0</td><td>S2T - X</td><td>S2T + S1T - 2X</td></tr></table></body></html>

Panel B. $S_{1T}\ge S_{2T}$


<html><body><table><tr><td></td><td colspan="3">Payoff</td></tr><tr><td>Current value of instrument</td><td>S2T ≤ S2T <X</td><td>S2T ≤X≤S1T</td><td>X<S2T≤S1T</td></tr><tr><td>+Cmax</td><td>0</td><td>S1T - X</td><td>Sir -X</td></tr><tr><td>+Cmin</td><td>0</td><td>0</td><td>S2T - X</td></tr><tr><td>Total</td><td>0</td><td>S1T -X</td><td>S2T + S1T - 2X</td></tr><tr><td>+C1</td><td>0</td><td>S1T -X</td><td>Sir -X</td></tr><tr><td>+C2</td><td>0</td><td>0</td><td>S2T - X</td></tr><tr><td>Total</td><td>0</td><td>S1T - X</td><td>S2T + S1T -2X</td></tr></table></body></html>

It is apparent that the call on the max plus the call on the min has the same payoff as the combination of long calls on both assets. Therefore, the following parity must hold for. their current prices:

$$
c_{\operatorname*{max}}+c_{\operatorname*{min}}=c_{1}+c_{2}.
$$

Note that the cash flow yields related to the underlying assets do not directly influence this. parity. This type of max-min parity will continue to be useful because all we need to do is to derive a pricing model for one of the two min-max options, and the price of the other. can be obtained using the previous equation.

Now let us consider a put on the minimum. Its current price evaluated at time $t$ is expressed as $p_{m i n}$ . Its payoff at expiration is

$$
\begin{array}{r}{{p}_{\operatorname*{min},T}=\operatorname*{max}\bigl[0,X-\operatorname*{min}\bigl(S_{1T},S_{2T}\bigr)\bigr].}\end{array}
$$

A put on the maximum has a current price of ${\boldsymbol{p}}_{\mathrm{max}}$ and a payoff of.

$$
\begin{array}{r}{\ p_{\operatorname*{max},T}=\operatorname*{max}\bigl[0,X-\operatorname*{max}\bigl(S_{1T},S_{2T}\bigr)\bigr].}\end{array}
$$

Following similar arguments as the call, we note that1

$$
\begin{array}{r}{\dot{p}_{\operatorname*{max}}+{p}_{\operatorname*{min}}=\dot{p}_{1}+\dot{p}_{2}.}\end{array}
$$

Intuitively, the call on the max will be worth at least the call on the min as $\operatorname*{max}\bigl(S_{1T},S_{2T}\bigr)\geq\operatorname*{min}\left(S_{1T},S_{2T}\right).$ Specifically, $c_{\operatorname*{max}}\geq c_{\operatorname*{min}}$ . We demonstrate this intuition in Table 21.2. Thus, if $c_{\mathrm{max}}\geq c_{\mathrm{min}}$ , then a portfolio can be created such that there is a positive probability of receiving money and no chance of losing. Clearly, this would require a nonnegative investment; otherwise, we have arbitrage resulting in disequilibrium.

Following a similar argument, the put on the min will be worth at least the put on the max. Specifically, $p_{\operatorname*{min}}\ge p_{\operatorname*{max}}$ . We demonstrate this intuition in Table 21.3. Thus, if $p_{\operatorname*{min}}<p_{\operatorname*{max}}$ then again there is a portfolio that can be created such that there is a positive probability of receiving money and no chance of losing. Clearly, this would require a nonnegative investment; otherwise, we have arbitrage resulting in disequilibrium.

IABLE 21.2 Max Call in Comparison to Min Call


<html><body><table><tr><td colspan="4">Panel A.Sir < S2T</td></tr><tr><td></td><td colspan="3">Payoff</td></tr><tr><td>Currentvalue ofinstrument</td><td>S1r < S2T < X</td><td>Sr≤X≤S2T</td><td>S>S>x</td></tr><tr><td>+Cmax</td><td></td><td>S2T - X</td><td>S2T - X</td></tr><tr><td>-Cmin</td><td>0</td><td>0</td><td>-(S1r - X)</td></tr><tr><td>Total</td><td>0</td><td>S2T - X</td><td>S2T - S1T >0</td></tr></table></body></html>

Panel B. $S_{1T}\ge S_{2T}$


<html><body><table><tr><td></td><td colspan="3">Payoff</td></tr><tr><td>Current value of instrument</td><td>S2T ≤S1T <X</td><td>S2T ≤X≤S1T</td><td>X<S2r< S1T</td></tr><tr><td>+Cmax</td><td>0</td><td>S1T -X</td><td>S1T -X</td></tr><tr><td>-Cmin</td><td></td><td>0</td><td>-(S2r - X)</td></tr><tr><td>Total</td><td>0</td><td>S1r -X</td><td>S1T - S2T >0</td></tr></table></body></html>

IABLE 21.3 Min Put in Comparison to Max Put

<html><body><table><tr><td colspan="4">Panel A. S1r < S2T</td></tr><tr><td colspan="4"></td></tr><tr><td>Current value of instrument</td><td>S1T < S2T < X</td><td>Payoff Sr ≤X≤S2T</td><td>X<Sir< S2T</td></tr><tr><td>+Pmin</td><td>X-S1T</td><td>X-S1T</td><td>0</td></tr><tr><td>-Pmax</td><td>-(X - S2T)</td><td>0</td><td>0</td></tr><tr><td>Total</td><td>S2T - S1T >0</td><td>X-S1r MO</td><td>0</td></tr><tr><td colspan="4">Panel B. Sr ≥ S2T</td></tr><tr><td></td><td colspan="3">Payoff</td></tr><tr><td>Current value of instrument</td><td>S2r ≤S1r <X</td><td>S2T ≤X≤S1T</td><td>X<S2r< S1T</td></tr><tr><td>+Pmin</td><td>X -S2T</td><td>X -S2T</td><td>0</td></tr><tr><td>—Pmax</td><td>-(X - S1T)</td><td>0</td><td>0</td></tr><tr><td>Total</td><td>S1T - S2T</td><td>X -S2T</td><td>0</td></tr><tr><td></td><td></td><td>MO</td><td></td></tr></table></body></html>

Further, the call on the max will be worth at least the maximum of the call on each asset $c_{\operatorname*{max}}\geq\operatorname*{min}\left(c_{1},c_{2}\right)$ . Without loss of generality, we let $c_{1}>c_{2}$ . We demonstrate this intuition in Table 21.4. Thus, if $c_{\operatorname*{max}}\geq c_{1}$ , then again there is a portfolio that can be created such that there is a positive probability of receiving money and no chance of losing. Clearly,. this would require a nonnegative investment; otherwise, we have arbitrage resulting in. disequilibrium.

Following a similar argument, the put on the min will be worth at least the maximum of the put on each asset or $\begin{array}{r}{\phi_{\operatorname*{max}}\ge\operatorname*{min}\left(\phi_{1},p_{2}\right)}\end{array}$

Consider the following comparison whereby a put on the min is shown to be equivalent. to a long position in risk-free bonds with face value. $X$ maturing at the option's expiration, a short position in a call on the minimum struck at zero, whose price we denote as $c_{\operatorname*{min},X=0}$ and a long position on a call on the min with exercise price X. Note first that a call on the. minimum struck at zero is an instrument that always pays off the lower-priced asset and there are effectively two exercise prices, $X=0$ and $X>0$ . We denote the current price of a call on the min struck at zero as $c_{\operatorname*{min},X=0}$ . We illustrate these results in Table 21.5..

From Table 21.5, it is apparent that a put on the min is a perfect substitute for the combination of options and the risk-free bond. Consequently, the current value of the put on the min is the same as the current value of the combination, namely

$$
\begin{array}{r}{p_{\operatorname*{min}}=X e^{-r_{c}\tau}-c_{\operatorname*{min},X=0}+c_{\operatorname*{min}}.}\end{array}
$$

Thus, once we have already obtained a formula for a call on the minimum, we can simply use this formula to get a put on the minimum.

Finally, we can easily obtain the price of the put on the maximum. Let us compare it to a long position in a pure discount bond, a call on the maximum struck at zero, and a long call on the maximum with an exercise price of $X$ illustrated in Table 21.6.

TABLE 21.4 Max Calls in Comparison to Max of Two Standard Calls


<html><body><table><tr><td colspan="4">Panel A. S1r < S2T</td></tr><tr><td colspan="4"></td></tr><tr><td>Currentvalue ofinstrument</td><td>S1r < S2r < X</td><td>ST ≤X≤S2T</td><td>X<ST < S2T</td></tr><tr><td>xew+</td><td>0</td><td>S2T - X</td><td>S2T - X</td></tr><tr><td>-C1</td><td>0</td><td>0 S2T - X</td><td>-(S1r - x) S2T - S1T</td></tr><tr><td>Total</td><td>0</td><td></td><td>>o</td></tr><tr><td colspan="4">Panel B. S1T ≥ S2T</td></tr><tr><td></td><td colspan="3">Payoff</td></tr><tr><td>Currentvalue ofinstrument</td><td>S2r ≤ Sr < X</td><td>s>xs</td><td>>X</td></tr><tr><td>+Cmax</td><td>0</td><td>S1r -X</td><td>S1T -X</td></tr><tr><td>-C1</td><td>0</td><td>-(Sir - x)</td><td>-(S1T - X)</td></tr><tr><td>Total</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

IABLE 21.5 Put-Call Parity for Options on the Min

<html><body><table><tr><td colspan="4">Panel A. S1r < S2T</td></tr><tr><td rowspan="2"></td><td colspan="3">Payoff</td></tr><tr><td>SiT < S2T < X</td><td>S1r ≤X≤S2T</td><td>X<ST < S2T</td></tr><tr><td>+Pmin</td><td>X-S1T</td><td>X-S1T</td><td>0</td></tr><tr><td>+Xe-rct</td><td>X</td><td>X</td><td>X</td></tr><tr><td>-Cmin,X=0</td><td>-S1T</td><td>-S1T</td><td>-S1T</td></tr><tr><td>+Cmin</td><td>0</td><td>0</td><td>S1r - X</td></tr><tr><td>Total</td><td>X -S1T</td><td>X-S1T</td><td>0</td></tr><tr><td colspan="4">Panel B. S1r ≥ S2T</td></tr><tr><td></td><td colspan="3">Payoff</td></tr><tr><td>Current value of instrument</td><td>S2r ≤ST <X</td><td>S2r ≤X≤S1T</td><td>X<S2r ≤ S1T</td></tr><tr><td>+Pmin</td><td>X -S2T</td><td>X -S2T</td><td>0</td></tr><tr><td>+Xe-rct</td><td>X</td><td>X</td><td>X</td></tr><tr><td>-Cmin,X=0</td><td>-S2T</td><td>-S2T</td><td>-S2T</td></tr><tr><td>+Cmin</td><td>0</td><td>0</td><td>S2T -X</td></tr><tr><td>Total</td><td>X -S2T</td><td>X-S2T</td><td>0</td></tr></table></body></html>

TABLE 21.6 Put-Call Parity for Options on the Max


<html><body><table><tr><td colspan="4">Panel A. Sir < S2T</td></tr><tr><td colspan="4"></td></tr><tr><td>Current value of instrument</td><td>SiT < S2T < X X -S2T</td><td>Payoff ST ≤X≤S2T</td><td>X<Sir < S2T 0</td></tr><tr><td>+Pmax +Xe-rct</td><td>X</td><td>0 X</td><td>X</td></tr><tr><td>—Cmax,X=0</td><td>-S2T</td><td>-S2T</td><td>-S2T</td></tr><tr><td>+Cmax</td><td>0</td><td>S2T -X</td><td>S2T - X</td></tr><tr><td>Total</td><td>X -S2T</td><td>0</td><td>0</td></tr><tr><td colspan="4">Panel B. S1r ≥ S2T</td></tr><tr><td></td><td colspan="3">Payoff</td></tr><tr><td>Current value of instrument</td><td>S2r ≤S1T < X</td><td>S2T ≤X≤S1T</td><td>X<S2T ≤S1T</td></tr><tr><td>+Pmax</td><td>X -S1T</td><td>0</td><td>0</td></tr><tr><td>+Xe-rct</td><td>+X</td><td>X+</td><td>+X</td></tr><tr><td>—Cmax,X=0</td><td>-S1T</td><td>-S1T</td><td>-S1T</td></tr><tr><td>+Cmax</td><td>0</td><td>S1T - X</td><td>S1T - X</td></tr><tr><td>Total</td><td>X-S1T</td><td>0</td><td>0</td></tr></table></body></html>

Equivalence is apparent and, consequently, the price of a put on the max can be obtained by the formula,

$$
\begin{array}{r}{p_{\operatorname*{max}}=X e^{-r_{c}\tau}-c_{\operatorname*{max},X=0}+c_{\operatorname*{max}}.}\end{array}
$$

Thus, once we obtain the price of a call on the minimum, we can then obtain the price of a call on the maximum using Equation (21.3), a put on the minimum using Equation (21.7), and a put on the maximum using Equation (21.8).
