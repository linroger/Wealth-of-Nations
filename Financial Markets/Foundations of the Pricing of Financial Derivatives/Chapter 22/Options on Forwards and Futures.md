---
tags:
  - european_option
  - futures_contracts
  - hedged_portfolio
  - option_pricing
  - options_on_futures
aliases:
  - Futures Options
  - Options on Futures
key_concepts:
  - Dynamically hedged portfolio
  - Futures market transparency
  - Long call option
  - Option pricing model
  - Short put option
---

# 22.3 OPTIONS ON FORWARDS AND FUTURES

Options on forwards are not widely used, but options on futures are very actively traded in the Us. One of the reasons for this is that futures markets are quite transparent. Prices are readily available, and there is considerable liquidity for many of these instruments. With the underlying being a futures contract and it being so widely traded in typically quite liquid. markets, it is not surprising that options on futures are quite popular. A long call option that is exercised leads to a long position in the futures, whereas the counterparty is assigned. a short position in the futures. A put option that is exercised leads to a short position in the underlying, whereas the counterparty is assigned a long position. If the futures expires at the same time as the option, exercise of the option converts into a position in the futures that immediately converts into a position in the underlying asset. As such, a European option on a futures that expires at the same time as the futures would have the same price as the corresponding European option on the spot..

Some options on futures, however, expire earlier than the underlying futures. In either case, however, we need an option pricing model that values the option in terms of the futures. Let us consider an option on a futures that expires in time. $T^{*}$ and with a time. to expiration is. $\tau^{*}$ . The underlying futures expires at. $T$ and the time to expiration of the futures is $\tau$ . To price this option, we shall construct a dynamically hedged portfolio of the option and the underlying futures. Specifically, we shall buy. $b$ call options and sell one. futures. The value of this portfolio at time. $t$ is

$$
w_{t}=b c_{t}.
$$

This equation does not imply that the futures price is zero when this portfolio is assembled. This statement is only that the value is xero. The price is certainly nonzero, and changes in price create value. If we properly choose the value of $b$ , we can convert this portfolio to a hedged portfolio so that the change in the value of the portfolio over the next instant can be expressed as

$$
d w_{t}=d f_{t}+b d c_{t}.
$$

Note a significant difference in Equations (22.16) and (22.17) that may seem inconsistent. In the latter, the value of the overall position reflects the change in both the value of the futures and the value of the option. For the former, the value of the futures starts off at zero, in accordance with the principle that the value of a futures is zero when initiated, just as with a forward contract.6 If the portfolio is completely hedged, its instantaneous return should be $\boldsymbol{w}_{t}\boldsymbol{r}_{c}d t$ . Hence, we can say that the change in the futures plus the change. in the value of $b$ options must equal the initial value,. $w_{t}$ plus interest,

$$
\begin{array}{r}{d f_{t}+b d c_{t}=w_{t}r_{c}d t}\ {=b c_{t}r_{c}d t.}\end{array}
$$

As with standard European options on the spot asset, we can assume that the call price is a function of the futures price and time. As such, we can express the call price change using Ito's lemma,

$$
d c_{t}=\frac{\partial c_{t}}{\partial f_{t}}d f_{f}+\frac{\partial c_{t}}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial f_{r}^{2}}d f_{t}^{2}.
$$

Substituting Equation (22.19) into Equation (22.18) and rearranging, we obtain

$$
b c_{t}r_{c}d t=d f_{t}+b\Bigg(\frac{\partial c_{t}}{\partial f_{t}}d f_{t}+\frac{\partial c_{t}}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial{f_{t}}^{2}}d{f_{t}}^{2}\Bigg).
$$

We are free to set the hedge ratio at whatever we want. Thus, if we set $b=-\partial f_{t}/\partial c_{t}$ , we obtain

$$
-\left({\frac{\partial f_{t}}{\partial c_{t}}}\right)c_{t}r_{c}d t=d f_{t}-\left({\frac{\partial f_{t}}{\partial c_{t}}}\right)\left({\frac{\partial c_{t}}{\partial f_{t}}}d f_{t}+{\frac{\partial c_{t}}{\partial t}}d t+{\frac{1}{2}}{\frac{\partial^{2}c_{t}}{\partial f_{t}^{2}}}d f_{t}^{2}\right).
$$

Rearranging, we have

$$
-\left(\frac{\partial f_{t}}{\partial c_{t}}\right)c_{t}r_{c}d t=-\left(\frac{\partial f_{t}}{\partial c_{t}}\right)\left(\frac{\partial c_{t}}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial{f_{t}}^{2}}{d f_{t}}^{2}\right).
$$

Because $d f_{t}$ is removed, the Equation (22.22) is non-stochastic, which means the risk is. hedged away. Now, we need to simplify Equation (22.22). Recall the standard stochastic process for the asset, which we learned when studying options,.

$$
d S_{t}=S_{t}\alpha d t+S_{t}\sigma d\mathrm{W}_{t}.
$$

And recall the futures pricing model, Equation (22.15). Because we are now in continuous time, we should use its continuous analog,.

$$
f_{t}=S_{t}e^{r_{c}\tau}.
$$

Because the futures price is known to be a function of time and the spot price, which we know follows geometric Brownian motion, we can express the futures price in terms of. the spot price and time using Ito's lemma,.

$$
d f_{t}=\frac{\partial f_{t}}{\partial S_{t}}d S_{t}+\frac{\partial f_{t}}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}f_{t}}{\partial{S_{t}}^{2}}d{S_{t}}^{2}.
$$

Equation (22.25) contains partial derivatives that can be derived from Equation (22.24) as follows:7

$$
\begin{array}{l}{{\displaystyle{\frac{\partial{\boldsymbol{f}}_{t}}{\partial{\boldsymbol{S}}_{t}}}=e^{r_{c}\tau}}}\ {~}\ {{\displaystyle{\frac{\partial^{2}{\boldsymbol{f}}_{t}}{\partial{\boldsymbol{S}}_{t}^{2}}}=0}}\end{array}
$$

$$
\frac{\partial f_{t}}{\partial t}=-r S_{t}e^{r_{c}\tau},
$$

and insert these into Equation (22.25),

$$
d f_{t}=e^{r_{c}\tau}d S_{t}+-r S_{t}e^{r_{c}\tau}+0.
$$

Substituting the stochastic process of the asset from Equation (22.23), the expression for $d f_{t}$ then becomes

$$
\begin{array}{r l}&{d f_{t}=f_{t}\big(\alpha d t+\sigma d\mathrm{W}_{t}\big)+-r_{c}f_{t}d t}\ &{\qquad=f_{t}\big(\alpha-r_{c}\big)d t+f_{t}\sigma d\mathrm{W}_{t}.}\end{array}
$$

Squaring this equation, we now know that $d f_{t}^{2}$ will bee $f_{t}^{2}\sigma^{2}d t$ Then, substituting into. Equation (22.22), we obtain

$$
-\left(\frac{\partial f_{t}}{\partial c_{t}}\right)c_{t}r d t=-\left(\frac{\partial f_{t}}{\partial c_{t}}\right)\left(\frac{\partial c_{t}}{\partial t}d t+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial f_{t}^{2}}f_{t}^{2}\sigma^{2}d t\right).
$$

Now multiply by. $\partial c_{t}/\partial f_{t}$ and rearrange to obtain

$$
c_{t}r_{c}=\frac{\partial c_{t}}{\partial t}+\frac{1}{2}\frac{\partial^{2}c_{t}}{\partial{f_{t}}^{2}}{f_{t}}^{2}\sigma^{2}.
$$

This equation is very similar to the partial differential equation for Black-Scholes-Merton. One difference is that in the BSM equation, there is a term $r_{c}S_{t}\partial c_{t}/\partial S_{t}$ which reflects interest on the funds tied up in the underlying. Here, however, there are no funds tied up in the underlying, because it is a futures.

The boundary condition is $c_{T}=\operatorname*{max}\bigl(0,f_{T}-X\bigr).$ The solution is similar to the BSM model and is often referred to as the Black model, as Fischer Black provided this result in a separate paper (Black 1976):

$$
\begin{array}{l}{{c_{t}=e^{-r_{c}\tau^{*}}\big[f_{t}N\big(d_{1}\big)-X N\big(d_{2}\big)\big]}}\ {{\mathrm{}}}\ {{d_{1}=\frac{\ln\left(\frac{f_{t}}{X}\right)+\left(\frac{\sigma^{2}}{2}\right)\tau^{*}}{\sigma\sqrt{\tau^{*}}}}}\ {{d_{2}=d_{1}-\sigma\sqrt{\tau^{*}}.}}\end{array}
$$

Recall that the option expiration, $\tau^{*}$ is shorter than the futures expiration, $\tau$ If the option and futures expire at the same time, we would insert. $\tau$ for $\tau^{*}$ and using the futures pricing equation, (22.24), we would find that Equation (22.31) would be precisely the BSM equation for the value of an option on the asset. Based on put-call parity, we can easily. find the put option equation or

$$
\begin{array}{r l}&{\boldsymbol{\phi}_{t}=\boldsymbol{c}_{t}-e^{-r_{c}\tau^{*}}\big(\boldsymbol{f}_{t}-\boldsymbol{X}\big)}\ &{\quad=e^{-r_{c}\tau^{*}}\big\{\boldsymbol{X}\big[1-N\big(d_{2}\big)\big]-f_{t}\big[1-N\big(d_{1}\big)\big]\big\}}\ &{\quad=e^{-r_{c}\tau^{*}}\big[\boldsymbol{X}\boldsymbol{N}\big(-d_{2}\big)-f_{t}\boldsymbol{N}\big(-d_{1}\big)\big].}\end{array}
$$

We now illustrate this model with a numerical example. Suppose the futures price is $\$52$ , the exercise price is $\$52.8$ , the time to expiration of the option contract is 0.25, the. interest rate is $2.0\%$ , and the volatility is $35\%$ . First, solving for the value of. $d_{1}$ and $d_{2}$ we have

$$
\begin{array}{r l}&{d_{1}=\frac{\ln\left(\frac{f_{t}}{X}\right)+\left(\frac{\sigma^{2}}{2}\right)\tau^{*}}{\sigma\sqrt{\tau^{*}}}=\frac{\ln\left(\frac{52}{52.8}\right)+\left(\frac{0.35^{2}}{2}\right)0.25}{0.35\sqrt{0.25}}=0.000}\ &{d_{2}=d_{1}-\sigma\sqrt{\tau^{*}}=0.000-0.35\sqrt{0.25}=-0.175.}\end{array}
$$

Based on Table 5.1: Standard Normal Cumulative Distribution Function Table, we have

$$
\begin{array}{r l}&{c_{t}=e^{-r_{c}\tau^{*}}\left[f_{t}N\big(d_{1}\big)-X N\big(d_{2}\big)\right]}\ &{\quad=e^{-(0.02)0.25}\left[52(0.5)-52.8(0.430540)\right]}\ &{\quad=3.2512~\mathrm{and}}\end{array}
$$

$$
\begin{array}{l}{{\displaystyle p_{t}=c_{t}-e^{-r_{c}\tau^{*}}\left(f_{t}-X\right)}~}\ {{\displaystyle~=3.2512-e^{-(0.02)0.25}(52-52.8)}~}\ {{\displaystyle~=4.0472}.}\end{array}
$$

As the case with options on the spot, American options on futures are considerably. more complex than European options on futures. What further complicates options on futures, however, is that call options could be optimally exercised early, which is not the case with options on the spot, as we have already discussed. This result occurs because of how the futures price converges to the spot price. Notice in Equation (22.3), the futures is higher than the spot. As expiration approaches, the futures must be pulled toward the spot. This pulling effect operates somewhat like a dividend, which pulls a stock price down. As we studied with options on stocks, a dividend can trigger early exercise that. avoids the loss due to the downward pressure on the underlying. This downward pressure on the futures has the same effect. As such, it might be optimal to exercise a call option on a futures early. Put options can also be exercised early, just as with put options on assets,. but the downward pressure that can trigger the early exercise of call options on futures will discourage the early exercise of put options on futures. If there are carrying costs or other benefits related to the futures price, the probability of early exercise will be altered, depending on the magnitude of these costs. Pricing an American call on a futures will typically use a numerical method, such as the binomial model. There is also an approximation formula that is a variation of the Barone-Adesi-Whaley formula we discussed in Chapter 19.
