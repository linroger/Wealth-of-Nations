---
tags:
  - '#american_options'
  - '#call_options'
  - '#convexity_rule'
  - '#european_options'
  - '#exercise_price'
  - '#option_pricing'
  - '#portfolio_k'
  - '#portfolio_l'
  - '#put_call_parity'
  - '#put_options'
---
# 2.8 THE CONVEXITY RULE

A mathematical function, $y=f(x)$ , is said to be convex if for any two values of $x$ $x_{2}>x_{1}$ we have that the line between these two $x$ values lies above or on the. $y=f(x)$ graph. It is possible to derive a relationship between the prices of three options differing by exercise price. Let their exercise prices be $X_{L}$ $X_{M}$ , and $X_{H}$ (for low, medium, and high) and the corresponding call prices be $c_{t L}$ $c_{t M}$ , and $c_{t H}$ . For convenience, we shall call these the first, second, and third calls, respectively. Let us construct Portfolio K consisting of $\omega$ units of the first call and $1-\omega$ units of the third call. In other words, we go long $\omega$ units of the first call and long $1-\omega$ units of the third. Portfolio. $\mathrm{L}$ consists of one unit of the second call. The value of $\omega$ is defined as $(X_{H}-X_{M})/(X_{H}-X_{L})$ so that $1-\omega$ is $(X_{M}-X_{L})/(X_{H}-X_{L})$ Table 2.9 shows the outcomes.

When $S_{T}<X_{L}$ , both portfolios produce the same result of zero value. When. $X_{L}\leq S_{T}<$ $X_{M}$ , Portfolio K is better than Portfolio L, because. $\omega>0$ and $S_{T}>X_{L}$ . When $X_{M}\leq S_{T}<$ $X_{H}$ , we can prove that Portfolio $\mathrm{K}$ is better by substituting the definition of. $\omega$ . In the last case, where $S_{T}>X_{H}$ , Portfolio K is equivalent to Portfolio L, which can also be proven. by substituting the definition of. $\omega$ . Putting these results together tells us that Portfolio K dominates Portfolio L. Consequently, the current value of Portfolio K must be at least as great as the current value of Portfolio L,.

$$
\omega c_{t L}+(1-\omega)c_{t H}\geq c_{t M}.
$$

TABLE 2.9 The Relationship Between the Prices of Three European Calls Differing Only by Their Exercise Prices


<html><body><table><tr><td></td><td></td><td colspan="4">ValueatExpiration</td></tr><tr><td>Instrument</td><td>CurrentValue</td><td></td><td></td><td>ST <XLXL ≤ S <XM XM ≤ ST <XH</td><td>Sr ≥ XH</td></tr><tr><td>Portfolio K</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>European call</td><td>OCtL</td><td>0</td><td>w(ST -XL)</td><td>@(ST -XL)</td><td>@(ST -XL)</td></tr><tr><td>European call</td><td>(1-∞)tH</td><td>0</td><td>0</td><td>0</td><td>(1 -∞)(S -XH)</td></tr><tr><td>Total Portfolio L</td><td>H(-1)+7∞</td><td>0</td><td>の(ST -XL)</td><td>w(ST -XL)</td><td>x∞ -s -(1 -∞)XH</td></tr><tr><td>European call</td><td>CtM</td><td>0</td><td>0</td><td>ST - XM</td><td>ST - XM</td></tr></table></body></html>

TABLE 2.10 The Relationship Between the Prices of Three European Puts Differing Only by Their Exercise Prices


<html><body><table><tr><td></td><td></td><td colspan="4">Value atExpiration</td></tr><tr><td>Instrument</td><td>CurrentValue</td><td>x >s</td><td>XL ≤ S < XM</td><td>XM ≤ ST < XH XH ≤ ST</td><td></td></tr><tr><td>Portfolio M</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Europeanput</td><td>OPtL</td><td>@(XL -ST)</td><td>0</td><td>0</td><td>0</td></tr><tr><td>Europeanput</td><td>(1-∞)PtH</td><td></td><td>(1 -∞)(XH-ST） (1-∞)(XH-ST） (1-∞)(XH-ST)</td><td></td><td>0</td></tr><tr><td>Total</td><td>OPtL +(1-∞)PtH</td><td>s-x∞ Hx( - L)+</td><td>(1 -∞)(XH-S） (1 -∞)(XH-ST)</td><td></td><td>0</td></tr><tr><td>Portfolio N</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>European put</td><td>PM</td><td>XM - ST</td><td>XM - ST</td><td>0</td><td>0</td></tr></table></body></html>

This statement is called the convexity rule because it proves that the option price is convex. with respect to the exercise price.' If there are dividends on the asset, the rule is not affected because none of the positions above will collect dividends. If the options were American, Portfolio K would still dominate Portfolio L because the payoffs above at expiration would. occur early. Thus,

$$
\begin{array}{r}{\omega C_{t L}+(1-\omega)C_{t H}\geq C_{t M}.}\end{array}
$$

Now, let us prove the rule for puts. Consider Table 2.10, which is based on Portfolios M and N.

It is easy to see that Portfolio M dominates Portfolio N. For the case in which $S_{T}\geq X_{H}$ both portfolios are worth zero. For the case in which $X_{M}\leq S_{T}<X_{H}$ Portfolio $_\mathrm{N}$ is worth zero, whereas Portfolio M has a positive value. For the case in which $X_{L}\leq S_{T}<X_{M}$ , we can prove that Portfolio M is worth more than Portfolio $_\mathrm{N}$ by substituting the definition of o. And for the case in which $S_{T}<X_{L}$ , it can be shown that Portfolio M dominates Portfolio N by also substituting the definition of o. These results mean that

$$
\omega p_{t L}+(1-\omega)p_{t H}\geq p_{t M}.
$$

![](images/f69c7d455860e8ee9d61daab354d7183f835f9890e3b908ba43658daf828ead5.jpg)
FIGURE 2.5 Relationship Between Option Prices and Strike Prices Expressed as Percentage of Stock Price

If there are dividends, the results are unaffected, as these instruments will not receive or pay dividends. If the puts are American, the outcomes above would occur early, and the. same result would hold..

$$
\omega P_{t L}+(1-\omega)P_{t H}\geq P_{t M}.
$$

So put options are also convex in the exercise price.

Figure 2.5 illustrates the convex relationship between call and put option mid prices and different strike price expressed as a percentage of the stock price. Note that for both the upper and lower limits, the relationship converges to linear. Hence, the convex relationships identified previously may at times be simply equal.

We now turn to addressing put-call parity.
