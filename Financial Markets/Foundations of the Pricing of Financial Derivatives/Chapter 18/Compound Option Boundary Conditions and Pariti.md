---
tags:
  - arbitrage
  - boundary_conditions
  - compound_option
  - european_option
  - option_pricing
aliases:
  - call on call
  - compound option
  - option bounds
  - option parities
key_concepts:
  - European-style call options
  - arbitrage profits
  - call on call bounds
  - compound option boundary conditions
  - option valuation problems
  - underlying asset price
---

# 18.3 COMPOUND OPTION BOUNDARY CONDITIONS AND PARITIES

We briefly review the appropriate compound option boundary conditions and parities followed by selected proofs. For completeness, we consider both the possibility of dividends on the underlying asset, denoted $\delta$ as before, as well as the possibility of dividends on the. underlying option, denoted $\widehat{q}$ or the option yield. In the previous section, recall equity was. viewed as an option on the firm and that equity may pay a dividend. Thus, for completeness, we need a model that can address the yield paid out of the firm as a whole as well as the yield paid out specifically to equity holders. Also, recall that compound options are often used in modeling complex financial valuation problems where the capacity to capture a cash flow related to the underlying option is useful..

Going forward, we adopt the more general case where. $S_{t}$ is the underlying asset price. Thus, in our prior discussion,. $S_{t}$ is the underlying firm value. In this way, the following. results are generic and can easily be applied to other assets.

We now review the detailed proof for the call on call lower and upper bounds. The remaining bounds are given without proof as they follow in a similar manner.

Call on call lower bound:

$$
c c_{t}\left[c_{t}\left(S_{t},X_{U},T_{2}\right),X_{C},T_{1}\right]\ge\operatorname*{max}\left[0,e^{-\widehat{q}\tau_{1}}c_{t}\left(S_{t},X_{U},T_{2}\right)-X_{C}e^{-r_{c}\tau_{1}}\right].
$$

Recall for European-style call options on the underlying instrument, we have the following lower bound:

$$
c_{t}\geq\operatorname*{max}\left(0,S_{t}e^{-\delta\tau_{2}}-X_{U}e^{-r_{c}\tau_{2}}\right).
$$

Thus, in a similar fashion, for a call on a call option, we have

$$
c c_{t}\left[c_{t}\left(S_{t},X_{U},T_{2}\right),X_{C},T_{1}\right]\ge\operatorname*{max}\left[0,e^{-\widehat{q}\tau_{1}}c_{t}\left(S_{t},X_{U},T_{2}\right)-X_{C}e^{-r_{c}\tau_{1}}\right].
$$

Although the intuition may not be clear, the boundary condition must hold or otherwise there will be arbitrage profits available, as illustrated in the following proof..

Proof: Recall that $X_{1}>0$ and that limited liability implies observed option prices are nonnegative. Assume the opposite:

$$
c c_{t}\left[c_{t}\left(S_{t},X_{U},T_{2}\right),X_{C},T_{1}\right]<\operatorname*{max}\left[0,e^{-\widehat{q}\tau_{1}}c_{t}\left(S_{t},X_{U},T_{2}\right)-X_{C}e^{-r_{c}\tau_{1}}\right].
$$

IABLE 18.1 Lower Bound for Call on Call


<html><body><table><tr><td></td><td></td><td colspan="2">At Expiration (T)</td></tr><tr><td>Strategy</td><td>Today (t)</td><td>CT ≤ Xc</td><td>CT > Xc</td></tr><tr><td>Sell e-@r1 units of underlying call</td><td>+e-qar1Ct</td><td>-CT</td><td>CT</td></tr><tr><td>Lend Xce-r1</td><td>-Xce-rt1</td><td>+Xc</td><td>+X</td></tr><tr><td>Buy call on call</td><td>+CCt</td><td>0</td><td>CT -Xc</td></tr><tr><td>Net</td><td>> 0 (By assumption)</td><td>+Xc - C ≥ 0 (By column)</td><td>=0</td></tr></table></body></html>

Note if $e^{-\widehat{q}\tau_{1}}c_{t}\left(S_{t},X_{U},T_{2}\right)-X_{C}e^{-r_{c}\tau_{1}}<0$ then $c c_{t}\left[c_{t}\left(S_{t},X_{U},T_{2}\right),X_{C},T_{1}\right]<0.$ In this case, simply sell the compound option and you have positive cash flow today at no risk in the future. Therefore, we only need now consider the case where

$$
c c_{t}\left[c_{t}\left(S_{t},X_{U},T_{2}\right),X_{C},T_{1}\right]<e^{-\hat{q}\tau_{1}}c_{t}\left(S_{t},X_{U},T_{2}\right)-X_{C}e^{-r_{c}\tau_{1}}.
$$

Move terms to the greater-than side,

$$
0<e^{-\widehat{q}\tau_{1}}c_{t}\left(S_{t},X_{U},T_{2}\right)-X_{C}e^{-r_{c}\tau_{1}}-c c_{t}\left[c_{t}\left(S_{t},X_{U},T_{2}\right),X_{C},T_{1}\right].
$$

Table 18.1 provides a cash flow table illustrating the arbitrage profits.

Because this trading strategy results in receiving money today and there is no chance of paying money in the future, this trading strategy is very attractive and should not appear in rational markets for very long. Therefore, the original asserted boundary condition would hold.

Call on call upper bound:

$$
c c_{t}\left[c_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]\leq e^{-\widehat{q}\tau_{1}}c_{t}\left(S,X_{U},T_{2}\right).
$$

Recall for European call options on the underlying instrument, we have the following upper bound:

$$
c_{t}\leq S_{t}e^{-\delta\tau_{2}}.
$$

In a similar fashion, for a compound call on call option, we have

$$
c c_{t}\left[c_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]\leq e^{-\widehat{q}\tau_{1}}c_{t}\left(S,X_{U},T_{2}\right).
$$

The option to purchase another option should not cost more than the underlying yieldadjusted option; otherwise, one would just buy the underlying option.

Proof: Recall that $X_{\mathrm{C}}>0$ and limited liability implies observed option prices are nonnegative. Assume the opposite:

$$
c c_{t}\left[c_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]>e^{-\widehat{q}\tau_{1}}c_{t}\left(S,X_{U},T_{2}\right).
$$

Move terms to the greater-than side:

$$
c c_{t}\left[c_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]-e^{-\hat{q}\tau_{1}}c_{t}\left(S,X_{U},T_{2}\right)>0.
$$

TABLE 18.2  Upper Bound for Call on Call


<html><body><table><tr><td></td><td></td><td colspan="2">At Expiration (T)</td></tr><tr><td>Strategy</td><td>Today (t)</td><td>x</td><td>Ct > Xc</td></tr><tr><td>Sellcallon call</td><td>+CCt</td><td>0</td><td>(x-) -</td></tr><tr><td>Buy e-qr1 units of underlying call</td><td>-e-qr1ct</td><td>+</td><td>+CT</td></tr><tr><td>Net</td><td>>0</td><td></td><td>Xc > 0</td></tr><tr><td></td><td>(By assumption)</td><td>(By limited liability)</td><td>(By assumption)</td></tr></table></body></html>

Table 18.2 illustrates the arbitrage opportunity with a cash flow table.

Because this trading strategy results in receiving money today and there is no chance of paying money in the future, this trading strategy is very attractive and should not appear in. rational markets for very long. In other words, it is an easy arbitrage opportunity. There-. fore, the original asserted boundary condition must hold..

The remaining boundary conditions are stated without proof. Proofs would follow in a similar manner to what we just covered. Call on put lower bound:

$$
c h_{t}\left[p_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]\geq\operatorname*{max}\left[0,e^{-\widehat{q}\tau_{1}}p_{t}\left(S,X_{U},T_{2}\right)-X_{C}e^{-r_{c}\tau_{1}}\right].
$$

Call on put upper bound:

$$
c{\boldsymbol{p}}_{t}\left[{\boldsymbol{p}}_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]\leq e^{-{\widehat{q}}\tau_{1}}{\boldsymbol{p}}_{t}\left(S,X_{U},T_{2}\right).
$$

Put on call lower bound:

$$
{p c}_{t}\left[{c}_{t}\left({S},{X}_{U},{T}_{2}\right),{X}_{C},{T}_{1}\right]\ge\operatorname*{max}\left[0,{X}_{C}e^{-{r}_{c}{\tau}_{1}}-e^{-\widehat{q}{\tau}_{1}}{c}_{t}\left({S},{X}_{U},{T}_{2}\right)\right].
$$

Put on call upper bound:

$$
\begin{array}{r}{p c_{t}\left[c_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]\leq X_{C}e^{-r_{c}\tau_{1}}.}\end{array}
$$

Put on put lower bound:

$$
\begin{array}{r}{p\d_{t}\left[p_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]\geq\operatorname*{max}\left[0,X_{C}e^{-r_{c}\tau_{1}}-e^{-\widehat{q}\tau_{1}}\d{p}_{t}\left(S,X_{U},T_{2}\right)\right].}\end{array}
$$

Put on put upper bound:

$$
\begin{array}{r}{\dot{p}\dot{p}_{t}\left[\dot{p}_{t}\left({\cal S},X_{\cal C},T_{2}\right),X_{\cal U},T_{1}\right]\leq X_{\cal C}e^{-r_{c}\tau_{1}}.}\end{array}
$$

The underlying option put-call parity is:7

$$
e^{-\widehat{q}_{c}\tau_{2}}c_{t}\left(S,X_{U},T_{2}\right)-e^{-\widehat{q}_{b}\tau_{2}}p_{t}\left(S,X_{U},T_{2}\right)=S_{t}e^{-\delta\tau_{2}}-X_{C}e^{-r_{c}\tau_{2}}.
$$

IABLE 18.3 Call on Call-Call on Put Parity


<html><body><table><tr><td></td><td></td><td colspan="2">At Expiration (T)</td></tr><tr><td>Strategy</td><td>Today (t)</td><td>CT ≤ Xc</td><td>CT > Xc</td></tr><tr><td>Sell call on call</td><td>+CCt</td><td>0</td><td>CT -Xc</td></tr><tr><td>Buy put on call</td><td>-pct</td><td>L-x +</td><td>0</td></tr><tr><td>Buy e-qr1 units of underlying call</td><td>-e-qt1 Ct</td><td>+CT</td><td>+CT</td></tr><tr><td>Borrow e-rc Xc</td><td>+e-rc1 X</td><td>-Xc</td><td>-Xc</td></tr><tr><td>Net</td><td></td><td>=0</td><td>=0</td></tr></table></body></html>

The compound option put-call parity relations include:

$$
c c_{t}\left[c_{t}\left(\boldsymbol{S},\boldsymbol{X}_{U},T_{2}\right),\boldsymbol{X}_{C},T_{1}\right]-p c_{t}\left[c_{t}\left(\boldsymbol{S},\boldsymbol{X}_{U},T_{2}\right),\boldsymbol{X}_{C},T_{1}\right]=e^{-\hat{q}\tau_{1}}c_{t}-e^{-r_{c}\tau_{1}}\boldsymbol{X}_{C},
$$

$$
c p_{t}\left[p_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]-p{p_{t}}\left[p_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]=e^{-\hat{q}\tau_{1}}{p_{t}}-e^{-r_{c}\tau_{1}}X_{C},
$$

$$
\begin{array}{r l}&{c c_{t}\left[c_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]-p c_{t}\left[c_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]}\ &{\quad-\left\{c p_{t}\left[p_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]-p{p_{t}}\left[p_{t}\left(S,X_{U},T_{2}\right),X_{C},T_{1}\right]\right\}}\ &{\quad\quad=e^{-\delta\tau_{2}}c_{t}-e^{-r_{c}\tau_{2}}X_{C}.}\end{array}
$$

We now sketch the proofs for the put-call parity stated in Equation (18.31).
Proof: Rearranging and simplifying notation,.

$$
c c_{t}-p c_{t}-e^{-\widehat{q}\tau_{1}}c_{t}+e^{-r_{c}\tau_{1}}X_{C}=0.
$$

Consider the cash flow table shown in Table 18.3.

Because this trading strategy results in no cash flow in the future, this trading strategy. would be very attractive if the net cash flow today is either positive or negative. Thus, we place a question mark for the net cash flow today. If the net cash flow today is positive,. then sell the call on the call, buy the put on the call, buy. $e^{-\hat{q}\tau_{1}}$ units of the underlying call,. and borrow $e^{-r_{c}\tau_{1}}X_{\mathrm{C}}$ . If the net cash flow today is negative, then do the opposite set of. trades, that is, buy the call on call, sell the put on call, sell call, and lend $e^{-r_{c}\tau_{1}}X_{\mathrm{C}}$
